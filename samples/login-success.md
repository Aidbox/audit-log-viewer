# Logout success

Base on the (example login)[http://build.fhir.org/audit-event-example-login.html].

```yaml
resourceType: AuditEventR5
id: example-logout-success
occuredDateTime: '2022-01-01T23:31:23Z'
recorded: '2023-02-10T11:22:33Z'
action: E
category:
- coding:
  - {code: '110114', system: 'http://dicom.nema.org/resources/ontology/DCM', display: User Authentication}
code:
  coding:
  - {code: '110123', system: 'http://dicom.nema.org/resources/ontology/DCM', display: Logout}
outcome:
  code: {code: '0', system: 'http://terminology.hl7.org/CodeSystem/audit-event-outcome', display: Success}
source:
  type:
  - coding:
    - {code: '3', system: 'http://terminology.hl7.org/CodeSystem/security-source-type', display: Web Server}
  observer:
    display: Cloud
    identifier: {value: hl7connect.healthintersections.com.au}
agent:
- who:
    display: Grahame Grieve
    identifier: {value: '95'}
  type:
    coding:
    - {code: humanuser, system: 'http://terminology.hl7.org/CodeSystem/extra-security-role-type', display: human user}
  requestor: true
  networkString: 127.0.0.1
- who:
    identifier: {value: 2.16.840.1.113883.4.2, system: 'urn:oid:2.16.840.1.113883.4.2'}
  requestor: false
  networkString: Workstation1.ehr.familyclinic.com
```
