Provides data enrichment for domains.
This integration was integrated and tested with version 1.0 of Whois
## Configure Whois on Demisto

1. Navigate to **Settings** > **Integrations** > **Servers & Services**.
2. Search for Whois.
3. Click **Add instance** to create and configure a new integration instance.

| **Parameter** | **Description** | **Required** |
| --- | --- | --- |
| with_error | Return Errors | False |
| proxy_url | Proxy URL. Supports socks4/socks5/http connect proxies (e.g. socks5h://host:1080) | False |
| Source Reliability | Reliability of the source providing the intelligence data. The default value is B - Usually reliable. | True |

4. Click **Test** to validate the URLs, token, and connection.
## Commands
You can execute these commands from the Demisto CLI, as part of an automation, or in a playbook.
After you successfully execute a command, a DBot message appears in the War Room with the command details.
### whois
***
Provides data enrichment for domains.


##### Base Command

`whois`
##### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| query | The domain to enrich. | Required | 


##### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| DBotScore.Score | string | The actual score. | 
| DBotScore.Indicator | string | The indicator that was tested. | 
| DBotScore.Type | string | The indicator type. | 
| DBotScore.Vendor | string | The vendor used to calculate the score. | 
| Domain.Name | string | The domain name. | 
| Domain.Whois.Name | string | The domain name. | 
| Domain.Whois.DomainStatus | string | The domain status. | 
| Domain.Whois.DNSSec | string | The domain name system security extension (DNSSEC). | 
| Domain.Whois.NameServers | string | The name servers. | 
| Domain.Whois.CreationDate | date | The date that the domain was created. | 
| Domain.Whois.UpdatedDate | date | The date that the domain was last updated. | 
| Domain.Whois.ExpirationDate | date | The date that the domain expires. | 
| Domain.Whois.Registrar.Name | string | The name of the registrar. | 
| Domain.Whois.Emails | string | The abuse emails. | 
| Domain.Whois.Registrar.AbuseEmail | string | The email address of the contact for reporting abuse. | 
| Domain.Whois.Registrant.name | string | The name of the registrant. | 
| Domain.Whois.Registrant.email | string | The email address of the registrant. | 
| Domain.Whois.Raw | string | The raw output. | 
| Domain.Whois.Administrator.country | string | The country of the domain administrator. | 
| Domain.Whois.Administrator.name | string | The name of domain administrator. | 
| Domain.Whois.Administrator.state | string | The state of domain administrator. | 
| Domain.Whois.Administrator.email | string | The email address of the domain administrator. | 
| Domain.Whois.Administrator.organization | string | The organization of the domain administrator. | 
| Domain.Whois.Administrator.postalcode | string | The postal code of the domain administrator | 
| Domain.Whois.Administrator.street | string | The street of the domain admin | 
| Domain.Whois.Administrator.phone | string | The phone number of the domain administrator. | 
| Domain.Whois.Administrator.city | string | The city of the domain administrator. | 
| Domain.Whois.TechAdmin.country | string | The country of tech administrator. | 
| Domain.Whois.TechAdmin.name | string | The name of tech administrator. | 
| Domain.Whois.TechAdmin.state | string | The state of tech administrator. | 
| Domain.Whois.TechAdmin.email | string | The email address of the tech administrator. | 
| Domain.Whois.TechAdmin.organization | string | The organization of the tech administrator. | 
| Domain.Whois.TechAdmin.postalcode | string | The postal code of the tech administrator. | 
| Domain.Whois.TechAdmin.street | string | The street of the tech administrator. | 
| Domain.Whois.TechAdmin.phone | string | The phone number of the tech administrator. | 
| Domain.Whois.TechAdmin.city | string | The city of the tech administrator. | 
| Domain.Whois.Registrant.country | string | The country of the registrant. | 
| Domain.Whois.Registrant.state | string | The state of the registrant. | 
| Domain.Whois.Registrant.organization | string | The organization of the registrant. | 
| Domain.Whois.Registrant.postalcode | string | The postal code of the registrant. | 
| Domain.Whois.Registrant.street | string | The street of the registrant. | 
| Domain.Whois.Registrant.phone | string | The phone number of the registrant. | 
| Domain.Whois.Registrant.city | string | The city of the registrant. | 
| Domain.Whois.ID | string | The ID of the domain. | 
| Domain.Whois.QueryStatus | string | The result of the command ("Success" or "Failed"). | 
| Domain.Whois.QueryValue | string | The query requested by the user. | 


##### Command Example
```!whois query=paloaltonetworks.com```

##### Context Example
```
{
    "DBotScore": {
        "Indicator": "paloaltonetworks.com",
        "Score": 0,
        "Type": "domain",
        "Vendor": "Whois"
    },
    "Domain": {
        "Admin": {
            "country": "US",
            "name": "Palo Alto Networks, Inc.",
            "state": "CA"
        },
        "CreationDate": "20-02-2005",
        "DomainStatus": [
            "clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)",
            "clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)",
            "clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)"
        ],
        "ExpirationDate": "20-02-2024",
        "Name": "paloaltonetworks.com",
        "NameServers": [
            "ns3.p23.dynect.net",
            "ns2.p23.dynect.net",
            "ns6.dnsmadeeasy.com",
            "ns1.p23.dynect.net",
            "ns4.p23.dynect.net",
            "ns7.dnsmadeeasy.com",
            "ns5.dnsmadeeasy.com"
        ],
        "Registrant": {
            "country": "US",
            "organization": "Palo Alto Networks, Inc.",
            "state": "CA"
        },
        "UpdatedDate": "01-09-2018",
        "WHOIS": {
            "Admin": {
                "country": "US",
                "name": "Palo Alto Networks, Inc.",
                "state": "CA"
            },
            "CreationDate": "20-02-2005",
            "DomainStatus": [
                "clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)",
                "clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)",
                "clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)"
            ],
            "ExpirationDate": "20-02-2024",
            "NameServers": [
                "ns3.p23.dynect.net",
                "ns2.p23.dynect.net",
                "ns6.dnsmadeeasy.com",
                "ns1.p23.dynect.net",
                "ns4.p23.dynect.net",
                "ns7.dnsmadeeasy.com",
                "ns5.dnsmadeeasy.com"
            ],
            "Registrar": [
                "MarkMonitor, Inc."
            ],
            "UpdatedDate": "01-09-2018"
        },
        "Whois": {
            "Administrator": {
                "country": "US",
                "name": "Palo Alto Networks, Inc.",
                "state": "CA"
            },
            "CreationDate": "20-02-2005",
            "DomainStatus": [
                "clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)",
                "clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)",
                "clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)"
            ],
            "Emails": [
                "abusecomplaints@markmonitor.com",
                "whoisrequest@markmonitor.com"
            ],
            "ExpirationDate": "20-02-2024",
            "ID": [
                "143300555_DOMAIN_COM-VRSN"
            ],
            "Name": "paloaltonetworks.com",
            "NameServers": [
                "ns3.p23.dynect.net",
                "ns2.p23.dynect.net",
                "ns6.dnsmadeeasy.com",
                "ns1.p23.dynect.net",
                "ns4.p23.dynect.net",
                "ns7.dnsmadeeasy.com",
                "ns5.dnsmadeeasy.com"
            ],
            "QueryStatus": "Success",
            "QueryValue": "paloaltonetworks.com",
            "Raw": [
                "Domain Name: paloaltonetworks.com\nRegistry Domain ID: 143300555_DOMAIN_COM-VRSN\nRegistrar WHOIS Server: whois.markmonitor.com\nRegistrar URL: http://www.markmonitor.com\nUpdated Date: 2018-09-01T04:00:27-0700\nCreation Date: 2005-02-20T18:42:10-0800\nRegistrar Registration Expiration Date: 2024-02-20T18:42:10-0800\nRegistrar: MarkMonitor, Inc.\nRegistrar IANA ID: 292\nRegistrar Abuse Contact Email: abusecomplaints@markmonitor.com\nRegistrar Abuse Contact Phone: +1.2083895770\nDomain Status: clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)\nDomain Status: clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)\nDomain Status: clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)\nRegistrant Organization: Palo Alto Networks, Inc.\nRegistrant State/Province: CA\nRegistrant Country: US\nRegistrant Email: Select Request Email Form at https://domains.markmonitor.com/whois/paloaltonetworks.com\nAdmin Organization: Palo Alto Networks, Inc.\nAdmin State/Province: CA\nAdmin Country: US\nAdmin Email: Select Request Email Form at https://domains.markmonitor.com/whois/paloaltonetworks.com\nTech Organization: Palo Alto Networks, Inc.\nTech State/Province: CA\nTech Country: US\nTech Email: Select Request Email Form at https://domains.markmonitor.com/whois/paloaltonetworks.com\nName Server: ns3.p23.dynect.net\nName Server: ns2.p23.dynect.net\nName Server: ns6.dnsmadeeasy.com\nName Server: ns1.p23.dynect.net\nName Server: ns4.p23.dynect.net\nName Server: ns7.dnsmadeeasy.com\nName Server: ns5.dnsmadeeasy.com\nDNSSEC: unsigned\nURL of the ICANN WHOIS Data Problem Reporting System: http://wdprs.internic.net/\n>>> Last update of WHOIS database: 2020-03-31T10:37:19-0700 <<<\n\nFor more information on WHOIS status codes, please visit:\n  https://www.icann.org/resources/pages/epp-status-codes\n\nIf you wish to contact this domain\u2019s Registrant, Administrative, or Technical\ncontact, and such email address is not visible above, you may do so via our web\nform, pursuant to ICANN\u2019s Temporary Specification. To verify that you are not a\nrobot, please enter your email address to receive a link to a page that\nfacilitates email communication with the relevant contact(s).\n\nWeb-based WHOIS:\n  https://domains.markmonitor.com/whois\n\nIf you have a legitimate interest in viewing the non-public WHOIS details, send\nyour request and the reasons for your request to whoisrequest@markmonitor.com\nand specify the domain name in the subject line. We will review that request and\nmay ask for supporting documentation and explanation.\n\nThe data in MarkMonitor\u2019s WHOIS database is provided for information purposes,\nand to assist persons in obtaining information about or related to a domain\nname\u2019s registration record. While MarkMonitor believes the data to be accurate,\nthe data is provided \"as is\" with no guarantee or warranties regarding its\naccuracy.\n\nBy submitting a WHOIS query, you agree that you will use this data only for\nlawful purposes and that, under no circumstances will you use this data to:\n  (1) allow, enable, or otherwise support the transmission by email, telephone,\nor facsimile of mass, unsolicited, commercial advertising, or spam; or\n  (2) enable high volume, automated, or electronic processes that send queries,\ndata, or email to MarkMonitor (or its systems) or the domain name contacts (or\nits systems).\n\nMarkMonitor reserves the right to modify these terms at any time.\n\nBy submitting this query, you agree to abide by this policy.\n\nMarkMonitor Domain Management(TM)\nProtecting companies and consumers in a digital world.\n\nVisit MarkMonitor at https://www.markmonitor.com\nContact us at +1.8007459229\nIn Europe, at +44.02032062220\n--\n",
                "   Domain Name: PALOALTONETWORKS.COM\n   Registry Domain ID: 143300555_DOMAIN_COM-VRSN\n   Registrar WHOIS Server: whois.markmonitor.com\n   Registrar URL: http://www.markmonitor.com\n   Updated Date: 2017-08-30T20:42:10Z\n   Creation Date: 2005-02-21T02:42:10Z\n   Registry Expiry Date: 2024-02-21T02:42:10Z\n   Registrar: MarkMonitor Inc.\n   Registrar IANA ID: 292\n   Registrar Abuse Contact Email: abusecomplaints@markmonitor.com\n   Registrar Abuse Contact Phone: +1.2083895740\n   Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited\n   Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited\n   Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited\n   Name Server: NS1.P23.DYNECT.NET\n   Name Server: NS2.P23.DYNECT.NET\n   Name Server: NS3.P23.DYNECT.NET\n   Name Server: NS4.P23.DYNECT.NET\n   Name Server: NS5.DNSMADEEASY.COM\n   Name Server: NS6.DNSMADEEASY.COM\n   Name Server: NS7.DNSMADEEASY.COM\n   DNSSEC: unsigned\n   URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/\n>>> Last update of whois database: 2020-03-31T17:45:45Z <<<\n\nFor more information on Whois status codes, please visit https://icann.org/epp\n\nNOTICE: The expiration date displayed in this record is the date the\nregistrar's sponsorship of the domain name registration in the registry is\ncurrently set to expire. This date does not necessarily reflect the expiration\ndate of the domain name registrant's agreement with the sponsoring\nregistrar.  Users may consult the sponsoring registrar's Whois database to\nview the registrar's reported date of expiration for this registration.\n\nTERMS OF USE: You are not authorized to access or query our Whois\ndatabase through the use of electronic processes that are high-volume and\nautomated except as reasonably necessary to register domain names or\nmodify existing registrations; the Data in VeriSign Global Registry\nServices' (\"VeriSign\") Whois database is provided by VeriSign for\ninformation purposes only, and to assist persons in obtaining information\nabout or related to a domain name registration record. VeriSign does not\nguarantee its accuracy. By submitting a Whois query, you agree to abide\nby the following terms of use: You agree that you may use this Data only\nfor lawful purposes and that under no circumstances will you use this Data\nto: (1) allow, enable, or otherwise support the transmission of mass\nunsolicited, commercial advertising or solicitations via e-mail, telephone,\nor facsimile; or (2) enable high volume, automated, electronic processes\nthat apply to VeriSign (or its computer systems). The compilation,\nrepackaging, dissemination or other use of this Data is expressly\nprohibited without the prior written consent of VeriSign. You agree not to\nuse electronic processes that are automated and high-volume to access or\nquery the Whois database except as reasonably necessary to register\ndomain names or modify existing registrations. VeriSign reserves the right\nto restrict your access to the Whois database in its sole discretion to ensure\noperational stability.  VeriSign may restrict or terminate your access to the\nWhois database for failure to abide by these terms of use. VeriSign\nreserves the right to modify these terms at any time.\n\nThe Registry database contains ONLY .COM, .NET, .EDU domains and\nRegistrars.\n"
            ],
            "Registrant": {
                "country": "US",
                "organization": "Palo Alto Networks, Inc.",
                "state": "CA"
            },
            "Registrar": {
                "Name": [
                    "MarkMonitor, Inc."
                ]
            },
            "TechAdmin": {
                "country": "US",
                "organization": "Palo Alto Networks, Inc.",
                "state": "CA"
            },
            "UpdatedDate": "01-09-2018",
            "Value": "paloaltonetworks.com"
        }
    }
}
```

##### Human Readable Output
### Whois results for paloaltonetworks.com
|Administrator|Creation Date|Domain Status|Emails|Expiration Date|ID|Name|NameServers|QueryStatus|Registrant|Registrar|Tech Admin|Updated Date|
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| country: US state: CA name: Palo Alto Networks, Inc. | 20-02-2005 | clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited),clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited), clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited) | abusecomplaints@markmonitor.com, whoisrequest@markmonitor.com | 20-02-2024 | 143300555_DOMAIN_COM-VRSN | paloaltonetworks.com | ns3.p23.dynect.net, ns2.p23.dynect.net, ns6.dnsmadeeasy.com, ns1.p23.dynect.net,ns4.p23.dynect.net, ns7.dnsmadeeasy.com, ns5.dnsmadeeasy.com | Success | organization: Palo Alto Networks, Inc. state: CA country: US | MarkMonitor, Inc. | organization: Palo Alto Networks, Inc. state: CA country: US | 01-09-2018 |


### domain
***
Provides data enrichment for domains.


##### Base Command

`domain`
##### Input

| **Argument Name** | **Description** | **Required** |
| --- | --- | --- |
| domain | The domain to enrich. | Required | 


##### Context Output

| **Path** | **Type** | **Description** |
| --- | --- | --- |
| DBotScore.Score | string | The actual score. | 
| DBotScore.Indicator | string | The indicator that was tested. | 
| DBotScore.Type | string | The indicator type. | 
| DBotScore.Vendor | string | The vendor used to calculate the score. | 
| Domain.Name | string | The domain name. | 
| Domain.Whois.Name | string | The domain name. | 
| Domain.Whois.DomainStatus | string | The domain status. | 
| Domain.Whois.DNSSec | string | The domain name system security extension (DNSSEC). | 
| Domain.Whois.NameServers | string | The name servers. | 
| Domain.Whois.CreationDate | date | The date that the domain was created. | 
| Domain.Whois.UpdatedDate | date | The date that the domain was last updated. | 
| Domain.Whois.ExpirationDate | date | The date that the domain expires. | 
| Domain.Whois.Registrar.Name | string | The name of the registrar. | 
| Domain.Whois.Emails | string | The abuse emails. | 
| Domain.Whois.Registrar.AbuseEmail | string | The email address of the contact for reporting abuse. | 
| Domain.Whois.Registrant.name | string | The name of the registrant. | 
| Domain.Whois.Registrant.email | string | The email address of the registrant. | 
| Domain.Whois.Raw | string | The raw output. | 
| Domain.Whois.Administrator.country | string | The country of the domain administrator. | 
| Domain.Whois.Administrator.name | string | The name of domain administrator. | 
| Domain.Whois.Administrator.state | string | The state of domain administrator. | 
| Domain.Whois.Administrator.email | string | The email address of the domain administrator. | 
| Domain.Whois.Administrator.organization | string | The organization of the domain administrator. | 
| Domain.Whois.Administrator.postalcode | string | The postal code of the domain administrator | 
| Domain.Whois.Administrator.street | string | The street of the domain admin | 
| Domain.Whois.Administrator.phone | string | The phone number of the domain administrator. | 
| Domain.Whois.Administrator.city | string | The city of the domain administrator. | 
| Domain.Whois.TechAdmin.country | string | The country of tech administrator. | 
| Domain.Whois.TechAdmin.name | string | The name of tech administrator. | 
| Domain.Whois.TechAdmin.state | string | The state of tech administrator. | 
| Domain.Whois.TechAdmin.email | string | The email address of the tech administrator. | 
| Domain.Whois.TechAdmin.organization | string | The organization of the tech administrator. | 
| Domain.Whois.TechAdmin.postalcode | string | The postal code of the tech administrator. | 
| Domain.Whois.TechAdmin.street | string | The street of the tech administrator. | 
| Domain.Whois.TechAdmin.phone | string | The phone number of the tech administrator. | 
| Domain.Whois.TechAdmin.city | string | The city of the tech administrator. | 
| Domain.Whois.Registrant.country | string | The country of the registrant. | 
| Domain.Whois.Registrant.state | string | The state of the registrant. | 
| Domain.Whois.Registrant.organization | string | The organization of the registrant. | 
| Domain.Whois.Registrant.postalcode | string | The postal code of the registrant. | 
| Domain.Whois.Registrant.street | string | The street of the registrant. | 
| Domain.Whois.Registrant.phone | string | The phone number of the registrant. | 
| Domain.Whois.Registrant.city | string | The city of the registrant. | 
| Domain.Whois.ID | string | The ID of the domain. | 
| Domain.Whois.QueryStatus | string | The result of the command ("Success" or "Failed"). | 


##### Command Example
```!domain domain=google.com```

##### Context Example
```
{
    "DBotScore": {
        "Indicator": "google.com",
        "Score": 0,
        "Type": "domain",
        "Vendor": "Whois"
    },
    "Domain": {
        "Admin": {
            "country": "US",
            "name": "Google LLC",
            "state": "CA"
        },
        "CreationDate": "15-09-1997",
        "DomainStatus": [
            "clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)",
            "clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)",
            "clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)",
            "serverUpdateProhibited (https://www.icann.org/epp#serverUpdateProhibited)",
            "serverTransferProhibited (https://www.icann.org/epp#serverTransferProhibited)",
            "serverDeleteProhibited (https://www.icann.org/epp#serverDeleteProhibited)"
        ],
        "ExpirationDate": "13-09-2028",
        "Name": "google.com",
        "NameServers": [
            "ns1.google.com",
            "ns2.google.com",
            "ns4.google.com",
            "ns3.google.com"
        ],
        "Registrant": {
            "country": "US",
            "organization": "Google LLC",
            "state": "CA"
        },
        "UpdatedDate": "09-09-2019",
        "WHOIS": {
            "Admin": {
                "country": "US",
                "name": "Google LLC",
                "state": "CA"
            },
            "CreationDate": "15-09-1997",
            "DomainStatus": [
                "clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)",
                "clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)",
                "clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)",
                "serverUpdateProhibited (https://www.icann.org/epp#serverUpdateProhibited)",
                "serverTransferProhibited (https://www.icann.org/epp#serverTransferProhibited)",
                "serverDeleteProhibited (https://www.icann.org/epp#serverDeleteProhibited)"
            ],
            "ExpirationDate": "13-09-2028",
            "NameServers": [
                "ns1.google.com",
                "ns2.google.com",
                "ns4.google.com",
                "ns3.google.com"
            ],
            "Registrar": [
                "MarkMonitor, Inc."
            ],
            "UpdatedDate": "09-09-2019"
        },
        "Whois": {
            "Administrator": {
                "country": "US",
                "name": "Google LLC",
                "state": "CA"
            },
            "CreationDate": "15-09-1997",
            "DomainStatus": [
                "clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)",
                "clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)",
                "clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)",
                "serverUpdateProhibited (https://www.icann.org/epp#serverUpdateProhibited)",
                "serverTransferProhibited (https://www.icann.org/epp#serverTransferProhibited)",
                "serverDeleteProhibited (https://www.icann.org/epp#serverDeleteProhibited)"
            ],
            "Emails": [
                "abusecomplaints@markmonitor.com",
                "whoisrequest@markmonitor.com"
            ],
            "ExpirationDate": "13-09-2028",
            "ID": [
                "2138514_DOMAIN_COM-VRSN"
            ],
            "Name": "google.com",
            "NameServers": [
                "ns1.google.com",
                "ns2.google.com",
                "ns4.google.com",
                "ns3.google.com"
            ],
            "QueryStatus": "Success",
            "QueryValue": null,
            "Raw": [
                "Domain Name: google.com\nRegistry Domain ID: 2138514_DOMAIN_COM-VRSN\nRegistrar WHOIS Server: whois.markmonitor.com\nRegistrar URL: http://www.markmonitor.com\nUpdated Date: 2019-09-09T08:39:04-0700\nCreation Date: 1997-09-15T00:00:00-0700\nRegistrar Registration Expiration Date: 2028-09-13T00:00:00-0700\nRegistrar: MarkMonitor, Inc.\nRegistrar IANA ID: 292\nRegistrar Abuse Contact Email: abusecomplaints@markmonitor.com\nRegistrar Abuse Contact Phone: +1.2083895770\nDomain Status: clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited)\nDomain Status: clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited)\nDomain Status: clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited)\nDomain Status: serverUpdateProhibited (https://www.icann.org/epp#serverUpdateProhibited)\nDomain Status: serverTransferProhibited (https://www.icann.org/epp#serverTransferProhibited)\nDomain Status: serverDeleteProhibited (https://www.icann.org/epp#serverDeleteProhibited)\nRegistrant Organization: Google LLC\nRegistrant State/Province: CA\nRegistrant Country: US\nRegistrant Email: Select Request Email Form at https://domains.markmonitor.com/whois/google.com\nAdmin Organization: Google LLC\nAdmin State/Province: CA\nAdmin Country: US\nAdmin Email: Select Request Email Form at https://domains.markmonitor.com/whois/google.com\nTech Organization: Google LLC\nTech State/Province: CA\nTech Country: US\nTech Email: Select Request Email Form at https://domains.markmonitor.com/whois/google.com\nName Server: ns1.google.com\nName Server: ns2.google.com\nName Server: ns4.google.com\nName Server: ns3.google.com\nDNSSEC: unsigned\nURL of the ICANN WHOIS Data Problem Reporting System: http://wdprs.internic.net/\n>>> Last update of WHOIS database: 2020-03-31T10:44:43-0700 <<<\n\nFor more information on WHOIS status codes, please visit:\n  https://www.icann.org/resources/pages/epp-status-codes\n\nIf you wish to contact this domain\u2019s Registrant, Administrative, or Technical\ncontact, and such email address is not visible above, you may do so via our web\nform, pursuant to ICANN\u2019s Temporary Specification. To verify that you are not a\nrobot, please enter your email address to receive a link to a page that\nfacilitates email communication with the relevant contact(s).\n\nWeb-based WHOIS:\n  https://domains.markmonitor.com/whois\n\nIf you have a legitimate interest in viewing the non-public WHOIS details, send\nyour request and the reasons for your request to whoisrequest@markmonitor.com\nand specify the domain name in the subject line. We will review that request and\nmay ask for supporting documentation and explanation.\n\nThe data in MarkMonitor\u2019s WHOIS database is provided for information purposes,\nand to assist persons in obtaining information about or related to a domain\nname\u2019s registration record. While MarkMonitor believes the data to be accurate,\nthe data is provided \"as is\" with no guarantee or warranties regarding its\naccuracy.\n\nBy submitting a WHOIS query, you agree that you will use this data only for\nlawful purposes and that, under no circumstances will you use this data to:\n  (1) allow, enable, or otherwise support the transmission by email, telephone,\nor facsimile of mass, unsolicited, commercial advertising, or spam; or\n  (2) enable high volume, automated, or electronic processes that send queries,\ndata, or email to MarkMonitor (or its systems) or the domain name contacts (or\nits systems).\n\nMarkMonitor reserves the right to modify these terms at any time.\n\nBy submitting this query, you agree to abide by this policy.\n\nMarkMonitor Domain Management(TM)\nProtecting companies and consumers in a digital world.\n\nVisit MarkMonitor at https://www.markmonitor.com\nContact us at +1.8007459229\nIn Europe, at +44.02032062220\n--\n",
                "   Domain Name: GOOGLE.COM\n   Registry Domain ID: 2138514_DOMAIN_COM-VRSN\n   Registrar WHOIS Server: whois.markmonitor.com\n   Registrar URL: http://www.markmonitor.com\n   Updated Date: 2019-09-09T15:39:04Z\n   Creation Date: 1997-09-15T04:00:00Z\n   Registry Expiry Date: 2028-09-14T04:00:00Z\n   Registrar: MarkMonitor Inc.\n   Registrar IANA ID: 292\n   Registrar Abuse Contact Email: abusecomplaints@markmonitor.com\n   Registrar Abuse Contact Phone: +1.2083895740\n   Domain Status: clientDeleteProhibited https://icann.org/epp#clientDeleteProhibited\n   Domain Status: clientTransferProhibited https://icann.org/epp#clientTransferProhibited\n   Domain Status: clientUpdateProhibited https://icann.org/epp#clientUpdateProhibited\n   Domain Status: serverDeleteProhibited https://icann.org/epp#serverDeleteProhibited\n   Domain Status: serverTransferProhibited https://icann.org/epp#serverTransferProhibited\n   Domain Status: serverUpdateProhibited https://icann.org/epp#serverUpdateProhibited\n   Name Server: NS1.GOOGLE.COM\n   Name Server: NS2.GOOGLE.COM\n   Name Server: NS3.GOOGLE.COM\n   Name Server: NS4.GOOGLE.COM\n   DNSSEC: unsigned\n   URL of the ICANN Whois Inaccuracy Complaint Form: https://www.icann.org/wicf/\n>>> Last update of whois database: 2020-03-31T17:45:45Z <<<\n\nFor more information on Whois status codes, please visit https://icann.org/epp\n\nNOTICE: The expiration date displayed in this record is the date the\nregistrar's sponsorship of the domain name registration in the registry is\ncurrently set to expire. This date does not necessarily reflect the expiration\ndate of the domain name registrant's agreement with the sponsoring\nregistrar.  Users may consult the sponsoring registrar's Whois database to\nview the registrar's reported date of expiration for this registration.\n\nTERMS OF USE: You are not authorized to access or query our Whois\ndatabase through the use of electronic processes that are high-volume and\nautomated except as reasonably necessary to register domain names or\nmodify existing registrations; the Data in VeriSign Global Registry\nServices' (\"VeriSign\") Whois database is provided by VeriSign for\ninformation purposes only, and to assist persons in obtaining information\nabout or related to a domain name registration record. VeriSign does not\nguarantee its accuracy. By submitting a Whois query, you agree to abide\nby the following terms of use: You agree that you may use this Data only\nfor lawful purposes and that under no circumstances will you use this Data\nto: (1) allow, enable, or otherwise support the transmission of mass\nunsolicited, commercial advertising or solicitations via e-mail, telephone,\nor facsimile; or (2) enable high volume, automated, electronic processes\nthat apply to VeriSign (or its computer systems). The compilation,\nrepackaging, dissemination or other use of this Data is expressly\nprohibited without the prior written consent of VeriSign. You agree not to\nuse electronic processes that are automated and high-volume to access or\nquery the Whois database except as reasonably necessary to register\ndomain names or modify existing registrations. VeriSign reserves the right\nto restrict your access to the Whois database in its sole discretion to ensure\noperational stability.  VeriSign may restrict or terminate your access to the\nWhois database for failure to abide by these terms of use. VeriSign\nreserves the right to modify these terms at any time.\n\nThe Registry database contains ONLY .COM, .NET, .EDU domains and\nRegistrars.\n"
            ],
            "Registrant": {
                "country": "US",
                "organization": "Google LLC",
                "state": "CA"
            },
            "Registrar": {
                "Name": [
                    "MarkMonitor, Inc."
                ]
            },
            "TechAdmin": {
                "country": "US",
                "organization": "Google LLC",
                "state": "CA"
            },
            "UpdatedDate": "09-09-2019",
            "Value": "google.com"
        }
    }
}
```

##### Human Readable Output
### Whois results for google.com
|Administrator|Creation Date|Domain Status|Emails|Expiration Date|ID|Name|NameServers|QueryStatus|Registrant|Registrar|Tech Admin|Updated Date|
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| country: US state: CA name: Google LLC | 15-09-1997 | clientUpdateProhibited (https://www.icann.org/epp#clientUpdateProhibited), clientTransferProhibited (https://www.icann.org/epp#clientTransferProhibited), clientDeleteProhibited (https://www.icann.org/epp#clientDeleteProhibited), serverUpdateProhibited (https://www.icann.org/epp#serverUpdateProhibited), serverTransferProhibited (https://www.icann.org/epp#serverTransferProhibited), serverDeleteProhibited (https://www.icann.org/epp#serverDeleteProhibited) | abusecomplaints@markmonitor.com, whoisrequest@markmonitor.com | 13-09-2028 | 2138514_DOMAIN_COM-VRSN | google.com | ns1.google.com, ns2.google.com, ns4.google.com, ns3.google.com | Success | organization: Google LLC state: CA country: US | MarkMonitor, Inc. | organization: Google LLC state: CA country: US | 09-09-2019 |

