# Release handling for Debian Cloud images

## How to make a release

* Trigger a build on the `master` branch, specifying following variables:

| Name | Description
|+++|+++|
| `DIST` | The Debian distribution to release, currently only `buster`.
| `VERSION` | The image version to release, e.g. `20190718-412`.

## Variables

### Per project

* `$DEBIAN_SSH_KEY`
* `$DEBIAN_SSH_REMOTE`

### Per trigger

* `$DIST`: Must be `buster`
* `$VERSION`
