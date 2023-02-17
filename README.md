## Before you start

This [Aidbox configuration project](https://docs.aidbox.app/aidbox-configuration/aidbox-zen-lang-project) contains definition for the `AuditEventR5` resource. When `FHIR R5` is released the name of the resource will be changed to `AuditEvent`.

## Where examples can be found

`demo-fixtures.edn` file contains all the [AuditEvent samples](https://github.com/Aidbox/audit-log-viewer/blob/main/zrc/audit-log-viewer/demo-fixtures.edn).

## AuditEvent shapes

This repo contains the set of `AuditEvent` resource samples. Each sample is based on the public example or created from scratch. In the latter case, the form of the event is validated with the FHIR community.

### Significant event samples

- [User fails to login](samples/login-failure.md)
- [User logins in](samples/login-success.md)
- [User logs out](samples/logout-success.md)
- [Remote session starts](samples/remote-login-success.md)
- [Remote session end](samples/remote-logout-success.md)
- [Software configuration was updated](samples/software-configuration-updated.md)
