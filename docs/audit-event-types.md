# AuditEvent types

https://build.fhir.org/valueset-audit-event-sub-type.html


# User login/logout

# Client login/logout



What is the difference between Authorization Decision and Access Control Decision?


Authorization Decision

110144


https://dicom.nema.org/medical/dicom/current/output/chtml/part16/chapter_D.html#DCM_110144


https://dicom.nema.org/medical/dicom/current/output/chtml/part16/chapter_D.html#DCM_110147



Security Layer and Access Control says Misha Kulakov

How do we authorize access to Aidbox?

Access Policy mechanism.

Eng creates access policy resource. He authorizes any client to perform specific actions.

AccessPolicy are being appled to any incoming request. It's called access control.

We may authorize via ACL. Engineer writes zen config, so he authorized access with more configuration. 

Smart on FHIR scenario. Patient/Practiitoner may authorize client to get access to specific data. This is an authorization decision.
