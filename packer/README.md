# Packer

This build step invokes `packer` commands in [Google Cloud Build](https://cloud.google.com/cloud-build).

Arguments passed to this builder will be passed to `packer` directly, allowing
callers to run [any Packer
command](https://www.packer.io/docs/commands/index.html).

## Building this Builder

Before using this builder in a Cloud Build config, it must be built and pushed to the registry in your 
project. Run the following command in this directory:

```
gcloud builds submit .
```

> **Advanced builder building:** To specify a particular version of packer, provide the packer version
> number, and the checksum of that version's zip archive, as Cloud Build [substitutions](https://cloud.google.com/cloud-build/docs/configuring-builds/substitute-variable-values#using_user-defined_substitutions):
> ```
> gcloud builds submit --substitutions=_PACKER_VERSION=1.5.5,_PACKER_VERSION_SHA256SUM=07f28a1a033f4bcd378a109ec1df6742ac604e7b122d0316d2cddb3c2f6c24d1 .
> ```

## Credentials

You can securely pass credentials to `packer` [using encrypted
files](https://cloud.google.com/cloud-build/docs/tutorials/using-encrypted-files).

See examples in the `examples` subdirectory.

## Status

This is unsupported demo-ware. Use at your own risk!
