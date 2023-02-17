# Software configuration updated

Base on the (example login)[http://build.fhir.org/audit-event-example-login.html].

```yaml
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
    identifier: {system: 'urn:oid:2.16.840.1.113883.4.2', value: 2.16.840.1.113883.4.2}
  type:
    coding:
    - {system: 'http://dicom.nema.org/resources/ontology/DCM', code: '110153', display: Source Role ID}
  requestor: false
  networkString: workstation1.example.com
id: example-service-event-software-configuration
code:
  coding:
  - {code: '110131', system: 'http://dicom.nema.org/resources/ontology/DCM', display: Software Configuration}
action: E
entity:
- what: {resourceType: Device, id: example-software-as-device}
```
