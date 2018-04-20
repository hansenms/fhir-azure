Loading FHIR Example Data
--------------------------

If you are experienting with FHIR servers, you may want to preload some sample data. You can download [http://www.hl7.org/fhir/examples-json.zip](http://www.hl7.org/fhir/examples-json.zip), which contains a bunch of resources. However, that is a lot of data and can take some time to upload and depending on the setting of your FHIR server, it may timeout, so I would recommend chopping that dataset into smaller pieces. Here is a how to do that in PowerShell (you will need [PowerShell Community Extensions](https://www.powershellgallery.com/packages/Pscx) if you don't have them already):

First download the dataset and unzip it:

```
Invoke-WebRequest -Uri http://www.hl7.org/fhir/examples-json.zip -OutFile examples-json.zip
New-Item -Type Directory example-json
Expand-Archive -OutputPath .\example-json -Path .\examples-json.zip -ShowProgress
```

Then create new zip files with chunks:

```
$chunkSize = 100
$files = Get-ChildItem .\example-json\*.json
New-Item -Type Directory ".\example-json-files"

$length = $files.Length
$fileCount = 0
for ($index = 0; $index -lt $length; $index += $chunkSize)
{
    $zipFileName = ".\example-json-files\example-json-" + $fileCount + ".zip"
    $filesToZip = $files[$index..($index+$chunkSize-1)] | Select-Object -ExpandProperty FullName
    Compress-Archive -Path $filesToZip -DestinationPath $zipFileName
    $fileCount++
}
```

Then if you would like, you can loop through the zip files and preload them. Here is how to do that with a [vonk](https://fire.ly/vonk) server:

```
$zips = Get-ChildItem .\example-json-files\*.zip
foreach ($z in $zips)
{
    Write-Host "Processing file" $z.FullName
    Invoke-WebRequest -Method Post -Uri https://<VONK-SERVER-URL>/administration/preload -InFile $z.FullName -ContentType "application/octet-stream"
}
```