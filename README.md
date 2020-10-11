# pynrds
pynrds will eventually be a complete Python library for the NAR NRDS API Service.

Watch this space! I'm working through prototyping calls and data structures with code coming soon. 

Short-term goal is to create a test set of simulated data.


### Update 10/10/20: 
Created and uploaded `get_member.py` which returns a `JSON` package of randomized member data in the same format as the NRDS API `/member/` endpoint. Tackled the easy elements first, this script will not generate simulated data for Certifications, Designations, etc (yet!) but the other information looks realistic enough for testing purposes. Ages, DOB, years of membership, NRDS insert dates, and all other info are random, but follow some rules to make the data realistic. The script's dependencies are all in the import section, notably `Delorean` and `Numpy`, as well as two different fake-data libraries: `mimesis` and `faker`, with `mimesis` doing the bulk of the work. The outputted addresses are a bit European in flavor, specifically British, but close enough. 

Once I complete simulated data templates for all the NRDS endpoints I can create a stand-in API that will return realistic but fake NRDS-like data and let us quickly mock up queries and build realistic applications that can be expected to work with "real" NRDS data. Eventually, we'll create a whole fake Association's worth of NRDS records and store it so we can interact with it exactly like the NRDS API. There are some clues to the theme in the code...

Example output below:

```json
{
    "Member": {
        "AssociationId": "8128",
        "DirectoryOptOut": "N",
        "DuesWaivedLocalFlag": "N",
        "DuesWaivedNationalFlag": "N",
        "DuesWaivedStateFlag": "N",
        "Email": "cyprus1941@protonmail.com",
        "JoinedDate": "06-17-2003",
        "JunkMailFlag": "Y",
        "MLSID": "1159",
        "MemberArbitrationEthicsPending": "N",
        "MemberBirthDate": "12-28-1957",
        "MemberCellPhone": {
            "PhoneArea": 939,
            "PhoneNumber": 6675368
        },
        "MemberDesignatedRealtor": "N",
        "MemberFirstName": "Rey",
        "MemberGender": "M",
        "MemberGeneration": "",
        "MemberHomeAddress": {
            "City": "North Haverbrook",
            "Country": "US",
            "State": "OR",
            "Street1": "1233 Lloyd Hill NW",
            "Street2": "Apt 222",
            "Zip": "91307",
            "Zip6": "5623"
        },
        "MemberHomePhone": {
            "PhoneArea": 939,
            "PhoneNumber": 3484539
        },
        "MemberId": "812821839",
        "MemberLastName": "Chase",
        "MemberLocalJoinedDate": "06-17-2003",
        "MemberMLSAssociationId": "95885",
        "MemberMailAddress": {
            "City": "Shelbyville",
            "Country": "US",
            "State": "OR",
            "Street1": "1286 Ver Mehr Parade East",
            "Street2": "Unit 572",
            "Zip": "07437",
            "Zip6": "6131"
        },
        "MemberMiddleName": "",
        "MemberNRDSInsertDate": "06-17-2003",
        "MemberNationalDuesPaidDate": "12-24-2019",
        "MemberNickname": "",
        "MemberOccupationName": "Video Artist",
        "MemberOfficeVoiceExtension": "7942",
        "MemberOnlineStatus": "Y",
        "MemberOnlineStatusDate": "",
        "MemberOrientationDate": "07-18-2003",
        "MemberPager": {
            "PhoneArea": 939,
            "PhoneNumber": 1933587
        },
        "MemberPersonalFax": {
            "PhoneArea": 939,
            "PhoneNumber": 3481112
        },
        "MemberPreferredFax": "O",
        "MemberPreferredMail": "M",
        "MemberPreferredPhone": "C",
        "MemberPreferredPublication": "M",
        "MemberPrimaryStateAssociationId": "0862",
        "MemberRELicense": "BO578204",
        "MemberReinstatementCode": "",
        "MemberReinstatementDate": "",
        "MemberSalutation": "",
        "MemberStateDuesPaidDate": "12-24-2019",
        "MemberStatus": "A",
        "MemberStatusDate": "",
        "MemberSubclass": "R",
        "MemberTitle": "",
        "MemberType": "R",
        "OfficeId": "8128",
        "OnRosterFlag": "Y",
        "PointOfEntry": "070008128",
        "PreviousNonMemberFlag": "N",
        "PrimaryIndicator": "P",
        "StopEMailFlag": "N",
        "StopFaxFlag": "N",
        "StopMailFlag": "N",
        "Timestamp": 95636675,
        "WebPage": "https://prerefine.com"
    }
}
```

And another:

```json
{
    "Member": {
        "AssociationId": "8128",
        "DirectoryOptOut": "N",
        "DuesWaivedLocalFlag": "N",
        "DuesWaivedNationalFlag": "N",
        "DuesWaivedStateFlag": "N",
        "Email": "bengalic2065@live.com",
        "JoinedDate": "09-18-1996",
        "JunkMailFlag": "Y",
        "MLSID": "9163",
        "MemberArbitrationEthicsPending": "N",
        "MemberBirthDate": "08-03-1963",
        "MemberCellPhone": {
            "PhoneArea": 636,
            "PhoneNumber": 5434389
        },
        "MemberDesignatedRealtor": "N",
        "MemberFirstName": "Rhett",
        "MemberGender": "M",
        "MemberGeneration": "",
        "MemberHomeAddress": {
            "City": "Springfield",
            "Country": "US",
            "State": "OR",
            "Street1": "1309 Keystone Glen",
            "Street2": "",
            "Zip": "04548",
            "Zip6": "7866"
        },
        "MemberHomePhone": {
            "PhoneArea": 939,
            "PhoneNumber": 3266853
        },
        "MemberId": "812822337",
        "MemberLastName": "Slater",
        "MemberLocalJoinedDate": "09-18-1996",
        "MemberMLSAssociationId": "54291",
        "MemberMailAddress": {
            "City": "Springfield",
            "Country": "US",
            "State": "OR",
            "Street1": "556 Emma Highway East",
            "Street2": "Suite 35",
            "Zip": "29503",
            "Zip6": "6225"
        },
        "MemberMiddleName": "",
        "MemberNRDSInsertDate": "09-18-1996",
        "MemberNationalDuesPaidDate": "09-22-2019",
        "MemberNickname": "",
        "MemberOccupationName": "Machine Minder",
        "MemberOfficeVoiceExtension": "7021",
        "MemberOnlineStatus": "Y",
        "MemberOnlineStatusDate": "",
        "MemberOrientationDate": "11-13-1996",
        "MemberPager": {
            "PhoneArea": 636,
            "PhoneNumber": 7498798
        },
        "MemberPersonalFax": {
            "PhoneArea": 636,
            "PhoneNumber": 4646479
        },
        "MemberPreferredFax": "C",
        "MemberPreferredMail": "M",
        "MemberPreferredPhone": "H",
        "MemberPreferredPublication": "M",
        "MemberPrimaryStateAssociationId": "0862",
        "MemberRELicense": "SL644727",
        "MemberReinstatementCode": "",
        "MemberReinstatementDate": "",
        "MemberSalutation": "",
        "MemberStateDuesPaidDate": "09-22-2019",
        "MemberStatus": "A",
        "MemberStatusDate": "",
        "MemberSubclass": "R",
        "MemberTitle": "",
        "MemberType": "R",
        "OfficeId": "8128",
        "OnRosterFlag": "Y",
        "PointOfEntry": "070008128",
        "PreviousNonMemberFlag": "N",
        "PrimaryIndicator": "P",
        "StopEMailFlag": "Y",
        "StopFaxFlag": "N",
        "StopMailFlag": "N",
        "Timestamp": 13035656,
        "WebPage": "https://retepora.org"
    }
}
```
