# Logout success

Based on the [example logout](http://build.fhir.org/audit-event-example-logout.html).

```yaml
id: example-login-success
resourceType: AuditEventR5

occuredDateTime: '2022-01-01T23:21:23Z'

recorded: '2023-02-10T11:22:33Z'

action: E

category:
- coding:
  - code: '110114'
    system: 'http://dicom.nema.org/resources/ontology/DCM'
    display: User Authentication

code:
  coding:
  - code: '110123'
    system: 'http://dicom.nema.org/resources/ontology/DCM'
    display: Logout

outcome:
  code: 
    code: '0'
    system: 'http://terminology.hl7.org/CodeSystem/audit-event-outcome'
    display: Success

source:
  type:
  - coding:
    - code: '6'
      system: 'http://terminology.hl7.org/CodeSystem/security-source-type'
      display: 'Security Server'
  observer:
    display: Keycloak
    identifier:
      value: keycloak.example.com ????

agent:
# user should be a person
- who:
    reference: '#person'
  requestor: true
  type:
    coding:
    - code: 'humanuser'
      system: 'http://terminology.hl7.org/CodeSystem/extra-security-role-type'
      display: 'human user'

# User agent
- who:
    reference: '#user-agent'
  requestor: false
  networkUri: '<IP Address>'

# IDP
- who:
    reference: '#idp'
  requestor: false
  networkUri: ... # IP address in the internal network

contained:
- id: 'person'
  resourceType: 'Person'
- id: 'user-agent'
  resourceType: 'Device'
  displayName: '<USER_AGENT>'
- id: 'idp'
  resourceType: 'Device'
```
