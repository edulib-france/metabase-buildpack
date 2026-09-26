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
Defaults to the version read from `.metabase-version` (see below), or to `*`
when the app has no such file.

### `.metabase-version`

A `.metabase-version` file at the root of the app pins the version without an
environment variable, so the deployed version lives in the app's own git
history: a change is reviewed like any other, and a rollback is a revert.
Blank lines, comments (`#`) and surrounding whitespace are ignored, and the
first remaining line is used:

```
# https://github.com/metabase/metabase/releases
v0.63.18
```

`METABASE_VERSION` still wins when it is set, so an urgent upgrade can be
applied from the dashboard and written back to the file afterwards. Remove the
variable to let the file take over.
