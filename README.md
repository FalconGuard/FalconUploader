## Falcon Uploader

Copyright © 2022 Falcon Guard


### Overview

Falcon Uploader is a tool for acquiring digital forensic artifacts from Windows systems and uploading them directly to Amazon Web Services S3 buckets. This tool can extract any file from a Windows system (32 or 64 bit) when executed with the correct privileges. Falcon Uploader will also calculate and upload the hash of each file extracted from the system.

### License

This software is licensed under the "Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International Public License" See the file LICENSE.pdf for additional details.

### Usage

The tool will take a directory path and a file name pattern from the user as input and will attempt to acquire all the files inside this directory that match the name pattern recursively. The tool also requires the name of the AWS S3 bucket that will be used for the upload and the credentials of a service account that has write access to the same bucket. The Collection Name is used as an identifier for the specific collection and is used to organize the artifacts in the target S3 bucket.

Select the correct version of the tool for your system (32 or 64 bit), open a prompt and use the command line below to run the tool:

```
C:\> falcon_uploader.exe -d <SOURCE DIRECTORY> -c <COLLECTION NAME> -p <FILE NAME PATTERN> -b <BUCKET NAME> -k <AWS KEY ID> -s <AWS SECRET ACESS KEY>
```

The tool must be executed with administrator privileges if the target files are located inside protect Windows directories like "C:\Windows".

You can read the blog post "Acquiring Forensic Artifacts with Falcon Uploader and Amazon S3 Buckets" on our company website (https://www.falconguard.cz/blog) for additional details on how to prepare a recommended configuration of the AWS service account and S3 buckets for this tool.

### Important

This software was written in Python and compiled as a Windows executable. Some Antivirus products could flag Python executables as malicious and block their execution. If you have issues running this tool, then try to create an exclusion for it in your Antivirus console. 
