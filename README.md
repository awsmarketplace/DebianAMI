# Release handling for Debian Cloud images

## How to make a release

* Run a pipeline on the `master` branch via [webinterface](https://salsa.debian.org/cloud-team/debian-cloud-images-release/pipelines/new), specifying following variables:

| Name | Description
|---|---|
| `DIST` | The Debian distribution to release, currently only `buster`.
| `VERSION` | The image version to release, e.g. `20190718-412`.

* After receiving the finished notification from Microsoft, manually run the `golive` job.

## Variables

### Per project

Environment variables needs to be configured in the GitLab web interface.

 * `$UPLOAD_AZURE_NOTIFY_EMAIL`: Run Azure publish process and send report to given e-mail address.
 * `$UPLOAD_SSH_KEY`
 * `$UPLOAD_SSH_REMOTE`

### Per trigger

* `$DIST`: Must be `buster`
* `$VERSION`
