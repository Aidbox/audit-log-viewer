# Remote login success

Base on the (example login)[http://build.fhir.org/audit-event-example-login.html].

```yaml
category:
- coding:
  - {code: '110139', system: 'http://dicom.nema.org/resources/ontology/DCM', display: Remote Service Operation Started}
  - {code: '110114', system: 'http://dicom.nema.org/resources/ontology/DCM', display: User Authentication}
occuredDateTime: '2022-01-01T23:31:23Z'
outcome:
  code: {code: '0', system: 'http://terminology.hl7.org/CodeSystem/audit-event-outcome', display: Success}
resourceType: AuditEventR5
source:
  type:
  - coding:
    - {code: '4', system: 'http://terminology.hl7.org/CodeSystem/security-source-type', display: Application Server}
  observer:
    display: Cloud
    identifier: {value: cloud.example.com}
recorded: '2023-02-10T11:22:33Z'
agent:
- who:
    display: Grahame Grieve
    identifier: {value: '95'}
  type:
    coding:
    - {code: humanuser, system: 'http://terminology.hl7.org/CodeSystem/extra-security-role-type', display: human user}
  requestor: true
- who:
    identifier: {value: 2.16.840.1.113883.4.2, system: 'urn:oid:2.16.840.1.113883.4.2'}
  requestor: false
  networkString: workstation1.example.com
id: example-remote-login-success
code:
  coding:
  - {code: '110122', system: 'http://dicom.nema.org/resources/ontology/DCM', display: Login}
action: E
```
