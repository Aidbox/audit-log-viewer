# FHIR REST Create

Questions:
- What source type of FHIR Server? Application, Web or Database Server?
- AuditEvent.agent.who.network. What should be set there? Is IP address from internet ok?
- AuditEvent.entity.agent. is it convenient to link here FHIR Server where reseource was saved?



- GET /Encounter?_revinclude=target:Provenance How many AuditEvent resources should be created?

- How secure is client? is it just one who can use https?

- > A smartphone app is an example of a Secure Application that has control over the security for the application, but not the rest of the mobile device software or hardware security. https://profiles.ihe.net/ITI/TF/Volume1/ch-9.html#9.1.1.2
  May web application be a secure app in terms of BALP?
  > The Secure Application does not have complete control over the full stack from hardware to user interface and external communications. It only has security services control over the actors with which it is grouped.



```yaml
id: example-fhir-rest-create
resourceType: AuditEventR5

occuredDateTime: '2022-01-01T23:11:23Z'

action: C # Create

recorded: '2023-02-10T11:22:33Z' # recordred by FHIR Server

source:
  type:
  - coding:
    - code: '4'
      system: 'http://terminology.hl7.org/CodeSystem/security-source-type'
      display: 'Application Server'
  # We suppose FHIR Server generates audit event itself
  observer:
    display: Aidbox
    type: Device

category:
- coding:
  - code: 'rest'
    system: 'http://terminology.hl7.org/CodeSystem/audit-event-type'
    display: 'RESTful Operation'
code:
  coding:
  - code: 'create'
    system: 'http://hl7.org/fhir/restful-interaction'
    display: 'create'

outcome:
  code:
    code: 'success'
    system: 'http://hl7.org/fhir/issue-severity'
    display: 'Operation Successful'
  detail:
  - text: New resource created
    coding:
    - code: MSG_CREATED
      system: http://terminology.hl7.org/CodeSystem/operation-outcome
      display: New resource created

agent:
# User interacts via browser
  - who:
      reference: Practitioner/pract # Patient/pt
      display: '<USERNAME>'
    requestor: true
    type:
      coding:
      - code: 'humanuser'
        system: 'http://terminology.hl7.org/CodeSystem/extra-security-role-type'
        display: 'human user'
  
  # User agent
  - who:
      resource: 
        id: 'user-agent'
        resourceType: 'Device'
        displayName: '<USER_AGENT>'
    requestor: false
    networkUri: '<IP Address>' # of client
    type:
      coding:
      - code: "110150" 
        system: http://dicom.nema.org/resources/ontology/DCM
        display: Application

# Or Client
  - who:
      reference: "Device/client" 
    requestor: true
    type:
      coding:
      - code: "110150" 
        system: http://dicom.nema.org/resources/ontology/DCM
        display: Application


# and FHIR Server
  - who:
      type: Device
      display: Aidbox
    requestor: false
    networkUri: ... # IP address of Aidbox in external network. Or Aidbox base url
    
    
patient: Patient/patient # if there is one
encounter: Encounter/encounter # if there is one

entity:
- what:
    reference: "ResourceType/resource"
    role:
      code: "4"
      system: http://terminology.hl7.org/CodeSystem/object-role
      display: Domain Resource
  query: ... # in case of conditional create
```
