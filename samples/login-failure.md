# Login failure

Base on the [example login](http://build.fhir.org/audit-event-example-login.html).

```yaml
id: example-login-failure
resourceType: AuditEventR5

occuredDateTime: '2022-01-01T23:11:23Z'

action: E # Execute

recorded: '2023-02-10T11:22:33Z' # recordred by IDP

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
    display: 'User Authentication'
code:
  coding:
  - code: '110122'
    system: 'http://dicom.nema.org/resources/ontology/DCM'
    display: 'Login'

outcome:
  code:
    code: '4'
    system: 'http://terminology.hl7.org/CodeSystem/audit-event-outcome'
    display: 'Minor failure'
  detail:
  - text: "Wrong credentials"

agent:
# we suppose this is a wrong place to store link to the User
- who:
    display: '<USERNAME>'
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
  ...
```
