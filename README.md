# Release handling for Debian Cloud images

## How to make a release

* Run a pipeline on the `master` branch via [webinterface](https://salsa.debian.org/cloud-team/debian-cloud-images-release/pipelines/new), specifying following variables:

| Name | Description
|---|---|
| `DIST` | The Debian distribution to release, currently only `buster`.
| `VERSION` | The image version to release, e.g. `20190718-412`.
| `UPLOAD_AZURE_ENABLED` | Set to '1' to enable generation and release to Microsoft Azure
| `RELEASE_EC2_ENABLED` | Set to '1' to enable generation and publication to Amazon Web Services

* After receiving the finished notification from Microsoft, manually run the `golive` job.

## Variables

### Per project

Environment variables needs to be configured in the GitLab web interface.

 * `$UPLOAD_CONFIG`
 * `$UPLOAD_AZURE_NOTIFY_EMAIL`: Run Azure publish process and send report to given e-mail address.
 * `$UPLOAD_SSH_KEY`
 * `$UPLOAD_SSH_REMOTE`

### Per trigger

* `$DIST`: Must be `buster`
* `$VERSION`
* `$UPLOAD_AZURE_ENABLED`
* `$RELEASE_EC2_ENABLED`
