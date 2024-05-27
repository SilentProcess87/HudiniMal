# Define the path to the input file containing the Base64 string
$inputFilePath = "C:\path\to\input\file.txt"

# Define the path to the output binary file
$outputFilePath = "C:\path\to\output\file.bin"

# Read the Base64 string from the input file
$base64String = Get-Content -Path $inputFilePath -Raw

# Convert the Base64 string to a byte array
$bytes = [System.Convert]::FromBase64String($base64String)

# Write the byte array to the binary file
[System.IO.File]::WriteAllBytes($outputFilePath, $bytes)

Write-Output "The binary file has been created successfully at $outputFilePath"
