---
name: S3 Plugin
description: The S3 plugin can upload files and build artifacts to a S3 bucket, or S3-compatible bucket such as Minio.
hide_table_of_contents: true
---

# S3

## Usage

```
kind: pipeline
name: default

steps:
- name: upload
  image: plugins/s3
  settings:
    bucket: my-bucket-name
    access_key: a50d28f4dd477bc184fbd10b376de753
    secret_key: bc5785d3ece6a9cdefa42eb99b58986f9095ff1c
    source: public/**/*
    target: /target/location
```

## Parameter Reference

__endpoint__

custom endpoint URL (optional, to use a S3 compatible non-Amazon service)

__access_key__ (optional)

amazon key

__secret_key__ (optional)

amazon secret key

__bucket__

bucket name

__region__

bucket region (us-east-1, eu-west-1, etc)

__acl__

access to files that are uploaded (private, public-read, etc)

source
source location of the files, using a glob matching pattern. Location must be within the drone workspace.

target
target location of files in the bucket

encryption
if provided, use server-side encryption

strip_prefix
strip the prefix from source path

exclude
glob exclusion patterns

path_style
whether path style URLs should be used (true for minio)
