# Login success

Questions:
- will this event describe only user login? or clients also?

Based on the [example login](http://build.fhir.org/audit-event-example-login.html).

<img width="841" alt="Screenshot 2023-02-17 at 16 35 17" src="https://user-images.githubusercontent.com/1931520/219697684-3bdaeecd-615f-4363-8edd-2e8f1b2b46ac.png">

```yaml
id: example-logout-success
resourceType: AuditEventR5

occuredDateTime: '2022-01-01T23:31:23Z'

recorded: '2023-02-10T11:22:33Z'

action: E

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

agent:
# user should be a person
- who:
    reference: "Practitioner/doctor"
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
- id: 'user-agent'
  resourceType: 'Device'
  displayName: '<USER_AGENT>'
- id: 'idp'
  resourceType: 'Device'
```
