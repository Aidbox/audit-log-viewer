# Login failure

Base on the (example login)[http://build.fhir.org/audit-event-example-login.html].

```yaml
resourceType: AuditEventR5
id: example-login-failure
occuredDateTime: '2022-01-01T23:11:23Z'
action: E
recorded: '2023-02-10T11:22:33Z'
category:
- coding:
  - {code: '110114', system: 'http://dicom.nema.org/resources/ontology/DCM', display: User Authentication}
code:
  coding:
  - {code: '110122', system: 'http://dicom.nema.org/resources/ontology/DCM', display: Login}
outcome:
  code: {code: '4', system: 'http://terminology.hl7.org/CodeSystem/audit-event-outcome', display: Minor failure}
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
- who:
    identifier: {value: 2.16.840.1.113883.4.2, system: 'urn:oid:2.16.840.1.113883.4.2'}
  requestor: false
  networkString: workstation1.example.com
```
