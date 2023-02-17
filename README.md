## Before you start

This [Aidbox configuration project](https://docs.aidbox.app/aidbox-configuration/aidbox-zen-lang-project) contains definition for the `AuditEventR5` resource. When `FHIR R5` is released the name of the resource will be changed to `AuditEvent`.

## Where examples can be found

`demo-fixtures.edn` file contains all the [AuditEvent samples](https://github.com/Aidbox/audit-log-viewer/blob/main/zrc/audit-log-viewer/demo-fixtures.edn).

## AuditEvent shapes

This repo contains the set of `AuditEvent` resource samples. Each sample is based on the public example or created from scratch. In the latter case, the form of the event is validated with the FHIR community.

| What should be audited             | Example event id                                |
| ---------------------------------- | ----------------------------------------------- |
| User fails to login                | `:example-login-failure`                        |
| User logins                        | `:example-login-success`                        |
| User logs out                      | `:example-logout-success`                       |
| User remote sessions starts        | `:example-remote-login-success`                 |
| Software configuration was updated | `:example-service-event-software-configuration` |
