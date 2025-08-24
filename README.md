In modern SAP development, the RESTful Application Programming Model (RAP) offers a powerful framework for building scalable, maintainable, and service-oriented applications. One of its standout features is Deep Insert, which allows the creation of a root entity along with its associated child entities in a single transactional request.

This blog walks through a real-world implementation of Deep Insert using RAP to create Business Process Exception Management (BPEM) cases via the standard BAPI BAPI_EMMA_CASE_CREATE.

Payload:
--batch

Content-Type: application/http
Content-Transfer-Encoding: binary

POST BPEMHeader HTTP/1.1

Content-Type: application/json
{
"CCAT": "4",
"MAINOBJTYPE": "Value",
"bpem_objects_flag": true,
"bpem_case_text_flag": true,
"bpem_message_flag": true,
"_BPEMCaseText": [
{
"TDLINE": "td1"
},
{
"TDLINE": "td2"
}
],
"_BPEMObject": [
{
"CELEMNAME": "gjh1",
"REFOBJTYPE": "sf1"
},
{
"CELEMNAME": "gjh2",
"REFOBJTYPE": "sf2"
}
],
"_BPEMMessages": [
{
"MSGID": "000",
"MSGNO": "001"
},
{
"MSGID": "001",
"MSGNO": "000"
}
]
}

--batch--

Output
<img width="1351" height="693" alt="SAP Gateway" src="https://github.com/user-attachments/assets/07000011-2732-4edf-b106-171951d74fad" />

<!---
bhaskarnagula/bhaskarnagula is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
