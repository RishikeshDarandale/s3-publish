# s3-publish

A simple utility to deploy a static website to s3-bucket

# Pre-requisite

**You need a node v8 or higher to run this utility.**

# Installation

## Install globally

```console
npm install --global s3-publish
```

## Install in project

```console
npm install --save-dev s3-publish
```

# Usage

This utility has following sub-commands:

## deploy

This sub-command sync the provided source folder with AWS s3 bucket.

```console
s3-publish deploy [options] <SOURCE_DIR> <S3_BUCKET_NAME>
```

### Options

`--delete`

This will delete all the files from the AWS s3 bucket which are not present in provided <SOURCE_DIR>

`--debug`

This will print extra debug statements for more visibility

## invalidate-cache

This sub-command will invalidate the cloudfront cache

```console
s3-publish invalidate-cache [options] <CLOUDFRONT_DISTRIBUTION_ID>
```

### Options

`--path <PATH>`

A object path to be invalidated. This can be provided multiple times to specify additional paths.

e.g.

```console
s3-publish invalidate-cache <CLOUDFRONT_DISTRIBUTION_ID> --path "/index.html" --path "/error.html"
```

