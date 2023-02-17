## Before you start

This [Aidbox configuration project](https://docs.aidbox.app/aidbox-configuration/aidbox-zen-lang-project) contains definition for the `AuditEventR5` resource. When `FHIR R5` is released the name of the resource will be changed to `AuditEvent`.

## Where examples can be found

`demo-fixtures.edn` file contains all the [AuditEvent samples](https://github.com/Aidbox/audit-log-viewer/blob/main/zrc/audit-log-viewer/demo-fixtures.edn).

## AuditEvent shapes

This repo contains the set of `AuditEvent` resource samples. Each sample is based on the public example or created from scratch. In the latter case, the form of the event is validated with the FHIR community.

## Clinical Data Types for Disclosures

Any requests to access data (including for viewing, display, import/export) that is tagged with any of the following attributes shall create a logs in the Audit Trail:

- Payment/Financial (45 CFR 170.210(d)) 
- Patient Confidential Information (UK 251(10) and (11) of the National Health Service Act 2006 
- Personal Identifiable Information – (UK GDPR) (EU GDPR)

The event must include
- Date/Time
- Patient Identification
- User Identification
- Description of the disclosure

## Significant System Event Auditing

- [User fails to login](samples/login-failure.md)
- [Successful USER login](samples/login-success.md)
- [User logoff](samples/logout-success.md)

- SERVICE events (including changes to configuration)
  - [Software configuration was updated](samples/software-configuration-updated.md)

- Failed attempts to access SYSTEM resources (files, folders, databases, services, etc.)

- SECURITY profile changes (permissions, group membership, password)
  - Changes to USER privileges

- Actions that require administrative authority (running privileged commands, running commands as another user, start/stop services, etc.)

- Begin transferring DICOM instances (export)
  - QIDO request/response
  - WADO request/response
  - STOW request/response

- Remote control sessions (session establishment, login, logout, end session, etc.)
  - [Remote session starts](samples/remote-login-success.md)
  - [Remote session end](samples/remote-logout-success.md)


## Clinical Data Activity Auditing

A Clinical Audit Event shall be created whenever any of the following activities take place on Protected Patient Data or Electronic Health Information:
- Creation
- Deletion
- Modification
- Storage

These Clinical Audit Events shall include, at least, the following information:
- Data and time of event log creation (or access request)
- Date and time of the event taking place
- Link to the identity of the patient
- Identity of the individual responsible for the event
- Type of action (for example: creations, additions, deletions, changes, queries, accesses, copy, print, and copy and paste)
- Type of event being created, or identification of requesting application





