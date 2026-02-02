# Security

The projects published in Github based on `VOTING Stimmunterlagen Online` are made available as part of a public Bug Bounty program.

## Code of Conduct

This project uses the [Code of Conduct](./CODE_OF_CONDUCT.md) to define expected conduct in our community.

Instances of abusive, harassing, or otherwise unacceptable behavior may be reported by contacting a project maintainer at psirt-voting@abraxas.ch

## Bug Bounty Policy

### Overview

The Bug Bounty Program is part of the Program as defined in the [Code of Conduct](./CODE_OF_CONDUCT.md) available on GitHub.
This Bug Bounty Policy (also called Security Policy) complements the [Code of Conduct](./CODE_OF_CONDUCT.md) with Bug Bounty specific rules and regulations.
The System subject to the Program including this Bug Bounty Program has the Abraxas product name `VOTING Stimmunterlagen Online`. The product `VOTING Stimmunterlagen Online` and its infrastructure include for example:

- `VOTING Stimmunterlagen Online - Service` (Backend)
- `VOTING Stimmunterlagen Online - WebApp` (Frontend)

We will from time to time as considered necessary issue an updated version of this Bug Bounty Policy.

### Program Rules

The rules and regulations established in the [Code of Conduct](./CODE_OF_CONDUCT.md) and this Bug Bounty Policy are binding for this Bug Bounty Program.

#### Legal Safe Harbor

Abraxas values a constructive and fair collaboration with the participants of the Program. Abraxas will not take legal actions against participants in this Bug Bounty Program, as long as participants act in good faith and in accordance with the license agreement, this Bug Bounty Policy, the provisions of the [Code of Conduct](./CODE_OF_CONDUCT.md) and the applicable laws. Under these conditions:

- We interpret activities by participants within this Program as authorized access under the Swiss Penal Code. This includes Swiss Penal Code paragraphs 143, 143bis and 144bis.
- We will not file a complaint against participants within this Program for trying to circumvent the security measures deployed in order to protect the services in-scope for this Program.
- If legal action is initiated by a third party against a participant within this Program, we will take reasonable measures supporting the participant to defend the claim of the third party.

Any non-compliance with the [license agreement](./CODE_OF_CONDUCT.md#license-source-code-permitted-use), [Code of Conduct](./CODE_OF_CONDUCT.md), this Bug Bounty Policy, and the applicable laws may result in exclusion from the Program and legal prosecution. For minor breaches, a warning may be issued. For severe breaches, Abraxas reserves all rights provided by applicable laws.

#### Basic Principles

All activities leading to the discovery of a vulnerability:

- are within the scope permitted by law (see section Legal Safe Harbor);
- are within the Program;
- may result in a bounty to be paid to you. The amount of compensation is based on the criticality of the vulnerability and the quality of the documentation submitted to Abraxas;
- shall not destroy, interrupt or lower the services and products used by Abraxas (and its customers and partners);
- shall respect the intellectual property rights and other rights of Abraxas, its customers and third-parties;
- shall not result in third-party data to be spied on or disclosed.

#### Eligibility Bug Bounty Program

- This is a public Program – everyone can participate.
- We reserve the right to terminate the Program at any moment and not accept nor award any new vulnerability reports. This termination will be announced by Abraxas suitable means.
- You must avoid tests that could cause degradation or interruption of our service (refrain from using automated tools and limit yourself about requests per second).
- You must not leak, manipulate, or destroy any user data.
- Only test with user accounts that are under your control.
- You must not be a former or current employee of Abraxas, Bug Bounty Switzerland, one of its contractors or project participants within the last six months.
- Strictly follow a “report first” approach (in contrast to “exploit first”). All activities that are not absolutely necessary to identify a vulnerability should be omitted and permission asked to further exploit.
- Any vulnerability must be reported exclusively through the channel specified in the [Submission Guidelines (CoC)](./CODE_OF_CONDUCT.md#submission-guidelines).

#### Responsible Vulnerability Disclosure

Vulnerability disclosure is possible from the start of the public phase of the Program, respecting the “Responsible Vulnerability Disclosure” section in the [Code of Conduct](./CODE_OF_CONDUCT.md). Abraxas will communicate transparently about results and will credit researchers publicly, if agreed.

#### Reporting Requirements

Please ensure to report only findings with a real impact on security of the product `VOTING Stimmunterlagen Online` and report clear proof of concepts that demonstrate the scenario.

Please make sure to complete your report in accordance with the guidelines set forth in the [Submission Guidelines (CoC)](./CODE_OF_CONDUCT.md#submission-guidelines).

### Scope

|System|URL|Description|
|---|---|---|
|VOTING Stimmunterlagen Online|<https://bbt.vo.abraxas-apps.ch/stimmunterlagen/*>|UI|
|VOTING Stimmunterlagen Online|<https://bbt.vo.abraxas-apis.ch/abraxas.voting.stimmunterlagen.v1.services.*><br />https://bbt.vo.abraxas-apis.ch/stimmunterlagen/v1/*|API|
|IAM System (Login) |<https://pre.abraxas-vo.sec.abraxas-apps.ch/*><br /><https://pre.abraxas-vo.sec.abraxas-apis.ch/*>|UI & API|

Should you identify an interesting but out-of-scope target you can attribute to `VOTING Stimmunterlagen Online`, please report it and ask for permission to test it.

The source code included in the public Bug Bounty Program can be used for identification of exploitable/demonstrable vulnerabilities.

### Out-of-Scope and general information

- `VOTING IAM` administrator use cases such as identity (lifecycle) management are not in-scope. The available accounts (see below) do not have according permissions for administration use cases.

- The self-registration website to create test users is not a productive component of the system. It is only a helping system for you in order that you can log in the application. This component is out of scope.

### Account Access

No user accounts are required for the pentests. However, test users can be generated by the "self-registration form" for a more substantial result. To do so, register yourself on the [Bug Bounty Platform](https://www.bugbounty.ch/abraxas/) and follow the instructions described there.

Afterwards, the following users and roles will be made available to you:

#### Users

|User|Function|Tenant|Application(s)|role(s)|
|---|---|---|---|---|
|User 1|Cantonal Supervisor|Kanton A1 <br />(canton A1)|- VOTING Stimmunterlagen Online <br />- VOTING IAM|Wahlverwalter|
|User 2|Municipal Supervisor|Gemeinde A1 <br />(municipality A1)|- VOTING Stimmunterlagen Online <br />- VOTING IAM|Wahlverwalter|
|User 2|Municipal Supervisor|Gemeinde A2 <br />(municipality A2)|- VOTING Stimmunterlagen Online <br />- VOTING IAM|Wahlverwalter|
|User 3|Municipal Supervisor|Gemeinde A3 <br />(municipality A3)|- VOTING Stimmunterlagen Online <br />- VOTING IAM|Wahlverwalter|
|User 4|Order Manager|Abraxas Informatik AG|- VOTING Stimmunterlagen Online <br />- VOTING IAM|Auftragsmanager|

##### Role description

|Role|Description|
|---|---|
|Wahlverwalter|A user with the role `Wahlverwalter` is responsible for preparing the voting cards for the printing order. The preparation includes verifying political businesses, selecting the layout of the voting cards, defining the enclosures, importing the voting register, approving the good for printing, creating the print job and, if necessary, placing the order for reprinting.|
|Auftragsmanager|A user with the role `Auftragsmanager` is responsible for the voting card order management. The user is responsible for managing the printing orders for voting cards and enclosures as well as for generating the invoices for authorities.|

Please consult the additional documents in this repository for further information on roles and authorizations.

### Qualifying Vulnerabilities

Everything with a real impact on security of `VOTING Stimmunterlagen Online` – e.g.:

- Remote code execution (RCE)
- Local files access and manipulation (LFI, RFI, XXE, SSRF, XSPA)
- Code injections (HTML, JS, SQL, PHP, ...)
- Cross-Site Scripting (XSS)
- Cross-Site Requests Forgery (CSRF) with real security impact
- Session Management
- Identitification and authentication failures
- Insecure direct object references (IDOR)
- CORS with real security impact
- Broken access control: Horizontal and vertical privilege escalation
- Source code findings with a measurable and provable impact on the system and its users

### Non-Qualifying Vulnerabilities

- All attacks which can be considered denial of service, resource starvation or brute force attacks
- Social engineering
- Physical attacks on people, buildings and devices
- Issues that require physical access to a victim’s computer/device
- For source code findings: Code smell or missing best practices
- For system or infrastructure: Missing best practices or other guidelines which do not indicate a security issue.
- Testing for weak credentials of prepared test users in the system
- Known issues listed on [Exclusions](./Exclusions.pdf)
- "Self" XSS
- Missing cookie flags on non-sensitive cookies
- Missing "HTTP Host Header" XSS
- Clickjacking/UI redressing
- Stack traces or path disclosure unless they leak sensitive information
- Software version disclosure
- Presence of autocomplete attribute on web forms
- Lack of HTTP Strict Transport Security Header
- Missing security-related HTTP headers which do not lead directly to a vulnerability
- SSL/TLS best practices
- Mixed content warnings
- Logout and other instances of low-severity Cross-Site Request Forgery
- Vulnerabilities related to E-Mail server configuration
- Vulnerabilities affecting outdated browsers or platforms
- Reports from automated web vulnerability scanners that have not been validated by hand
- 0-day vulnerabilities in third-party components not maintained or controlled by Abraxas, including those for which a patch has only recently become available
- Any hypothetical flaw or best practices without exploitable POC
- Bypassing rate-limits or the non-existence of rate-limits
- Username / email enumeration
- Theoretical vulnerabilities derived solely from static code analysis without a working proof of exploit on the official test environment
- Exploits that rely on prior impersonation or unauthorized access to another user without an in-scope exploit chain

### Reward Grid

The Abraxas Bug Bounty Grid defines in which framework and methodology bounties can be defined. It is based on the CVSS Scoring Model. Please note that in a normal, productive setting `VOTING Stimmunterlagen Online` is not exposed to the Internet. For the Public Bug Bounty, the following static grid is used.

#### Bounties

|Scope|Low|Medium|High|Critical|
|---|---|---|---|---|
|1.	VOTING Stimmunterlagen Online Service (Backend)<br />2.	VOTING Stimmunterlagen Online WebApp (Frontend)|CHF 500|CHF 1'500|CHF 4'000|CHF 10'000|
|3. IAM System|CHF 500|CHF 1'500|CHF 4'000|CHF 10'000|

#### Scenarios

Additionally, there are specific scenarios for which Abraxas is prepared to offer special bounties. These bounties apply to all scopes and will be paid instead of the above CVSS based bounties (and not additional to them), if applicable.

|No.|Scenario|Examples|Bounty Range|
|---|---|---|---|
|1|The voting card set or invidivual voting cards can be manipulated which leads to a disruption of the ballot.<br /><br />Note: Manipulation of data within the source systems is excluded and cannot be claimed here. The manipulations must happen after exportation and verification from the source systems.| - The insertion of additional voting cards.<br />- The removal of valid generated voting cards.<br />- Changing the delivery address.<br />- Adjustments to the content of individual voting cards.<br />- Adding, removing or tampering of attachements<br />| CHF 10'000 - CHF 30'000|

Rewards are distributed at the discretion of Abraxas.

#### Eligibility Bounties

- You must be the first reporter of a vulnerability to be eligible for a bounty.
- The vulnerability must be a qualifying vulnerability or enter in one of the categories of the specific scenarios to be eligible for a bounty.
- In case of exploits on different endpoints, parameters or components caused by the same underlying weakness, we reserve the right to honor only the first report and reject the subsequent ones as 'Duplicate' or 'Informative' depending on the case.
- Claims related to the reporting of a vulnerability before, after or without actually reporting a vulnerability are not considered by Abraxas.
