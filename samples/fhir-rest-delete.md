# FHIR REST Delete

Questions:


```yaml
id: example-fhir-rest-delete
resourceType: AuditEventR5

occuredDateTime: '2022-01-01T23:11:23Z'

action: D # Delete

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
  - code: delete
    system: http://hl7.org/fhir/restful-interaction
    display: delete

outcome:
  code:
    code: 'success'
    system: 'http://hl7.org/fhir/issue-severity'
    display: 'Operation Successful'
  detail:
  - text: Resource deleted
    coding:
    - code: MSG_DELETED_DONE
      system: http://terminology.hl7.org/CodeSystem/operation-outcome
      display: Resource deleted

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
  query: ... # in case of conditional delete?
```
