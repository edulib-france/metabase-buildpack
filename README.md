# Metabase buildpack

This buildpack installs Metabase into a Scalingo app image.

> :warning: **This buildpack is not meant to be use as a standalone but rather
in a multi-buildpack deployment scenario** such as the one we prepared for you
in our [Metabase distribution](https://github.com/Scalingo/metabase-scalingo).

## Usage

We strongly advise to use our [Metabase distribution](https://github.com/Scalingo/metabase-scalingo)
and follow the instructions over there for a swift experience.

### Environment

The following environment variables are available for you to tweak your
deployment:

#### `METABASE_VERSION`

The version of Metabase you want to deploy.\
Use `*` or `latest` to instruct the buildpack to install the latest version
available.\
When specifying a precise version number, make sure to prefix it with a
**`v`**! For example: `v0.46.6.1`.\
Defaults to `*`
