#!/bin/bash
for file in *.json ; do
    name=$(jq -r '.name' $file)
    sed -i "2 a\    \"symbolicName\": \"${name}\"," "$file";
    sed -i '2 a\    "linkedArtifactId": "93c85070-1c57-4f21-86a7-4aaf7ffe41e5",' "$file";
    sed -i "2 a\    \"linkedArtifactName\": \"${name}\"," "$file";

done
