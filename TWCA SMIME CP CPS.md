# TAIWAN-CA INC. S/MIME Certification Authority Certificate Policy and Certification Practice Statement (TWCA S/MIME CP/CPS)

**(Version 1.0)**

Effective Date: 2026/10/31

## Document History

| Version | Effective Date | Revision Description |
| --- | --- | --- |
| 1.0 | 2026/10/31 | Initial release. The S/MIME portions were extracted from TWCA-CP V2.6 and TWCA GLOBAL CPS V1.9 and consolidated into this newly compiled document. | 

Table of Contents

## Summary

The key items of the TAIWAN-CA INC. S/MIME Certification Authority Certificate Policy and Certification Practice Statement are described as follows: 

### Issued Certificates

The types and applicable scopes of the certificates issued by this Certification Center in accordance with this Statement are described as follows:

#### Certificate Types and Applicable Scope

| Certificate Type | Applicable Scope |
|-----------------|-----------------|
| S/MIME Certificate | Used to protect email communication security. Through organization validation, it confirms that the subject identified in the certificate has control over the Mailbox Address it asserts, and provides digital signature and encryption capabilities for email, ensuring the authenticity of the message origin and the integrity of its content. It is applicable to email applications of enterprises, organizations, or government entities. |

**Note:**

- Certificate usage scope is detailed in "[1.4 Certificate Usage](#14-certificate-usage)."
- Certificates referred to in this Statement are certificates that contain the `emailProtection` (OID: 1.3.6.1.5.5.7.3.4) EKU. Certificates MUST have a subjectAltName (hereinafter referred to as SAN) extension, and the SAN extension MUST contain at least one `rfc822Name` Mailbox Address.
- According to the BR definition, certificates contain multiple types. This Certification Center only issues Organization-validated certificates, which include multipurpose and strict profiles.

### Important Legal Liability Matters

- If a Subscriber encounters grounds for certificate revocation (such as Private Key data leakage or loss), the Subscriber must immediately notify this Certification Center and carry out the certificate revocation procedures. However, the Subscriber shall still bear the risks and responsibilities arising from the use of that certificate before the certificate revocation status has been published.
- This Certification Center shall not be liable for damages arising from processing Subscriber registration data and certificate issuance, unless it has failed to follow this Statement, has violated applicable laws, or the damage is attributable to its intentional act or negligence.
- This Certification Center shall not be liable for damages to Subscribers caused by force majeure events (such as earthquakes) or other causes not attributable to this Certification Center (such as war).
- If this Certification Center fails to properly safeguard Subscriber registration and certificate-related data, resulting in leakage, misuse, tampering, or unauthorized use of such information that causes damage to third parties, this Certification Center shall be liable for damages.
- After receiving a certificate revocation request, this Certification Center shall publish the revocation no later than the time limit specified in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate), and shall issue the Certificate Revocation List (CRL) and publish it in the Repository at the frequency specified in [Section 4.9.7](#497-crl-issuance-frequency). Before the CRL is published, the Subscriber shall take appropriate actions to minimize the impact on Relying Parties and shall bear all liabilities arising from the use of that certificate. For revocation operation specifications, please refer to [Section 4.9](#49-certificate-revocation-and-suspension).
- In the event of a damage compensation dispute between this Certification Center and a Subscriber arising from certificate issuance or use, the liability of both parties shall be limited to the scope defined by relevant laws and regulations and the contract.
- By accepting and using a certificate issued by this Certification Center, a Relying Party acknowledges and agrees to the legal liability terms of this Certification Center and relies on that certificate within the scope specified in this Statement.

### Other Important Matters

- When there are concerns that the Subscriber's Private Key has been lost or compromised, or when Subscriber-related information has changed, the Subscriber must notify this Certification Center in accordance with the relevant operating procedures.
- Subscribers shall properly generate, safeguard, and use Private Keys, and comply with the restrictions on the use of keys and certificates.
- When applying for certificates, Subscribers must provide accurate and correct information. When accepting certificates issued by this Certification Center, Subscribers must verify the correctness of the certificate content and confirm that the Public Key and Private Key are a matching key pair.
- When verifying certificates, Relying Parties shall use the self-signed certificate of the Root Certification Authority to verify the digital signature of the Subordinate Certification Authority certificate, and use the Subordinate Certification Authority certificate to verify whether the digital signature of the Subscriber Certificate was signed by the Subordinate Certification Authority's Private Key, and verify through the Certificate Revocation List or OCSP whether the certificate status has been revoked.
- When using the Certificate Revocation List issued by this Certification Center, Relying Parties shall first verify the digital signature to confirm whether the Certificate Revocation List is valid.
- The Company obtained the ISO 27001 Information Security Management System certificate in September 2007, has maintained its validity continuously, and completed the transition to ISO 27001:2022 in June 2024.
- The Company obtained the BS 10012 Personal Information Management System certificate in November 2013. The transition to BS 10012:2017 was completed in July 2018, and the ISO/IEC 27701 Privacy Information Management System certificate was obtained on July 6, 2020; both remain valid to the present.
- The Company obtained the ISO 20000-1 IT Service Management System certificate in December 2020, maintaining validity to the present.
- The Company obtained the ISO 22301 Business Continuity Management System certificate in November 2021, maintaining validity to the present.
- This Certification Center conducts internal audits at least once per quarter and commissions an accounting firm to conduct at least one external audit per year to ensure that its operations comply with the Certification Practice Statement and Certificate Policy. For detailed audit operation specifications, please refer to [Chapter 8](#8-compliance-audit-and-other-assessments).

# 1 INTRODUCTION

## 1.1 Overview

TAIWAN-CA INC. (hereinafter referred to as "the Company" or "TWCA") was jointly established with investment from Taiwan Stock Exchange Corporation (TWSE), Taiwan Depository & Clearing Corporation (TDCC), Financial Information Service Co., Ltd. (FISC), and HiTRUST Inc.

The TAIWAN-CA INC. S/MIME Certification Authority Certificate Policy and Certification Practice Statement (hereinafter referred to as "this Statement") is a combined Certificate Policy (CP) and Certification Practice Statement (CPS) description, established in compliance with the "Required Items for Digital Signature Certification Practice Statements" promulgated by the competent authority under the Electronic Signatures Act. Its primary purpose is to describe how the TAIWAN-CA INC. S/MIME Certification Authority (hereinafter referred to as "this Certification Center") carries out certificate issuance and management operations.

In addition to domestic laws and regulations, in order to ensure the global trustworthiness of the certificates it issues and to maintain network communication security and user trust, this Certification Center expressly declares its compliance with the latest requirements of the following international standards and browser root certificate policies: 

- **CA/Browser Forum (hereinafter referred to as CABF)**: the requirements of the latest version of the [Baseline Requirements for the Issuance and Management of Publicly-Trusted S/MIME Certificates](https://cabforum.org/working-groups/smime/requirements/) (hereinafter referred to as BR) established by the CABF, which is published at https://cabforum.org/.
- **Browser Policies**: Including but not limited to the latest requirements of the [Mozilla Root Store Policy](https://www.mozilla.org/en-US/about/governance/policies/security-group/certs/policy/), [Apple Root Program](https://github.com/apple/apple-root-program/blob/main/policy.md), and [Microsoft Trusted Root Program](https://github.com/TrustedRootProgram/Program-Requirements/blob/main/Requirements.md) (covering email/S/MIME trust).
- **CCADB Policy**: Complies with the [Common CA Database (hereinafter referred to as CCADB) Policy](https://www.ccadb.org/policy) co-maintained by multiple browser vendors.

To ensure that email is not easily forged, tampered with, or stolen during transmission, and to reliably authenticate Mailbox Addresses and their associated Legal Entities or organizations for identification by Relying Parties, TWCA has established a Public Key Infrastructure (TWCA Public Key Infrastructure; TWCA PKI, hereinafter referred to as "this Infrastructure") and has set up a Trust Anchor Root Certification Authority (Root Certification Authority; RCA), which issues certificates to Subordinate Certification Authorities, which in turn issue certificates to Subscribers.

## 1.2 Document name and identification

The name of this Statement is "TAIWAN-CA INC. S/MIME Certification Authority Certificate Policy and Certification Practice Statement". For the certificate policy identifiers used by this Certification Center, please refer to [Section 7.1.6](#716-certificate-policy-object-identifier).

### 1.2.1 Revisions

This Statement complies with and conforms to the [BR](https://cabforum.org/working-groups/smime/requirements/). This Certification Center reviews the above standards and updates this Statement at least once every 365 days, incrementing the version number and adding a dated changelog entry, even if no other changes are made. In addition, if any inconsistency is found between this Statement and the above standards or domestic laws, this Certification Center will make amendments, or raise objections to CABF as appropriate. For the history of version changes, please refer to the "Document History" section of this Statement.

## 1.3 PKI participants

This Certification Center includes the following members:

- Certification Authority (CA)
- Registration Authority (RA)
- Subscriber
- Relying Party
- Policy Management Authority (PMA)

The Certification Authority is divided by hierarchy and purpose into the "Root Certification Authority" (Root CA, abbreviated as RCA) and the "Subordinate Certification Authority" (Subordinate CA), collectively referred to as "this Certification Center."

This Statement will describe in [Chapter 3](#3-identification-and-authentication) and [Chapter 4](#4-certificate-life-cycle-operational-requirements) how this Certification Center conducts Subscriber Certificate issuance and management operations, and how Subscribers and Relying Parties apply for and use certificates; [Chapter 5](#5-facility-management-and-operational-controls) describes the management guidelines for the Root Certification Authority and the Subordinate Certification Authority.

### 1.3.1 Certification authorities

#### 1.3.1.1 Root Certification Authority

The Root Certification Authority is the top-level certification management organization and serves as the Trust Anchor of this Infrastructure. It is operated and managed by the Company and is primarily responsible for the following:

- Issuance and management of Subordinate Certification Authority certificates; it shall not issue Subscriber Certificates.
- Management and publication of Subordinate Certification Authority certificates and Certificate Revocation Lists (CRL) in the Repository.
- Provision of Online Certificate Status Protocol (OCSP) services.
- Maintaining the stability and operation of the Repository.
- It is deployed in an independent, security-controlled operating environment, where two or more authorized personnel jointly carry out the generation and deployment of Subordinate Certification Authority certificates, which are signed with the Root CA Private Key. The RCA certificate is a self-signed certificate. When a new certificate is generated or re-keyed, it is published in the repository of this Certification Center (https://www.twca.com.tw/repository).

#### 1.3.1.2 Subordinate Certification Authority

The Subordinate Certification Authority is operated and managed by the Company and is primarily responsible for the following:

- Issuance and management of Subscriber Certificates.
- Management and publication of Subscriber Certificates and Subscriber Certificate Revocation Lists (CRL) in the Repository.
- Provision of Online Certificate Status Protocol (OCSP) services.
- Maintaining the stability and operation of the Repository.

#### 1.3.1.3 Policy Management Authority

The TAIWAN-CA INC. Policy Management Authority (PMA) is an organization established within the Company and is responsible for formulating the following:

- Certificate Policy and Certification Practice Statement (CP/CPS).
- Operational standards.

### 1.3.2 Registration authorities

The Registration Authority (RA) is primarily responsible for verifying the identity of applicants (Subscribers) and the related information required for certificate issuance, to serve as the basis for this Certification Center to issue Subscriber Certificates.

This Certification Center establishes its own Registration Authority and does not delegate it to a third party.

#### 1.3.2.1 Enterprise registration authorities

This Certification Center does not delegate the verification of Certificate Requests to an Enterprise Registration Authority (Enterprise RA), and does not accept a Certificate Request authorized by an Enterprise RA.

Every Certificate Request is verified by the Registration Authority of this Certification Center. Validation of mailbox authorization or control is performed by this Certification Center in accordance with [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control), and verification of Organization identity is performed by this Certification Center in accordance with [Section 3.2.3](#323-authentication-of-organization-identity). This Certification Center does not accept an Applicant organization's own verification result, internal records, or attestation as a substitute for either.

Because no verification function is delegated, the acceptance conditions that the [BR](https://cabforum.org/working-groups/smime/requirements/#1321-enterprise-registration-authorities) impose on Certificate Requests authorized by an Enterprise RA, and the associated contractual limitation and monitoring obligations, do not arise for this Certification Center. See also [Section 8.8](#88-review-of-delegated-parties). Should this Certification Center decide to delegate to an Enterprise RA, this Statement will be amended in accordance with [Section 9.12](#912-amendments) before any such delegation takes effect.

### 1.3.3 Subscribers

A Subscriber is the entity recorded in the certificate Subject name, who holds the Private Key corresponding to the Public Key in the certificate.

Subscribers of this Certification Center are Legal Entities or organizations that apply for certificates.

### 1.3.4 Relying parties

A Relying Party is an entity that uses the Public Key in the certificate issued by this Certification Center to verify the validity of the digital signature messages of Subscriber Certificates issued by this Certification Center.

Relying Parties use the identity information recorded in Subscriber Certificates to identify the identity information of the Subscriber.

Relying Parties shall use the information recorded in the certificates issued by this Certification Center to determine whether to rely on the certificate or whether it can be used for a specific purpose.

### 1.3.5 Other participants

No stipulation.

## 1.4 Certificate usage

### 1.4.1 Appropriate certificate uses

The primary goal of the certificates issued by this Certification Center is to provide a framework of “reasonable assurance” to senders and recipients of email messages that the Subject identified in a Certificate has control of the domain or Mailbox Address being asserted. A variation of this use case is where the Subscriber organization digitally signs email to establish its authenticity and source of origin. This Statement describes an integrated set of technologies, protocols, identity-proofing, lifecycle management, and auditing requirements for the issuance and management of Publicly-Trusted Certificates. It also serves to inform users and help them to make informed decisions when relying on Certificates.

The EKU extension field of S/MIME Subscriber Certificates issued by this Certification Center contains only the following combinations of usages, where each usage is represented by its corresponding Object Identifier (OID):

1. **Secure Email** (Trust Purpose as defined in Appendix A of the Apple Root Program Policy): Singly contains the Extended Key Usage `id-kp-emailProtection` (OID: 1.3.6.1.5.5.7.3.4).
2. **Legacy S/MIME** (Trust Purpose as defined in Appendix A of the Apple Root Program Policy): Simultaneously contains the Extended Key Usages `id-kp-emailProtection` (OID: 1.3.6.1.5.5.7.3.4) and `id-kp-clientAuth` (OID: 1.3.6.1.5.5.7.3.2).

The Trust Purposes designated for the certificate hierarchy governed by this Statement are accordingly **Secure Email** and **Legacy S/MIME**, which the Apple Root Program Policy permits a single CP/CPS document to combine. This Statement designates no other Trust Purpose. This Certification Center incorporates and commits to compliance with the Baseline Requirements applicable to those Trust Purposes, namely the [BR](https://cabforum.org/working-groups/smime/requirements/).

The Extended Key Usage requirements for the Subordinate CA certificates of this hierarchy are stated in [Section 7.1.2.2](#7122-subordinate-ca-certificates).

The certificate profiles comply with BR. If a Subscriber has entered into a contract with the Company that separately specifies the certificate usage scope, transaction limits, and compensation limits, such agreement shall prevail.

### 1.4.2 Prohibited Certificate Uses

Certificates issued by this Certification Center, other than for the uses specified in [Section 1.4.1](#141-appropriate-certificate-uses), are prohibited from being used for the following purposes:

- Eavesdropping on or intercepting third-party communications.
- Uses that cause bodily harm, death, or psychological injury.
- Applications or businesses that pose significant harm to social order and public interest.
- Applications or businesses explicitly prohibited or excluded by the Electronic Signatures Act, other relevant laws and regulations, or the competent authorities of the respective industries.

## 1.5 Policy administration

### 1.5.1 Organization Administering the Document

The authority for the formulation, revision, and publication of this Statement rests with the PMA.

### 1.5.2 Contact Person

For any questions regarding this Statement, or for related security incident reports (such as concerns about Key Compromise or certificate mis-issuance), please provide detailed information and contact details through the following contact:

| Item | Details |
|------|---------|
| Company Name | TAIWAN-CA INC. (TWCA) |
| Contact Person | Customer Service Center |
| Address | 10th Floor, 85, Yen-Ping South Road, Zhongzheng District (100), Taipei, Taiwan, R.O.C. |
| Telephone | 886-2-23708886 |
| Email | ca@twca.com.tw |

To report a Key Compromise, certificate misuse, impersonation, fraud, or other inappropriate conduct, please send an email to ca@twca.com.tw; this Certification Center accepts such reports 24 x 7. A report of Key Compromise shall include proof as described in [Section 4.9.12](#4912-special-requirements-re-key-compromise).

### 1.5.3 Person determining CPS suitability for the policy

The Certification Practice Statement established by this Certification Center shall be approved by the PMA.

### 1.5.4 CPS approval procedures

In accordance with the Electronic Signatures Act, the Certification Practice Statement established by this Certification Center must be approved by the competent authority before this Statement may be published and certificate issuance services may be provided.

## 1.6 Definitions and acronyms

Refer to [Appendix I](#appendix-i-glossary) and [Appendix II](#appendix-ii-acronyms-and-abbreviations).

Where a section of this Statement states "No stipulation", it means that this Statement imposes no requirements related to that section, as that term is used in [RFC 3647](https://datatracker.ietf.org/doc/html/rfc3647). Where a section states "Not applicable", it means that the subject matter of that section does not arise given the operational model of this Certification Center.


# 2 PUBLICATION AND REPOSITORY RESPONSIBILITIES

## 2.1 Repositories

The Repository of this Certification Center provides querying or downloading of certificates, Certificate Revocation Lists (CRL), Certificate Policy and Certification Practice Statement, and other certificate operation-related information. It also provides Online Certificate Status Protocol (OCSP) services.

The Repository URL is: https://www.twca.com.tw/repository

The Repository addresses for CRL and OCSP are specified in certificate extension fields. For detailed information, please refer to [Chapter 7](#7-certificate-crl-and-ocsp-profiles).

## 2.2 Publication of certification information

The information published by this Certification Center includes the following:

- Previous versions of this Statement.
- Certificates and related information of this Certification Center.
- Issued certificates.
- CRL.
- OCSP services.
- Historical audit reports.
- Organization Registration Agency List (see [Section 3.2.3](#323-authentication-of-organization-identity)).

## 2.3 Time or frequency of publication

This Statement, upon completion of revisions and approval by the Policy Management Authority (PMA), will be submitted to the competent authority for approval. This Certification Center shall publish it in the Repository within 7 working days of receiving the approval document.

Certificates of this Certification Center, once issued, together with the certificate chain and related certificate information, shall be published in the Repository within 7 working days for querying by Subscribers or Relying Parties. The CRL issuance frequency is in accordance with the provisions of [Section 4.9.7](#497-crl-issuance-frequency).

This Certification Center reviews and updates this Statement at least every 365 days, incrementing the version number and adding a dated entry to the "Document History" section, even if no other change is made to the document.

## 2.4 Access controls on repositories

The Repository is made publicly available in read-only mode for querying by Subscribers or Relying Parties. However, to prevent malicious attacks or tampering, access controls are enforced when updating Repository information or when traffic is abnormal.
# 3 IDENTIFICATION AND AUTHENTICATION

## 3.1 Naming

### 3.1.1 Types of names

Certificates issued by this Certification Center, including CA Certificates and Subscriber Certificates, use Subject Distinguished Names (Subject DN) and Issuer Distinguished Names (Issuer DN) that comply with X.500 Distinguished Name (DN) naming conventions. The attributes and contents of these names comply with the relevant provisions of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) and [BR](https://cabforum.org/working-groups/smime/requirements/).
### 3.1.2 Need for names to be meaningful

The subject distinguished name recorded in the Subscriber Certificate shall comply with the naming requirements of relevant laws and regulations, must be sufficient to identify a specific Legal Entity or organization, and must be identifiable by Relying Parties.

### 3.1.3 Anonymity or pseudonymity of subscribers

This Statement does not allow Subscribers to use anonymous names, pseudonyms, aliases, or pen names.

### 3.1.4 Rules for interpreting various name forms

The interpretation rules for the name forms recorded in certificates are defined in accordance with ITU-T X.520 name attribute definitions.

### 3.1.5 Uniqueness of names

This Certification Center shall verify the uniqueness of Subscribers' Chinese and English names, Mailbox Addresses (the domain name part after the "@" symbol shall belong to the same Legal Entity or organization), and Legal Entity or organization distinguished names. The same domain name may not be used by different Legal Entities or organizations; however, multiple certificates for the same domain name or Mailbox Address may be issued to the same Legal Entity or organization.

When Subscriber Certificates have identical unique distinguished names, this Certification Center gives priority to the Subscriber who first registered and passed the organization identity and domain validation. If a later Applicant completes identity verification before the earlier Applicant, the later Applicant may be given priority.

In the event of a dispute regarding the use of a distinguished name, if a competent authority/institution confirms through legitimate documentation that the name belongs to another Applicant, this Certification Center shall revoke the registered Subscriber's right to use the unique distinguished name, revoke the issued certificate, and the Subscriber shall bear the relevant legal liability.

### 3.1.6 Recognition, authentication, and role of trademarks

This Certification Center respects the registered trademarks of Subscribers' Chinese and English names. After verification, this Certification Center accepts the Subscriber's use of such Chinese and English names but does not guarantee the approval, verification, or uniqueness of the Subscriber's registered trademark. In the event of a trademark dispute, the Subscriber shall resolve it through legal channels on their own.

## 3.2 Initial identity validation

The purpose of initial identity validation is to prevent fraudulent applications and to confirm the authenticity of the identity information provided by the Applicant. To this end, the Registration Authority (RA) shall adhere to the following principles when performing identity validation:
- Complete authenticity verification, validation verification, and linkage verification of the collected identity documentation, with the verification strength matching the requirements of this Statement and BR.
- If the Applicant entrusts an agent to handle the application, a verifiable authorization mechanism must be in place to complete the agent's identity and authorization verification.
- The final recorded identity information must be confirmed by the Applicant to ensure that the information to be recorded is consistent with what the Applicant submitted and is the Applicant's correct information.

This Certification Center only issues Organization-validated certificates. Initial validation includes the following procedures:
1. Validation of mailbox authorization or control: Perform mailbox validation in accordance with [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control) (validating authority over mailbox via domain, or validating control over mailbox via email).
2. Organization identity validation: Perform organization identity validation in accordance with [Section 3.2.3](#323-authentication-of-organization-identity) to confirm its legal existence and identity information.

### 3.2.1 Method to prove possession of private key

The Public Key contained in the certificate and the corresponding Private Key shall be generated by the Subscriber. The Subscriber shall provide a PKCS#10 certificate signing request signed with the Private Key and submit it to this Certification Center as proof of possession of the Private Key. This Certification Center shall use the Subscriber's Public Key to verify the Subscriber's signature on the PKCS#10 certificate signing request to confirm that the Subscriber is the owner of the Private Key, that the Public Key and Private Key form a key pair, and the integrity of the Subscriber's identity information.

### 3.2.2 Validation of mailbox authorization or control

Validation of mailbox authorization or control must be performed. The validation method is "validating authority over mailbox via domain" or "validating control over mailbox via email" to confirm that the certificate Applicant has authority over or control of the Mailbox Address. For every domain or Mailbox Address in issued certificates, the Validation Record states the validation method used, including the relevant version number of the BR or the TLS Baseline Requirements on which that method is based.

The validity period of validation data shall comply with the following requirements:
- Validating authority over mailbox via domain: The period from completion of validation to certificate issuance shall not exceed 398 days.
- Validating control over mailbox via email: The period from completion of validation to certificate issuance shall not exceed 30 days.
- Validation of organization identity and authority: The period from completion of validation to certificate issuance shall not exceed 825 days.

#### 3.2.2.1 Validating authority over mailbox via domain

This Certification Center validates the Applicant's domain name (the domain portion after the "@" in the Mailbox Address) in accordance with [BR Section 3.2.2.1](https://cabforum.org/working-groups/smime/requirements/#3221-validating-authority-over-mailbox-via-domain). That section incorporates the domain validation methods defined in TLS BR Section 3.2.2.4; this Certification Center uses at least one of the following:

| Validation Method Name (Applicable TLS BR Section) | Description |
|---|---|
| **Email to a Constructed Address** ([TLS BR 3.2.2.4.4](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32244-email-to-a-constructed-address)) | This Certification Center sends an email containing a unique Random Value with a 30-day validity period to the designated recipient. This Certification Center then verifies the Random Value. The recipient email address is limited to: admin, administrator, webmaster, hostmaster, or postmaster, followed by "@" and the domain name to be validated. **Restrictions and requirements:** This Certification Center will not use this validation method after March 15, 2028. |
| **DNS Change Validation** ([TLS BR 3.2.2.4.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32247-dns-change)) | The Applicant creates a CNAME, TXT, or CAA resource record in the DNS service of the domain to be validated, naming it with the domain name to be validated or a label prefixed with an underscore character placed before the domain name to be validated, and places therein a Random Value provided by this Certification Center and unique to the certificate request. This Certification Center then verifies the record. The Random Value is valid for 30 days from its creation. **Restrictions and requirements:** This Certification Center implements Multi-Perspective Issuance Corroboration (MPIC) for this validation method; see [Section 4.2.2.2](#4222-multi-perspective-issuance-corroboration). |
| **Website Change Validation** ([TLS BR 3.2.2.4.18](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322418-agreed-upon-change-to-website-v2)) | The Applicant places a Random Value provided by this Certification Center and unique to the certificate request in the specified website directory of the domain to be validated: "/.well-known/pki-validation". This Certification Center then initiates an HTTP request to verify. The Random Value is valid for 30 days from its creation. The HTTP response status code must indicate success (2xx). If redirected, only HTTP-layer redirects are permitted (HTTP response status codes limited to: 301, 302, 307, or 308), and the redirected URL must use the HTTP/HTTPS protocol on an authorized port. **Restrictions and requirements:** This Certification Center implements Multi-Perspective Issuance Corroboration (MPIC) for this validation method; see [Section 4.2.2.2](#4222-multi-perspective-issuance-corroboration). |

This Certification Center uses only the three validation methods listed in the table above. This Certification Center does not provide an Automated Certificate Management Environment (ACME, as defined in [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555)) service, and does not assign ACME account identifiers (`accounturi`).

In accordance with [SBR Section 3.2.2](https://cabforum.org/working-groups/smime/requirements/#322-validation-of-mailbox-authorization-or-control), all Validation Records of this Certification Center include the applied Fully Qualified Domain Name (FQDN), the validation method used, the Authorization Domain Name for which verification was completed, and the TLS BR version followed. Of the validation methods above, Email to a Constructed Address (TLS BR Section 3.2.2.4.4) and DNS Change Validation (TLS BR Section 3.2.2.4.7) may prune domain labels as permitted by TLS BR Section 3.2.2.4, using the Public Suffix List to determine the Base Domain Name as the limit of pruning; Website Change Validation (TLS BR Section 3.2.2.4.18) does not prune.

When performing the domain validation, this Certification Center's Primary Network Perspective DNS resolver used for querying DNS records must establish a validation chain to the IANA DNSSEC root trust anchor and perform DNSSEC validation.

#### 3.2.2.2 Validating control over mailbox via email

This Certification Center sends a Random Value via email to a designated recipient, and then this Certification Center verifies the Random Value. This verification method satisfies the following requirements:
- The recipient is the one specified in the Subject Alternative Name (SAN) of the certificate.
- The Random Value has a validity period of 24 hours.
- The entropy of the Random Value is at least 112 bits.
- The Random Value shall not be reused.

#### 3.2.2.3 Validating applicant as operator of associated mail server(s)

Not applicable. This Certification Center does not use the validation method set out in [BR Section 3.2.2.3](https://cabforum.org/working-groups/smime/requirements/#3223-validating-applicant-as-operator-of-associated-mail-servers) (establishing control over a mailbox on the basis that the Applicant operates the mail server(s) associated with that Mailbox Address).

#### 3.2.2.4 Validating control over mailbox using ACME extensions

Not applicable. This Certification Center does not provide an ACME service and therefore does not use the ACME extension validation method set out in [BR Section 3.2.2.4](https://cabforum.org/working-groups/smime/requirements/#3224-validating-control-over-mailbox-using-acme-extensions). See [Section 3.2.2.1](#3221-validating-authority-over-mailbox-via-domain).

### 3.2.3 Authentication of organization identity

This Certification Center and the Registration Authority verify the identity of the Organization Applicant to confirm its legal existence, full legal name, address, Jurisdiction of Incorporation or registration, and registration identifier. The verification methods are as follows:

1. **Verification of Name, Address, and Identifier**: This Certification Center or the Registration Authority MUST verify the full legal name, address, and registration identifier of the Organization Applicant using documentation provided by, or through communication with, a government agency in the jurisdiction of the Legal Entity’s creation, existence, or recognition; the government agencies used and their inquiry channels are recorded in the "Organization Registration Agency List" (see [Section 3.2.8](#328-reliability-of-verification-sources)). Where the Applicant is a government agency, this Certification Center confirms that the agency actually exists and verifies its agency name using an inquiry channel recorded in that List.

   For identity verification documentation (including physical paper copies or scanned electronic files) provided by Applicants, Validation Specialists must perform validation checks to verify that the documents are not falsified or altered (checking for physical or digital edit artifacts). Additionally, these documents must be cross-checked against government databases of competent authorities to confirm their authenticity.

2. **Status Verification**: In the course of the above verification, this Certification Center also confirms that the Legal Entity's status as recorded by the registration agency is "approved and established" or another operating status; where the entity is recorded as dissolved, revoked, withdrawn, suspended, or closed, the certificate is not issued. Where the Applicant is a government agency, this Certification Center confirms that it is still found in the inquiry above; if the agency cannot be found, the certificate is not issued.

Organization verification is performed through the government agency channels recorded in the "Organization Registration Agency List" to verify organization registration data and status; a channel not recorded in that List is not used. The "Organization Registration Agency List" used by this Certification Center is disclosed in the repository on the home page of the official website, and its sources are all official data of government agencies.

In addition to Organization verification, a "validation of mailbox authorization or control" must be performed to confirm that the Certificate Applicant has authority over or control of the Mailbox Address. Specific methods are described in [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control).

**Disclosure of pseudonyms**: this Certification Center does not issue certificates containing a Pseudonym. As provided in [Section 3.1.3](#313-anonymity-or-pseudonymity-of-subscribers), this Statement does not permit Subscribers to use anonymity, pseudonyms, aliases, or pen names; the Subject Distinguished Name of a Subscriber Certificate does not contain the `pseudonym` attribute (see Note 2 to [Section 7.1.4.2.2](#71422-subject-distinguished-name-fields)).

### 3.2.4 Authentication of individual identity

Not applicable (this Certification Center does not issue Sponsor-validated or Individual-validated certificates).

### 3.2.5 Non-verified subscriber information

This Certification Center shall verify all Subscriber information.

### 3.2.6 Validation of authority

This Certification Center establishes and executes a written Applicant Representative verification and management process to verify the authority and approval of an Applicant Representative to request certificate issuance or revocation, or to assign responsibilities to others to act in those roles. This Certification Center does not verify authority to act as an Enterprise RA, because it does not accept Certificate Requests authorized by an Enterprise RA (see [Section 1.3.2.1](#1321-enterprise-registration-authorities)). This process allows Applicants to specify the individuals who may act as Applicant Representatives on an ongoing basis in electronic or secure written form, and this Certification Center restricts certificate operations only to those individuals on the list. If a request is received from an individual outside this specification, it must be rejected. Upon verified written request from the organization Applicant, this Certification Center must provide the Applicant with the current list of its authorized Applicant Representatives.

Before commencing to issue Organization-validated Certificates for an Applicant, this Certification Center or the Registration Authority (RA) MUST use a Reliable Method of Communication to verify the authority and approval of the Applicant Representative. A Reliable Method of Communication means a postal address, telephone number, or email address that has been verified, through a source other than the Applicant Representative, as belonging to the Applicant organization; contact information supplied solely by the Applicant Representative within the application documents is not used as a Reliable Method of Communication.

Provided that a Reliable Method of Communication is used, this Certification Center may establish the authenticity of the certificate request directly with the Applicant Representative, or with an authoritative source within the Applicant's organization, such as the Applicant's main business offices, corporate offices, human resource offices, information technology offices, or other department that this Certification Center deems appropriate.

### 3.2.7 Criteria for interoperation

This Certification Center publicly discloses every Cross Certificate that identifies a Certification Authority of this Certification Center as the Subject, where this Certification Center arranged for or accepted the establishment of the trust relationship concerned. Disclosure is made in the CCADB, and the disclosed information identifies the Subject certificate, the Issuing CA, and the certificate's validity period.

This Certification Center discloses each Subordinate CA certificate it issues in the CCADB within 7 calendar days of issuance and before that Subordinate CA begins issuing certificates, and updates that disclosure within 7 calendar days after the Subordinate CA certificate is revoked (per Section 3.2 of the [CCADB Policy](https://www.ccadb.org/policy)).

Where this Certification Center issues a Cross Certificate to another Certification Authority, that Certification Authority is subject to the same requirements as a Subordinate Certification Authority under this Statement, and the certificate is issued in accordance with [Section 7.1.2.2](#7122-subordinate-ca-certificates).

This Certification Center does not establish interoperation with any Certification Authority outside the scope of this Statement other than by a Cross Certificate disclosed as described above.

### 3.2.8 Reliability of verification sources

The information sources used by this Certification Center under [Section 3.2.3](#323-authentication-of-organization-identity) are official data maintained by government agencies and delivered over HTTPS, each of which is a government agency within the meaning of item 1 of [BR Section 3.2.3.2.1](https://cabforum.org/working-groups/smime/requirements/#32321-verification-of-name-address-and-identifier). The name, URL, and permitted uses of each source are disclosed, in accordance with [BR Section 3.2.3.3](https://cabforum.org/working-groups/smime/requirements/#3233-disclosure-of-verification-sources), in the "Organization Registration Agency List", which is disclosed in the repository on the home page of the official website and is updated whenever an information source is added, changed, or discontinued.

Before adding an information source, this Certification Center confirms that its provider is the government agency responsible for the registration concerned, that the data is kept current by that agency, and that the access channel protects transmission integrity. Where this Certification Center determines that an information source is no longer reliable or accurate, it ceases to use that source and re-evaluates the validations previously completed using it; where such validations are determined to be unreliable, it revokes the affected certificates in accordance with [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate).

## 3.3 Identification and authentication for re-key requests

### 3.3.1 Identification and authentication for routine re-key

As the duration of key usage increases, the risk of loss or compromise increases. Subscribers must periodically re-key to ensure key security.
The certificate must be re-keyed upon expiration of its validity period. Within the certificate re-key period before the expiration date (e.g., one month before expiration), the Subscriber shall independently generate a new Public Key and Private Key pair and apply to this Certification Center / Registration Authority (RA) for the issuance of a new certificate. This constitutes the re-key (Rekey) of the certificate and Private Key.
For the validity period of certificates, the maximum is 825 days. The validity period of the Private Key is the same as that of the certificate.
Before the certificate validity period expires, the Subscriber signs the new certificate signing request (CSR) with the newly generated Private Key, to prove possession of that new Private Key, and additionally signs the entire re-key request message with the currently valid original Private Key, to confirm that the requester is the holder of the original certificate; the request is then transmitted to the Registration Authority (RA) to apply for new certificate issuance.
When the Subscriber performs certificate and Private Key re-key after the certificate validity period has expired, the Subscriber must apply for certificate re-key with the Registration Authority (RA) using the identity authentication methods specified in [Section 3.2](#32-initial-identity-validation). After obtaining the identity authentication identification data for the certificate re-key application from the Registration Authority (RA), the Subscriber shall submit the certificate signing request signed with the new Private Key, together with the Subscriber's identity authentication identification information, to this Certification Center / Registration Authority (RA) in accordance with the Registration Authority's operational procedures to apply for new certificate issuance. Upon receiving the Subscriber's certificate signing request, the Registration Authority (RA) shall verify the legitimacy of Private Key possession and verify the legitimacy and integrity of the Subscriber's certificate signing request.
A re-key request is processed in accordance with [Section 4.7.3](#473-processing-certificate-re-keying-requests) and must complete all checks under [Section 4.2](#42-certificate-application-processing); a signature made with the existing Private Key serves only to confirm the source of the request and does not replace those checks.



### 3.3.2 Identification and authentication for re-key after revocation

After a Subscriber's certificate is revoked, the Subscriber must undergo the initial validation method specified in [Section 3.2](#32-initial-identity-validation) or other methods that can effectively confirm the Subscriber's identity, and re-apply for a new certificate.

## 3.4 Identification and authentication for revocation request

When a Subscriber submits a certificate revocation request, the Subscriber may contact this Certification Center via email, telephone, or physical documents. This Certification Center shall verify the revocation request using the contact information registered by the Subscriber. Once the verification is passed, this Certification Center shall authenticate the revocation request and perform the certificate revocation operation; the operating procedure is described in [Section 4.9.3](#493-procedure-for-revocation-request).
If the revocation request is submitted by the Registration Authority (RA), after the Registration Authority (RA) has verified the Subscriber's identity, it initiates the revocation request to this Certification Center. After confirming the identity of the Registration Authority (RA) (verified through the RA certificate), this Certification Center performs the certificate revocation operation. Upon receiving the Subscriber Certificate revocation reply message from this Certification Center, the Registration Authority (RA) shall check the legitimacy and integrity of the reply message and, after confirming it is correct, reply to the Subscriber.
Competent authorities, courts, litigation arbitration bodies, and other authorized parties shall submit applications to the Registration Authority (RA) in writing.

# 4 CERTIFICATE LIFE-CYCLE OPERATIONAL REQUIREMENTS

## 4.1 Certificate application

### 4.1.1 Who can submit a certificate application

The representative or agent of a Legal Entity or organization wishing to apply for a certificate serves as the certificate Applicant.

### 4.1.2 Enrollment process and responsibilities

Certificate applicants shall read the Subscriber agreement in advance and fully understand the rights and obligations associated with using the certificate. The Applicant may complete identity verification through the online registration system and confirm agreement to the relevant terms, or prepare and sign a certificate application form in writing and submit it to this Certification Center for processing of the certificate application.

Each certificate request (including a paper application form and an online application) contains a certification by, or on behalf of, the Applicant that all of the information contained therein is correct.

Certificate applicants must generate the certificate key pair and the corresponding PKCS#10 certificate request file (hereinafter referred to as CSR) themselves, and submit it through a secure channel provided by this Certification Center.

## 4.2 Certificate application processing

### 4.2.1 Performing identification and authentication functions

The certificate Applicant must be the representative of a Legal Entity or organization, or a person designated by that representative in accordance with [Section 3.2.6](#326-validation-of-authority). The Applicant must generate the key pair and the corresponding PKCS#10 certificate request file (CSR) and submit it through a secure channel provided by this Certification Center. The certificate request information must include at least one `rfc822Name` Mailbox Address to be included in the `subjectAltName` extension of the certificate.

After accepting the request, this Certification Center performs validation of mailbox authorization or control and authentication of organization identity in accordance with [Section 3.2](#32-initial-identity-validation), and performs the following general verifications prior to issuance:

| Verification Requirement | Description |
|---|---|
| Validation Record validity check | This Certification Center performs validation in accordance with [Section 3.2](#32-initial-identity-validation). If no valid mailbox authorization/control Validation Record or organization identity Validation Record is found, the complete validation procedure must be re-executed. The validity period of each type of Validation Record is set out in [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control). |
| Proof of possession of Private Key | The signature value of the CSR is verified using the Applicant's Public Key to confirm that the Applicant holds the corresponding Private Key and that the Public Key and Private Key form a key pair (see [Section 3.2.1](#321-method-to-prove-possession-of-private-key)). |
| Key compliance | This Certification Center checks the Public Key in the CSR by querying the badkeys database (https://badkeys.info/ ) to ensure it is not a known weak key (such as a Debian Weak Key), and confirms that it satisfies [Section 6.1.5](#615-key-sizes) and [Section 6.1.6](#616-public-key-parameters-generation-and-quality-checking). This Certification Center checks whether the Public Key is already in use by another Applicant: the same Applicant may use the same Public Key in more than one of its certificates, but different Applicants (for example, different Legal Entities or organizations) must not hold the same Public Key. If a check fails, the certificate is not issued. |
| Consistency of Subject information | The Subject Distinguished Name and extension fields in the CSR are verified to be consistent with the request information, and each `rfc822Name` in the `subjectAltName` is verified to have completed the validation required by [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control). |
| Attribute restrictions | In accordance with [Section 7.1.4.2.2](#71422-subject-distinguished-name-fields), the Subject Distinguished Name is verified not to contain the `givenName`, `surname`, `pseudonym`, or `title` attributes. |
| CAA record check | Performed in accordance with [Section 4.2.2.1](#4221-certification-authority-authorization). If the check fails, the certificate is not issued. |

### 4.2.2 Approval or rejection of certificate applications

Upon completion of the identification and authentication procedures specified in [Section 4.2.1](#421-performing-identification-and-authentication-functions), the certificate application is considered approved. If the identification and authentication procedures cannot be completed, the certificate application shall be rejected.

#### 4.2.2.1 Certification authority authorization

Before issuing a certificate, this Certification Center checks whether "Certification Authority Authorization (CAA) Records" exist in the Domain Name System (DNS) for the domain part of each `rfc822Name` recorded in the subjectAltName extension of the certificate, in accordance with [RFC 9495](https://datatracker.ietf.org/doc/html/rfc9495) Section 4. If a CAA record exists and contains an `issuemail` property, this Certification Center further checks whether the property value includes a domain name representing this Certification Center. The Issuer Domain Name that this Certification Center recognizes is `twca.com.tw`. If no domain name representing this Certification Center is included, the Applicant is deemed not to have authorized this Certification Center to issue the certificate, and this Certification Center refuses to issue it.

Where an `accounturi` parameter is present in the CAA record, this Certification Center processes it in accordance with [RFC 8657](https://datatracker.ietf.org/doc/html/rfc8657). Because this Certification Center does not provide an ACME service and does not assign ACME account identifiers (see [Section 3.2.2.1](#3221-validating-authority-over-mailbox-via-domain)), an `accounturi` parameter can never be matched. Accordingly, if every CAA `issuemail` record authorizing this Certification Center for the relevant domain contains a non-empty `accounturi` parameter, the certificate request is rejected.

Where a `validationmethods` parameter is present in the CAA record, this Certification Center processes it in accordance with [RFC 8657](https://datatracker.ietf.org/doc/html/rfc8657). The labels recognized by this Certification Center map to the validation methods listed in [Section 3.2.2.1](#3221-validating-authority-over-mailbox-via-domain) as follows (label matching is performed case-sensitively):

| Label | Validation Method | Reference |
|---|---|---|
| `ca-tbr-4` | Email to a Constructed Address (sunset March 15, 2028) | [TLS BR 3.2.2.4.4](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32244-email-to-a-constructed-address) |
| `ca-tbr-7` | DNS Change Validation | [TLS BR 3.2.2.4.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32247-dns-change) |
| `ca-tbr-18` | Website Change Validation | [TLS BR 3.2.2.4.18](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322418-agreed-upon-change-to-website-v2) |

Where none of the labels listed in the `validationmethods` parameter corresponds to the validation method actually used to validate control over the domain, the parameter is treated as not satisfied and the certificate request is rejected.

During the validation process, the DNS resolver used by the Primary Network Perspective establishes a complete validation chain from the IANA DNSSEC root trust anchor and performs DNSSEC validation, so as to ensure the integrity and security of the query.

This Certification Center records the results of each CAA validation, including the queried domain, the records obtained, and the determination made, and retains them in accordance with [Section 5.5.2](#552-retention-period-for-archive). Upon completion of the CAA record check, this Certification Center must issue the certificate within the time limit of the TTL of the CAA record or 8 hours, whichever is longer. If the certificate is not issued within this limit, a new CAA check must be performed prior to issuance.

#### 4.2.2.2 Multi-perspective issuance corroboration

This Certification Center implements Multi-Perspective Issuance Corroboration (MPIC) for the domain validation methods marked as using MPIC in the table in [Section 3.2.2.1](#3221-validating-authority-over-mailbox-via-domain) (DNS Change Validation and Website Change Validation) and for the Certification Authority Authorization (CAA) record checks performed when those methods are used; the BR does not require MPIC for validation by email (TLS BR Section 3.2.2.4.4 and [Section 3.2.2.2](#3222-validating-control-over-mailbox-via-email)). The specific operational practices are as follows:

1. **Geographic Distribution and Distance Limits:** The remote Network Perspectives deployed by this Certification Center use DNS resolvers that are geographically dispersed. The straight-line distance between each remote node and the Primary Network Perspective, as well as between different remote nodes, is maintained at a minimum of 500 kilometers. A perspective node may use a recursive DNS resolver that is not co-located with it, provided that the resolver falls within the same Regional Internet Registry (RIR) service region as the node relying upon it; for any pair of DNS resolvers used in a single Multi-Perspective Issuance Corroboration attempt, the straight-line distance is likewise at least 500 kilometers.
2. **DNSSEC Validation:** DNSSEC validation is performed by the Primary Network Perspective. The DNS resolver of the Primary Network Perspective establishes a complete validation chain from the IANA DNSSEC root trust anchor and performs DNSSEC validation on every DNS query associated with domain validation and CAA lookups; local policy is not used to disable it, and a DNSSEC validation error (for example SERVFAIL) is not treated as permission to issue. Remote perspective nodes do not perform DNSSEC validation; their function is to repeat the query over a different network path and compare the result with that of the Primary Network Perspective.
3. **DNS Cache Isolation:** To avoid obtaining an incorrect query result from a tampered DNS cache, the DNS resolvers at each perspective node enforce strict cache isolation. Independent query contexts are required for each domain verification query to prevent cached data from different requests or perspectives from interfering with each other.
4. **No Reuse of Results:** Results or information obtained from one perspective node are not reused or cached when performing validation through subsequent perspective nodes. When Multi-Perspective Issuance Corroboration is retried, whether using the same or an alternative validation method, corroborations from previous attempts are not relied upon. This Certification Center does not reuse CAA corroborating evidence from earlier requests; a fresh multi-perspective CAA check is performed for every certificate request.
5. **Issuance Window After a CAA Check:** After processing a CAA record, the certificate is issued within the TTL of that CAA record, or 8 hours, whichever is greater; beyond that period, the CAA check and Multi-Perspective Issuance Corroboration are performed again.
6. **Protection of Communications:** All communications between a remote Network Perspective and this Certification Center take place over an authenticated and encrypted channel relying on modern protocols (for example, HTTPS).

**Minimum number of remote Network Perspectives required:**

| Effective Date | Minimum Number of Remote Perspectives | Additional requirements that must also be met |
|---|---|---|
| September 15, 2025 | 2 | The "Allowed number of inconsistencies for remote Network Perspectives" below must be satisfied; otherwise the certificate is not issued. |
| March 15, 2026 | 3 | In addition to the above, the remote Network Perspectives that corroborate the Primary Network Perspective must fall within the service regions of at least two (2) distinct RIRs; otherwise the certificate is not issued. |
| June 15, 2026 | 4 | Same as the requirements effective March 15, 2026. |
| December 15, 2026 | 5 | Same as the requirements effective March 15, 2026. |

**Allowed number of inconsistencies for remote Network Perspectives:**

| Number of Remote Perspectives | Allowed Number of Inconsistencies |
|---|---|
| 2–5 | 1 |
| 6 or more | 2 |

Matters not set out in detail in this section are handled in accordance with [TLS BR Section 3.2.2.9](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#3229-multi-perspective-issuance-corroboration).

### 4.2.3 Time to process certificate applications

Subject to the contract signed between the Subscriber and this company.

## 4.3 Certificate issuance

### 4.3.1 CA actions during certificate issuance

The certificate issuance procedure is as follows:
- The Subscriber logs in to the Registration Authority (RA) after at least passing identity identification code and password verification, and transmits the generated certificate application message signed with the Subscriber's Private Key to the Registration Authority (RA).
- After the Registration Authority (RA) verifies that the Subscriber's identity identification code and password are correct, it checks the integrity of the Subscriber's certificate application message. Once verified as correct, the Registration Authority (RA) signs the Subscriber's certificate application message with the Registration Authority's Private Key, encrypts it for protection, and transmits it to this Certification Center.
- The reviewing personnel of this Certification Center log in to the certificate management website through two-factor authentication to perform the validation procedures defined in [Section 3.2](#32-initial-identity-validation), and another reviewing officer performs a review procedure. Once all data is confirmed to be correct, the certificate is issued and transmitted to the Registration Authority (RA).
- The Registration Authority (RA) checks the legitimacy and integrity of the Subscriber Certificate response message returned by this Certification Center. Once verified as correct, the Subscriber Certificate is transmitted to the Applicant.
- The certificate start date of Subscriber Certificates issued by this Certification Center shall not be backdated; that is, the certificate start date shall not be earlier than the time of certificate issuance.
- This Certification Center uses zlint and pkilint, prior to signing, to check that the to-be-signed certificate content (tbsCertificate) complies with the encoding and profile requirements of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) and the [BR](https://cabforum.org/working-groups/smime/requirements/), and queries the badkeys database (https://badkeys.info/ ) to determine whether the Public Key carried in the certificate is a known weak key (including Debian weak keys, keys affected by the ROCA vulnerability, and RSA keys that can be factored using Fermat's factorization method); if any check fails, the certificate will not be issued.

The Registration Authority (RA) or this Certification Center may, for security control considerations, deliver the certificate application and Private Key generation software to the Subscriber in a trusted and secure manner. Such software must undergo appropriate security evaluation and verification by the Registration Authority (RA) or this Certification Center.

### 4.3.2 Notification to subscriber by the CA of issuance of certificate

For Subscribers who apply for issuance in real-time online, the issuance result is available immediately after this Certification Center completes the certificate issuance process.
For Subscribers who do not apply for issuance in real-time online, this Certification Center shall notify the Subscriber by telephone or email after completing the certificate issuance process.

## 4.4 Certificate acceptance

### 4.4.1 Conduct constituting certificate acceptance

After receiving the certificate issued by this Certification Center, the Subscriber shall perform the following procedures:
- Confirm that the certificate content is consistent with the information at the time of application and is the Subscriber's correct information.
- Check whether the Public Key in the certificate is the same as the Public Key information in the PKCS#10 certificate signing request.
- The Subscriber must verify the certificate chain of the certificate, check the correctness, integrity, and validity of each certificate in the chain, and confirm whether the certificate has been revoked, whether the certificate validity period has expired, and whether it was indeed issued by this Certification Center.
- If an error is found in the certificate, the Registration Authority (RA) shall be immediately notified to revoke the certificate, and the certificate issuance procedure in [Section 4.3](#43-certificate-issuance) may be re-performed.
- After receiving the applied certificate, the Subscriber must confirm that they have fully understood and agree to the rights and obligations of using the certificate. If the Subscriber does not agree, it shall be deemed a refusal to accept the certificate, and the Subscriber shall notify the Registration Authority (RA) to revoke the certificate.

This Certification Center does not provide certificate modification services. Where the Subscriber identification information or other information recorded in a certificate must be changed, the Subscriber shall first revoke the original certificate and then apply for a new certificate, in accordance with [Section 4.8](#48-certificate-modification).

### 4.4.2 Publication of the certificate by the CA

After the Subscriber completes the acceptance procedure, this Certification Center shall publish the issued Subscriber Certificate in the Repository.

### 4.4.3 Notification of certificate issuance by the CA to other entities

No stipulation.

## 4.5 Key pair and certificate usage

### 4.5.1 Subscriber private key and certificate usage

The usage, scope of application, and limitations of the Subscriber Certificate are governed by the provisions of [Section 1.4](#14-certificate-usage).
The Subscriber shall properly protect their Private Key. If there are any concerns about unauthorized use, exposure, or loss, the Subscriber must report to the Registration Authority (RA).

### 4.5.2 Relying party public key and certificate usage

Before relying on a Subscriber Certificate issued by this Certification Center, the Relying Party shall at a minimum perform the following necessary procedures to determine whether to rely on the certificate:
- Obtain the self-signed certificate of the Root Certification Authority (RCA) of this Certification Center through an appropriate and secure channel.
- Check whether the RCA self-signed certificate, the Subordinate CA certificate, and the Subscriber Certificate have expired.
- Use the Public Key of the RCA self-signed certificate to verify whether the digital signature of the Subordinate CA certificate is valid and has not been revoked.
- Use the Public Key of the Subordinate CA certificate to verify whether the digital signature of the Subscriber Certificate is valid.
- Check that the Subscriber Certificate has not been revoked by the Subordinate CA.

If the above verifications cannot be passed, it indicates that the Subscriber Certificate obtained by the Relying Party was not issued by this Certification Center or the certificate has expired, and the Relying Party shall not rely on the Subscriber Certificate. Only after the Relying Party has established trust in the certificate may the Relying Party use it to verify the correctness of digital signatures on emails and to verify the identity of the signer.

## 4.6 Certificate renewal

Certificate renewal refers to the re-issuance of a certificate with the same key, different serial number, and extended validity period under the condition that the Subscriber's identification information remains unchanged.

This Certification Center does not provide certificate renewal services. A Subscriber who needs a new certificate before expiry of an existing certificate shall perform a certificate re-key (generating a new key pair) in accordance with [Section 4.7](#47-certificate-re-key).

### 4.6.1 Circumstance for certificate renewal

Not applicable (this Certification Center does not provide certificate renewal services).

### 4.6.2 Who may request renewal

Not applicable (this Certification Center does not provide certificate renewal services).

### 4.6.3 Processing certificate renewal requests

Not applicable (this Certification Center does not provide certificate renewal services).

### 4.6.4 Notification of new certificate issuance to subscriber

Not applicable (this Certification Center does not provide certificate renewal services).

### 4.6.5 Conduct constituting acceptance of a renewal certificate

Not applicable (this Certification Center does not provide certificate renewal services).

### 4.6.6 Publication of the renewal certificate by the CA

Not applicable (this Certification Center does not provide certificate renewal services).

### 4.6.7 Notification of certificate issuance by the CA to other entities

Not applicable (this Certification Center does not provide certificate renewal services).

## 4.7 Certificate re-key

Certificate re-key refers to generating a new Public Key and Private Key pair and applying to the certification authority for certificate issuance using the original registration information.

### 4.7.1 Circumstance for certificate re-key

As specified in [Section 3.3.1](#331-identification-and-authentication-for-routine-re-key).

### 4.7.2 Who may request certification of a new public key

The Subscriber has the right to re-key the certificate.

### 4.7.3 Processing certificate re-keying requests

The Subscriber's identity is authenticated in accordance with [Section 3.3](#33-identification-and-authentication-for-re-key-requests); all checks under [Section 4.2](#42-certificate-application-processing) are performed (including the validation data reuse periods and key checks under [Section 4.2.1](#421-performing-identification-and-authentication-functions) and the CAA check under [Section 4.2.2.1](#4221-certification-authority-authorization)); and the certificate is then issued in accordance with [Section 4.3](#43-certificate-issuance). Where validation data has exceeded the period specified in [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control), validation is performed again. A signature made with the existing Private Key serves only to confirm the source of the request and does not replace the checks above.

### 4.7.4 Notification of new certificate issuance to subscriber

As specified in [Section 4.3.2](#432-notification-to-subscriber-by-the-ca-of-issuance-of-certificate).

### 4.7.5 Conduct constituting acceptance of a re-keyed certificate

As specified in [Section 4.4](#44-certificate-acceptance).

### 4.7.6 Publication of the re-keyed certificate by the CA

As specified in [Section 4.4.2](#442-publication-of-the-certificate-by-the-ca).

### 4.7.7 Notification of certificate issuance by the CA to other entities

As specified in [Section 4.4.3](#443-notification-of-certificate-issuance-by-the-ca-to-other-entities).

## 4.8 Certificate modification

Certificate modification refers to the re-issuance of a certificate to the Subscriber when the Public Key in the certificate remains unchanged but the recorded Subscriber's name identification information needs to be changed.
This Certification Center does not accept certificate modification by the Subscriber. If the Subscriber's identification information or other information recorded in the certificate needs to be changed, the certificate must first be revoked in accordance with [Section 4.9](#49-certificate-revocation-and-suspension), and then a new certificate issuance shall be applied for in accordance with Sections [4.1](#41-certificate-application), [4.2](#42-certificate-application-processing), [4.3](#43-certificate-issuance), and [4.4](#44-certificate-acceptance).

### 4.8.1 Circumstance for certificate modification

Not applicable (this Certification Center does not provide certificate modification services). Where information recorded in a certificate must be changed, revocation and re-application apply in accordance with [Section 4.8](#48-certificate-modification).

### 4.8.2 Who may request certificate modification

Not applicable (this Certification Center does not provide certificate modification services).

### 4.8.3 Processing certificate modification requests

Not applicable (this Certification Center does not provide certificate modification services).

### 4.8.4 Notification of new certificate issuance to subscriber

Not applicable (this Certification Center does not provide certificate modification services).

### 4.8.5 Conduct constituting acceptance of modified certificate

Not applicable (this Certification Center does not provide certificate modification services).

### 4.8.6 Publication of the modified certificate by the CA

Not applicable (this Certification Center does not provide certificate modification services).

### 4.8.7 Notification of certificate issuance by the CA to other entities

Not applicable (this Certification Center does not provide certificate modification services).

## 4.9 Certificate revocation and suspension

When a revocation event occurs, the relevant certificate shall be revoked and added to the CRL/OCSP. Revoked certificates must be included in all subsequently published CRL/OCSP until the certificate expires.

### 4.9.1 Circumstances for revocation

#### 4.9.1.1 Reasons for revoking a subscriber certificate

This Certification Center shall revoke the certificate within 24 hours when any of the following circumstances occur:

1. The Subscriber requests in writing to terminate the use of the certificate.
2. The Subscriber informs that the original certificate application was not authorized.
3. The Private Key associated with the Subscriber's certificate is proven or suspected to have been compromised.
4. The key pair used by the Subscriber is a weak key (e.g., Debian Weak Key).
5. The validation data for domain authorization or mailbox control for any Mailbox Address in the certificate is unreliable.

Where a Root Store Program requests that this Certification Center revoke a certificate, this Certification Center revokes it within 24 hours of receiving that request, using the corresponding CRLReason.

This Certification Center shall revoke the certificate within 5 days when any of the following circumstances occur:

6. The key used by the Subscriber violates the provisions of Sections [6.1.5](#615-key-sizes) and [6.1.6](#616-public-key-parameters-generation-and-quality-checking).
7. The Subscriber's certificate has been misused.
8. The Subscriber has violated the competent authority's laws, the certificate policy, this Statement, or the Subscriber agreement.
9. The Subscriber is no longer permitted to legally use the Mailbox Address or Domain Name recorded in the certificate.
10. The information recorded in the certificate has changed.
11. The certificate was not issued in accordance with the BR, the certificate policy, or the procedures specified in this Statement.
12. The information recorded in the certificate is inaccurate.
13. This Certification Center's authority to issue certificates has expired, been revoked, or been suspended — unless arrangements have been made to continue maintaining CRL and OCSP services.
14. Items that the certificate policy requires to be revoked.
15. A method is known to exist that can compromise the Subscriber's key, or the key generation method has known weaknesses.
#### 4.9.1.2 Reasons for revoking a subordinate CA certificate

The Root Certification Authority (RCA) shall revoke a Subordinate CA certificate within 7 days if one or more of the following occurs:

1. The Subordinate CA requests revocation in writing.
2. The Subordinate CA notifies the RCA that the original certificate request was not authorized and does not retroactively grant authorization.
3. The RCA obtains evidence that the Subordinate CA's Private Key corresponding to the Public Key in the certificate suffered a Key Compromise or no longer complies with the requirements of [Section 6.1.5](#615-key-sizes) and [Section 6.1.6](#616-public-key-parameters-generation-and-quality-checking).
4. The RCA obtains evidence that the certificate was misused.
5. The RCA is made aware that the certificate was not issued in accordance with the BR or this Statement, or that the Subordinate CA has not complied with the BR or this Statement.
6. The RCA determines that any of the information appearing in the certificate is inaccurate or misleading.
7. The RCA or the Subordinate CA ceases operations for any reason and has not made arrangements for another CA to provide revocation support for the certificate.
8. The RCA's or the Subordinate CA's right to issue certificates under the BR expires or is revoked or terminated, unless the RCA has made arrangements to continue maintaining the CRL/OCSP Repository.
9. Revocation is required by this Statement.

### 4.9.2 Who can request revocation

1. The Subscriber.
2. This Certification Center or its Registration Authority.
3. The competent authority, a court, or an arbitral body.
4. Persons other than those listed above who suspect that a certificate key has been compromised or have other security concerns may also notify this Certification Center. This Certification Center will proceed with the certificate revocation procedure after confirming the report is valid. For contact information, please refer to [Section 1.5.2](#152-contact-person).

### 4.9.3 Procedure for revocation request

This Certification Center accepts certificate revocation requests 7 x 24. For how to report a Key Compromise, certificate misuse, or other problems, see [Section 1.5.2](#152-contact-person). The certificate revocation procedure is as follows:
- Those authorized to request certificate revocation as defined in [Section 4.9.2](#492-who-can-request-revocation) apply for certificate revocation.
- If the certificate Subscriber submits the certificate revocation application, authentication shall be performed as specified in [Section 3.4](#34-identification-and-authentication-for-revocation-request); other certificate revocation applications shall be verified based on the certificate revocation reasons defined in [Section 4.9.1](#491-circumstances-for-revocation).
- After this Certification Center completes authentication, the revocation is completed within the time limits specified in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate) and [Section 4.9.1.2](#4912-reasons-for-revoking-a-subordinate-ca-certificate).
- Manual application: The Subscriber submits a certificate revocation request. After this Certification Center verifies the Subscriber's identity, the operational personnel shall execute the certificate revocation.
- Internet application: The Subscriber logs in to the Registration Authority's certificate system webpage. After the Registration Authority verifies the Subscriber's identity, this Certification Center's certificate system executes the certificate revocation.
- When the Registration Authority receives the Subscriber Certificate revocation response message from this Certification Center, it checks the legitimacy and integrity of the response message; once verified as correct, the response is relayed to the requesting Subscriber.
- Competent authorities, courts, litigation arbitration bodies, and other authorized parties shall submit applications to the Registration Authority in writing.

### 4.9.4 Revocation request grace period

The S/MIME BR makes no stipulation as to the period within which a Subscriber must submit a revocation request. After becoming aware of a revocation circumstance set out in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate), the Subscriber shall immediately submit a certificate revocation request.

A delay by a Subscriber in submitting a request does not relieve this Certification Center of its obligation to complete revocation within the time limits set out in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate); once this Certification Center becomes aware of a revocation circumstance, it completes revocation within the time limits set out in that Section.

### 4.9.5 Time within which CA must process the revocation request

Within 24 hours after receiving a Certificate Problem Report, this Certification Center shall investigate the facts and circumstances related to that report and shall provide a preliminary report on its findings to both the Subscriber and the entity who filed the Certificate Problem Report. A Certificate Problem Report may be submitted by a Subscriber, a Relying Party, an Application Software Supplier, or any other third party. In cases requiring revocation, the period from receipt of the Certificate Problem Report or revocation-related notice to published revocation shall not exceed the time limits specified in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate).

After reviewing the facts and circumstances, this Certification Center works with the Subscriber and any entity reporting the Certificate Problem Report or other revocation-related notice to establish whether or not the certificate will be revoked and, if so, the date on which it will be revoked. The date selected considers the nature of the alleged problem (scope, context, severity, magnitude, and risk of harm), the consequences of revocation (direct and collateral impacts to Subscribers and Relying Parties), the number of Certificate Problem Reports received about the particular certificate or Subscriber, the entity making the complaint, and relevant legislation.

### 4.9.6 Revocation checking requirement for relying parties

Before relying on a certificate, Relying Parties shall check its status through the CRL or OCSP and shall, based on their risk, liability, and potential consequences, decide which method to use and the query frequency.

If a Relying Party checks certificate status through a CRL issued by this Certification Center, the Relying Party shall verify before use that the CRL was issued by this Certification Center, including verifying the correctness and validity of the CRL's digital signature. Other verification considerations must satisfy the relevant requirements of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280).

If a Relying Party checks certificate status through OCSP messages provided by this Certification Center, the Relying Party shall verify before use that the OCSP message was issued by this Certification Center's OCSP Responder, including verifying the correctness and validity of the OCSP message's digital signature. Other verification considerations must satisfy the relevant requirements of [RFC 6960](https://datatracker.ietf.org/doc/html/rfc6960).

### 4.9.7 CRL issuance frequency

All CRLs issued by this Certification Center are published via a publicly accessible HTTP URL.

CRLs covering Subscriber Certificates are issued by the Subordinate CA on a daily schedule, with the `nextUpdate` field no more than 10 days after the `thisUpdate` field; the value currently configured for that schedule is 1 day.

CRLs covering Subordinate CA certificates are issued by the Root CA on a daily schedule, with the `nextUpdate` field no more than 12 months after the `thisUpdate` field; the value currently configured for that schedule is 1 day.

This Certification Center may adjust the configured schedule values stated in the two preceding paragraphs as operationally required, provided that they remain within the `nextUpdate` limits stated above; in any case, CRLs covering Subscriber Certificates are updated and published at least every 7 days, CRLs covering Subordinate CA certificates are updated and published at least every 12 months, and a CRL is updated and published within 24 hours after any certificate it covers is recorded as revoked.

The CRL issuance system of this Certification Center also provides a forced-issuance function. For the circumstances set out in [Section 4.9.1](#491-circumstances-for-revocation) that require revocation within 24 hours (for example, Key Compromise), this Certification Center triggers that function manually once the revocation has been recorded, and issues and publishes an updated CRL immediately rather than waiting for the scheduled run.

### 4.9.8 Maximum latency for CRLs

No stipulation.

### 4.9.9 On-line revocation/status checking availability

This Certification Center provides OCSP services, supporting OCSP service queries via HTTP GET or POST. Response messages comply with [RFC 6960](https://datatracker.ietf.org/doc/html/rfc6960) specifications and include a digital signature for the message.

For OCSP responses issued by this Certification Center covering the status of Subscriber Certificates and CA certificates, the validity interval (`thisUpdate` to `nextUpdate`) is at least 8 hours and no more than 7 days; the value currently configured is 4 days. For a validity interval of 16 hours or more, this Certification Center provides an updated response before one-half of the validity period has elapsed; for a validity interval of less than 16 hours, it provides an updated response at least 8 hours prior to the `nextUpdate`. This validity interval and update timing meet [BR Section 4.9.10](https://cabforum.org/working-groups/smime/requirements/#4910-on-line-revocation-checking-requirements). The `nextUpdate` of an OCSP response is no later than the notAfter of the Delegated Responder certificate included in that response. This Certification Center may adjust the configured value as operationally required, provided that the adjusted value continues to meet these requirements. The OCSP issuance system also provides a forced-issuance function; for circumstances requiring revocation within 24 hours, this Certification Center triggers that function manually once the revocation has been recorded and re-signs the response immediately rather than waiting for the scheduled run.

Where any CA certificate is revoked, this Certification Center updates the OCSP response for that certificate within 24 hours.

For a query on a certificate serial number that this Certification Center has not assigned, its OCSP responder returns "revoked" or "unknown", and never "good". For other related content, please refer to [Section 7.3](#73-ocsp-profile).

### 4.9.10 On-line revocation checking requirements

The Relying Party must use the CRL issued by this Certification Center to check the certificate status before deciding to rely on a certificate issued by this Certification Center.
If the Relying Party of a certificate does not use the CRL issued by this Certification Center to check the certificate status, the Relying Party must check the certificate status through the OCSP service as specified in [Section 4.9.9](#499-on-line-revocationstatus-checking-availability).

### 4.9.11 Other forms of revocation advertisements available

No stipulation.

### 4.9.12 Special requirements re key compromise

If Key Compromise is suspected, the reporter may submit evidentiary information through legitimate channels (refer to [Section 1.5.2](#152-contact-person)) to contact the appropriate contact of this Certification Center. This Certification Center accepts the following method to prove suspected Key Compromise:

- Submit a CSR signed with the suspected compromised key (in standard PKCS#10 format) as proof. The CN of the CSR must be "Proof of Key Compromise for TWCA" for this Certification Center to verify its authenticity.

When this Certification Center's signing key is compromised, the following procedures shall be followed:

1. Generate a new signing key pair and the corresponding new certificate.
2. Revoke all issued certificates. Use the new signing key to issue a CRL that includes all issued unexpired certificate information (including previously revoked certificates issued before the Key Compromise).
3. Notify Subscribers.
4. Provide the certificate corresponding to this Certification Center's new signing key.
5. Use the new signing key to issue certificates to Subscribers.

If a Subscriber's key is suspected or confirmed to have been compromised, the Subscriber shall notify this Certification Center immediately upon learning of the fact to revoke the certificate.

### 4.9.13 Circumstances for suspension

As this Certification Center does not provide certificate suspension services, the following provisions regarding who may request certificate suspension, certificate suspension procedures, and certificate suspension period limitations are not applicable.

If Key Compromise occurs, the certificate suspension procedure shall not be used; the matter shall be handled in accordance with [Section 4.9.12](#4912-special-requirements-re-key-compromise).

### 4.9.14 Who can request suspension

Not applicable.

### 4.9.15 Procedure for suspension request

Not applicable.

### 4.9.16 Limits on suspension period

Not applicable.

## 4.10 Certificate status services

### 4.10.1 Operational characteristics

Subscribers may check certificate status through the CRL and OCSP services provided by this Certification Center.

The download location of the Certificate Revocation List (CRL) is noted in the cRLDistributionPoints extension field of the certificate.

The revocation information for a revoked certificate is removed from the CRL and OCSP services only after the certificate's validity period has expired.

### 4.10.2 Service availability

This Certification Center provides 24x7 certificate status services for Relying Parties to query the status of all unexpired certificates.

This Certification Center operates its CRL and OCSP services with resources sufficient to provide a response time of ten seconds or less under normal operating conditions. For CRL issuance frequency, refer to [Section 4.9.7](#497-crl-issuance-frequency).

This Certification Center provides a 24x7 contact mechanism for reporting significant certificate issues (e.g., certificates applied for fraudulently or issued erroneously). Upon confirmation, the problematic certificates will be revoked, and any illegal incidents will be referred to law enforcement agencies. For the contact window of this Certification Center, refer to [Section 1.5.2](#152-contact-person).

### 4.10.3 Optional features

Refer to the provisions of Sections [4.9.9](#499-on-line-revocationstatus-checking-availability) and [4.9.11](#4911-other-forms-of-revocation-advertisements-available).

## 4.11 End of subscription

When a certificate issued by this Certification Center expires, is revoked, or this Certification Center ceases operations, the issued certificate becomes invalid.

## 4.12 Key escrow and recovery

### 4.12.1 Key escrow and recovery policy and practices

The keys of this Certification Center and Subscribers shall not be escrowed.

### 4.12.2 Session key encapsulation and recovery policy and practices

No stipulation.

# 5 FACILITY, MANAGEMENT, AND OPERATIONAL CONTROLS

The security controls of this Certification Center, in addition to complying with this Statement, also comply with the "Network and Certificate System Security Requirements" (NCSSR) established by CABF.

This Certification Center defines and maintains an inventory of its CA Infrastructure. The inventory covers the server hosts and database hosts of the certificate systems, the offline Root CA systems, the hardware security modules, and the systems that support the security of the foregoing, namely network communication equipment and network boundary control devices, intrusion detection and prevention devices, logging and monitoring systems, and endpoint protection devices; assets located in the primary machine room, the primary key room, and the standby machine room are all included.

For each asset, the inventory records the machine room in which it is located, its category, host or device designation, asset number, purpose, and IP address; for an asset that operates offline, the IP address field records the offline status instead.

The inventory is maintained jointly by the operations department and the information security department of the Company, and is updated whenever an asset is added, replaced, or has its purpose changed. Each asset listed in the inventory is protected against common network and system threats using intrusion detection and prevention controls, as required by the NCSSR.

## 5.1 Physical controls

### 5.1.1 Site location and construction

The server room of this Certification Center is located within the Company's premises. It meets the facility standards for storing highly important and sensitive information, and incorporates physical security mechanisms including access control, security guards, intrusion detection, and video surveillance to prevent unauthorized access to the equipment of this Certification Center.

### 5.1.2 Physical access

The physical access control measures for the server room of this Certification Center are as follows:

- Three levels of identity verification access control (using Smart Cards or fingerprint recognition), of which at least two levels require simultaneous identity authentication of two or more persons before entry is permitted. The facility is equipped with 24-hour CCTV motion-detection surveillance and infrared intrusion alarm systems to record access to the server room and prevent unauthorized entry.
- Backup data related to the Private Keys used in the operations of this Certification Center are securely stored in safes protected by surveillance camera systems. Operational personnel involved in certificate management system operations must have at least two persons present to perform certificate management operations, all under the monitoring of surveillance equipment.
- Equipment such as hardware, software, and Hardware Security Modules (HSMs) are all placed in environments protected by surveillance camera systems, and at least two persons must be present to perform key management-related operations.

### 5.1.3 Power and air conditioning

The server room of this Certification Center is equipped with diesel generators and an Uninterruptible Power Supply (UPS). When the regular power supply system fails, it automatically switches to diesel generator power, with the UPS providing stable power during the switchover process.

The facility has an independent air conditioning system to ensure stable system operation and provide an optimal working environment, with regular maintenance and testing performed.

### 5.1.4 Water exposures

The server room of this Certification Center is a sealed building. Apart from internally accessible entry doors, the exterior is entirely a concrete structure, and the floor is fitted with raised flooring, eliminating concerns about water ingress.

### 5.1.5 Fire prevention and protection

The server room of this Certification Center is constructed with fire-resistant materials and equipped with fire suppression equipment with a central monitoring system that can automatically activate fire suppression upon detection of a fire.

### 5.1.6 Media storage

The media storage environment of this Certification Center is designed to prevent accidental media damage. It includes equipment and an environment with anti-magnetic and anti-static interference protection for magnetic media. Important data backup media are stored in fire-resistant safes, with one copy of the backup media stored at an Off-site Backup / Disaster Recovery Site with security control measures.

### 5.1.7 Waste disposal

When hardware equipment, disk drives, and cryptographic devices used by this Certification Center are decommissioned, any commercially sensitive and confidential information stored therein must undergo secure erasure and destruction, verified by the audit unit, with verification documents retained.

Documents and media containing commercially sensitive and confidential information must undergo secure erasure and destruction during disposal so that the information cannot be recovered or accessed, verified by the audit unit, with verification documents retained.

### 5.1.8 Off-site backup

This Certification Center maintains an Off-site Backup / Disaster Recovery Site with backup equipment. When the equipment used in daily operations cannot function normally due to external factors, the backup equipment can provide continuous operational capability for this Certification Center.

Media information and documents required for the operation of this Certification Center are backed up and stored at a highly secure Off-site Backup environment with temperature and humidity controls, anti-magnetic and anti-static interference protection, surveillance camera monitoring, and personnel access requiring authorization.

Backup log files of this Certification Center are all stored at the highly secure Off-site Backup / Disaster Recovery Site.

## 5.2 Procedural controls

### 5.2.1 Trusted roles

Under the Public Key Infrastructure (PKI) framework, the certificate management operations of this Certification Center must be conducted under rigorous and secure operational procedures. To ensure proper separation of duties and responsibilities, and to ensure that backup arrangements for positions do not jeopardize the overall system security and operational integrity, the Trusted Roles and their division of duties at this Certification Center are as follows:

- **System Administrator** — Responsible for system installation, management operations, and environment parameter configuration.
- **Certificate Officer** — Responsible for certificate issuance and certificate revocation.
- **Auditor** — Responsible for conducting internal audits, reviewing, and maintaining Audit Logs.
- **Operator** — Responsible for routine maintenance operations such as backup, restoration, and website data maintenance.
- **Developer** — Responsible for system design and development.

### 5.2.2 Number of persons required per task

The personnel requirements for each Trusted Role are as follows:

- System Administrator — at least 2 persons.
- Certificate Officer — at least 2 persons.
- Auditor — at least 1 person.
- Operator — at least 2 persons.
- Developer — at least 1 person.

Before completed code is submitted for integration into the production environment, at least two authorized trusted persons must review and confirm it, ensuring the code meets business logic and security requirements before approval for release.

Before issuing a Subscriber Certificate, at least 2 persons in Trusted Roles must confirm before Subscriber Certificate issuance can be executed.

### 5.2.3 Identification and authentication for each role

System Administrators, Certificate Officers, Auditors, and Operators who perform certificate management operations at this Certification Center are assigned duties separated by business function and use unique identification codes, Smart Cards, and associated identity verification passwords to achieve identification and authentication of Trusted Roles.

Developers of this Certification Center access source code exclusively through a code version control management platform, integrated with Active Directory (AD) account privilege control mechanisms, with project access privileges assigned according to development tasks.

All operations performed by relevant operational personnel according to business requirements are recorded in detail to ensure auditability of system resource usage and to enable assessment of system security threats and risks.

### 5.2.4 Roles requiring separation of duties

| Role | Certificate Officer | System Administrator | Auditor | Operator | Developer |
|------|:---:|:---:|:---:|:---:|:---:|
| Certificate Officer | ○ | X | X | X | X |
| System Administrator | X | ○ | X | ○ | X |
| Auditor | X | X | ○ | X | X |
| Operator | X | ○ | X | ○ | X |
| Developer | X | X | X | X | ○ |

## 5.3 Personnel controls

### 5.3.1 Qualifications, experience, and clearance requirements

Operational personnel of this Certification Center must be loyal, trustworthy, and enthusiastic about their work. They shall not hold other concurrent positions that affect certificate operations and shall have no records of legal violations or poor credit.

- Certificate Officers must have at least practical experience in certificate operations, or have passed examinations after receiving certificate-related operational training.
- System Administrators must have at least practical experience in certificate operations and experience in computer system planning and operations management.
- Auditors must have at least professional knowledge in information security or system auditing and experience in independently reviewing operational processes.
- Operators must have at least received training in certificate lifecycle management and system management.
- Developers must have at least the capability of secure code writing and system development.

### 5.3.2 Background check procedures

Working personnel of this Certification Center must undergo an identity background security check by the human resources management department in accordance with background check regulations, followed by a practical experience review by the relevant operations department, before they may assume their positions. Annual reviews of practical experience must be conducted based on the characteristics of each position, serving as the basis for determining the person's suitability for the role or for making job adjustments.

Upon termination of an individual's employment or contracting relationship, this Certification Center disables that individual's access to the CA Infrastructure and to network boundary controls in all forms (including physical access control, system accounts, remote connection privileges, and smart cards) within 24 hours of the termination.

All accounts capable of authenticating to or accessing the CA Infrastructure and network boundary controls (including personnel accounts, service accounts, and privileged accounts) are reviewed by this Certification Center every 3 months to confirm that the account remains necessary and that its privileges remain consistent with the holder's duties, and to remove accounts or privileges that are no longer required. The results of each review are documented.

### 5.3.3 Training requirements

Operational personnel of this Certification Center receive training appropriate to their duties, covering the hardware and software functions required for system operation, operational procedures, certificate issuance review procedures, security control procedures, Disaster Recovery operation specifications, key management operations, the Certificate Policy and this Statement, and other information security-related operational specifications. When there are changes to the certificate system or new systems are added, appropriate training is also provided.

Specifically, this Certification Center enforces strict training and qualification testing for "Validation Specialists" responsible for identity and mailbox verification tasks. Before allowing a Validation Specialist to perform any verification task, this Certification Center requires the specialist to pass an examination provided by this Certification Center on the information verification requirements outlined in the BR. The CA documents and maintains records proving that each Validation Specialist possesses the skills required for the assigned task before permitting execution. Training for Validation Specialists covers basic Public Key Infrastructure knowledge, authentication and vetting policies and procedures (including this Statement), common threats to the information verification process (including phishing and other social engineering tactics), and the requirements of the [BR](https://cabforum.org/working-groups/smime/requirements/) (per [BR Section 5.3.3](https://cabforum.org/working-groups/smime/requirements/#533-training-requirements)).

For hardware, software, application systems, and security management systems related to the certificate management system, this Certification Center has established comprehensive training specifications. Training on relevant skills is conducted when new personnel are hired or when systems at this Certification Center are changed. Detailed records of training outcomes are maintained and serve as a reference for work delegation of relevant operational personnel.

### 5.3.4 Retraining frequency and requirements

For personnel involved in the operation of the certificate management system, this Certification Center reviews their relevant knowledge and skills for operating the certificate management system at least once per year and provides appropriate training. Training is provided to operational personnel whenever certificate management system functions are updated, new systems are added, or there are advances and updates in Public Key Infrastructure-related knowledge and technology.

### 5.3.5 Job rotation frequency and sequence

- A System Administrator must have left the original position for at least 1 year before being eligible to transfer to the role of Certificate Officer or Auditor.
- A Certificate Officer must have left the original position for at least 1 year before being eligible to transfer to the role of System Administrator or Auditor.
- An Auditor must have left the original position for at least 1 year before being eligible to transfer to the role of System Administrator or Certificate Officer.
- An Operator may concurrently serve as a System Administrator in accordance with [Section 5.2.4](#524-roles-requiring-separation-of-duties); before doing so, the Operator must complete the relevant System Administrator training and pass the review.
- An Operator must have served for at least 2 years and must have completed relevant training and passed the review before being eligible to transfer to the role of Certificate Officer or Auditor.
- A Developer must have left the original position for at least 1 year before being eligible to transfer to the role of System Administrator, Certificate Officer, or Auditor.

### 5.3.6 Sanctions for unauthorized actions

If operational personnel involved in the operation of the certificate management system of this Certification Center intentionally or negligently perform operations outside the scope of their duties, regardless of whether it causes security issues for the certificate management system, the matter shall be immediately reported to the supervisory manager and handled in accordance with relevant operational regulations.

### 5.3.7 Independent contractor requirements

If this Certification Center engages outsourced personnel to serve as Operators due to insufficient human resources, this Certification Center must conduct background checks in accordance with the procedures specified in [Section 5.3.2](#532-background-check-procedures), followed by training on job-related knowledge and skills as specified in [Section 5.3.3](#533-training-requirements). In addition to signing confidentiality agreements related to the scope of work, such outsourced personnel must comply with relevant operational regulations and legal requirements. The rights and obligations of such outsourced personnel are the same as those of the internal Operators of this Certification Center.

### 5.3.8 Documentation supplied to personnel

To ensure the normal operation of the certificate management system, this Certification Center must provide relevant operational personnel with the following operational documents for system operation, including at minimum:

- Operating documents for hardware, software operating platforms, network systems and website-related operations, and cryptographic system operations.
- Operating documents related to the certificate management system of this Certification Center.
- This Statement, Certificate Policy, and related operational specification documents.
- Internal operational documents of the certificate management system of this Certification Center, such as: system backup and recovery operational documents, off-site Disaster Recovery backup and recovery operational documents, and routine work operational documents.

## 5.4 Audit logging procedures

### 5.4.1 Types of events recorded

Each Audit Log entry of this Certification Center, whether recorded automatically or manually, includes the following items:

- Event type.
- Date and time of the event.
- Result of the event (success or failure).
- The entity or person that triggered the event.
- Description of the event content.

The following are the types of audit events recorded by this Certification Center:

**Security Audit**

- Any changes to important audit parameters, such as audit event types, old and new parameter values, etc.
- Any attempts to delete or modify Audit Log files.

**Personnel and Trusted Role Management, Identification and Authentication**

- Setup of new roles, whether successful or failed.
- Changes to the maximum tolerance for authentication attempts.
- Maximum number of failed authentication attempts when a user logs into the system.
- Administrator unlocking a locked account.
- Administrator changing the system's authentication mechanism, e.g., from password to biometric.

**Key Operation Procedures**

- Key generation.
- Key backup, storage, recovery, and archival.
- Key destruction.
- Certificate requests, re-key requests, and revocation for this Certification Center's own certificates.

**Private Key Loading and Storage**

- Loading Private Keys into system components.

**Addition, Deletion, and Storage of Trusted Public Keys**

- Changes to trusted Public Keys, including addition, deletion, and storage.

**Private Key Export**

- Export of Private Keys (excluding keys intended for single-use or one-time use only).

**Certificate Registration**

- Certificate registration application process, including certificate requests and re-key requests.
- Approval and rejection of certificate requests.
- Issuance of certificates.
- All information generated and documentation received in connection with processing a certificate request and issuing a certificate, together with the date, time, and personnel involved.
- Records of all verification activities stipulated in the BR and this Statement.

**Certificate Revocation**

- Certificate revocation application process.
- CRL generation records.
- OCSP service signing records.

**Approval of Certificate Status Changes**

- Approval or rejection of applications for certificate status changes.

**Configuration Settings**

- Changes to security configuration-related settings.

**Account Management**

- Adding or removing roles and users.
- Modifying access permissions of user accounts or roles.

**Certificate Profile Management**

- Introduction, changes, and retirement of certificate profiles.

**CRL Profile Management**

- Changes to CRL profiles.

**System Installation and Significant Operational Events**

- Installing the operating system.
- Installing the certificate management system.
- Installation, update, and removal of software on a Certificate System.
- Installing the Hardware Security Module (HSM).
- Removing the Hardware Security Module (HSM).
- Destroying the Hardware Security Module (HSM).
- Starting the system.
- Attempting to log into the certificate management system.
- Receipt of hardware and software.
- Attempting to set a password.
- Attempting to change a password.
- Internal data backup of this Certification Center.
- Internal data restoration of this Certification Center.
- File operations (e.g., creation, renaming, moving, etc.).
- Transmitting any information to the repository.
- Accessing the internal database of this Certification Center.
- Key Compromise.
- Key changeover of this Certification Center.

**Changes to This Certification Center's Server Configuration**

- Hardware.
- Software.
- Operating system.
- Patches.
- Security profiles.

**Router and Firewall Activities**

- Successful and unsuccessful login attempts to routers and firewalls.
- All administrative actions performed on routers and firewalls, including configuration changes, firmware updates, and access control modifications.
- All changes made to access control lists (ACLs) or rules (e.g., firewall rules) on routers and firewalls, including additions, modifications, and deletions.
- All system events and errors on routers and firewalls, including hardware failures, software crashes, and system restarts.

**Physical Access and Site Security**

- Personnel entering and exiting the server room of this Certification Center.
- Accessing the servers of this Certification Center.
- Known or suspected violations of physical security regulations.

**Anomalous Events**

- Software errors.
- Software integrity check failures.
- Receipt of malformed messages.
- Messages routed through non-standard paths.
- Network attacks (suspected or confirmed).
- Equipment failures.
- Power irregularities.
- UPS failures.
- Significant network service or access failures.
- Violations of this Statement.
- System clock resets.

### 5.4.2 Frequency of processing audit log

This Certification Center performs continuous automated monitoring of the integrity of its logging process; to the extent not covered by continuous automated monitoring, Audit Logs are reviewed by personnel in a Trusted Role every 31 days, investigating events that have occurred. The review includes verifying that the Audit Logs have not been tampered with, reviewing all log entries, and examining any alerts or anomalies, with explanations provided and preventive measures proposed. The results of the Audit Log review are documented.

Where the automated monitoring mechanism generates a security alert, personnel in a Trusted Role begin an initial response within 24 hours of the alert being generated, and handle and report the matter in accordance with [Section 5.7.1](#571-incident-and-compromise-handling-procedures).

### 5.4.3 Retention period for audit log

The relevant Audit Log reports and media data of this Certification Center are retained for at least 7 years; records of CA certificate and key lifecycle events are in addition retained until at least 2 years after the later of the destruction of the CA Private Key and the revocation or expiration of the final CA certificate sharing the corresponding Public Key.

### 5.4.4 Protection of audit log

- Only authorized personnel may read the Audit Logs, and only authorized personnel may back up the Audit Logs.
- Signature or encryption technology is used to preserve current and archived electronic Audit Logs, which are stored on write-once optical discs or other media that cannot alter the Audit Log records.
- Keys used to protect event logs shall not be used for any other purpose.
- Paper and physical Audit Logs are stored in a secure location.

### 5.4.5 Audit log backup procedures

Electronic Audit Logs are backed up once per month and stored at a backup location outside of this Certification Center.

### 5.4.6 Audit collection System (internal vs. external)

The audit system is built into the certificate management system of this Certification Center. The audit process is activated when the certificate management system starts and is only stopped when the certificate management system is shut down.

If the automated audit system cannot operate normally and the security mechanisms protecting system data integrity and confidentiality are in a high-risk state, this Certification Center will suspend certificate issuance services until the issue is resolved.

### 5.4.7 Notification to event-causing subject

If an event is recorded by the audit system, the audit system is not required to notify the individual who caused the event that the event has been recorded by the system.

### 5.4.8 Vulnerability assessments

The following Vulnerability Assessments are conducted once per year:

- Identify foreseeable internal and external threats that may result in unauthorized access, information disclosure, information misuse, data tampering, or destruction of any certificate data or certificate management processes.
- Assess the likelihood of threats occurring and the potential damage to certificate data and certificate management processes if they occur.
- Assess whether the current applicable information security policies, management procedures, information technology, and other protective measures of this Certification Center are sufficient to defend against threats.

This Certification Center additionally performs the following, as required by the NCSSR:

- **Vulnerability scanning**: each system listed in the CA Infrastructure inventory undergoes a vulnerability scan every 3 months, and additionally following any major infrastructure or application change. The review, response, and remediation time limits for identified vulnerabilities are set out in [Section 6.7](#67-network-security-controls).
- **Penetration testing**: performed every 12 months, and additionally following any infrastructure or application change defined by the Company as major.
- **Change management process**: reviewed every 12 months and updated as required.
- **Monitoring and logging policies and procedures**: reviewed and updated every 12 months.

## 5.5 Records archival

### 5.5.1 Types of records archived

The Archive Records of this Certification Center include the following types:

- Accreditation-verified data.
- Certification Practice Statement.
- Subscriber agreements.
- System and equipment configuration settings.
- Content of system or configuration modifications and updates.
- Certificate application data.
- Revocation application data.
- Certificate acceptance confirmation documents.
- Issued or published certificates.
- Records of key changeover.
- Issued or published CRLs.
- Audit Logs.
- Other explanatory materials or applications used to verify and corroborate archived content.
- Documents required by independent auditors.
- Subscriber identification and authentication data.

### 5.5.2 Retention period for archive

The archived data of this Certification Center is retained for at least 7 years; archived data relating to CA certificates and keys is in addition retained until at least 2 years after the later of the destruction of the CA Private Key and the revocation or expiration of the final CA certificate sharing the corresponding Public Key.

### 5.5.3 Protection of archive

Archived data shall not be written to, modified, or deleted. Individual archived data belonging to a Subscriber may be released to that Subscriber or to other institutions permitted by law.

Archived data must have one copy stored at an Off-site Backup / Disaster Recovery Site outside the location of this Certification Center, with security control measures and damage prevention measures for storage media.

### 5.5.4 Archive backup procedures

Key, certificate, transaction data, and other related data are organized, archived, and backed up on a daily, weekly, and monthly basis in accordance with backup and disaster recovery procedures. One copy is stored in a secure environment within the Company, and another copy is stored at a secure Off-site Backup environment. When the certificate system cannot be opened due to an anomaly, the certificate system recovery operation is performed using the preserved backup data in accordance with the system backup and recovery operation manual.

### 5.5.5 Requirements for time-stamping of records

Archived electronic records (e.g., certificates, CRLs, and Audit Logs) include date and time information, and these records are protected by appropriate digital signatures or cryptographic algorithms that can be used to detect whether the date and time information in the records has been tampered with. However, the date and time information in these electronic records is not electronic timestamp data provided by a neutral third party, but rather the date and time of the computer operating system.

All computer systems of this Certification Center are continuously synchronized with a trusted time source using the Network Time Protocol (NTP) (see [Section 6.8](#68-time-stamping)) to ensure the accuracy and reliability of the date and time information in electronic records.

Archived paper records also include date information, and time information when necessary. The date and time records in paper documents shall not be arbitrarily altered; if alteration is necessary, it must be confirmed with the signature of an Auditor.

### 5.5.6 Archive collection system (internal or external)

The archived record information related to the operations of this Certification Center is maintained by internal operational personnel of the Company, generated under resource accountability independence and secure control measures. The information preserved by the Audit Log collection system is also generated by internal control systems. Archived records of documents related to the operation of the certificate management system are collected and managed by personnel with the relevant business authority.

### 5.5.7 Procedures to obtain and verify archive information

A written application with formal authorization must be obtained before archived data can be accessed. The Auditor is responsible for verifying archived data; paper documents must be verified for the authenticity of the document issuer and date, while electronic files are verified through the digital signature of the archived data or by cryptographic means.

## 5.6 Key changeover

To reduce the risk of the signing key of this Certification Center being compromised, the signing key is renewed before the end of its usage period set out in [Section 6.3.2](#632-certificate-operational-periods-and-key-pair-usage-periods).

When the Subordinate CA performs key changeover, a new Key Pair is generated and submitted to the Root Certification Authority (RCA) for certificate issuance, then made available for download by Relying Parties in accordance with the provisions of [Section 6.1.4](#614-ca-public-key-delivery-to-relying-parties).

The key validity period for Subscribers takes into account key length, protection methods, control methods, and other various factors, and must not violate the provisions of [Section 6.1.5](#615-key-sizes) and [Section 6.3.2](#632-certificate-operational-periods-and-key-pair-usage-periods).

### 5.6.1 Subscriber Key Changeover

The Subordinate CA sets the lifecycle for Subscriber keys to be the same as the lifecycle of certificates issued by the Subordinate CA to Subscribers; that is, once the validity period of the Subscriber Certificate ends, the Subscriber key immediately becomes invalid and cannot be used.

Before the Subscriber key validity period expires, the Subscriber may generate a new Key Pair and apply to the Subordinate CA or Registration Authority for the issuance of a new certificate. Relevant operations are governed by the provisions of [Section 3.3.1](#331-identification-and-authentication-for-routine-re-key).

When an old key has security concerns and its validity period has not yet expired, the Subscriber must first apply to the Subordinate CA or Registration Authority to revoke the old certificate before generating a new Key Pair and applying for the issuance of a new certificate in accordance with the Registration Authority's operational specifications. Certificate revocation operations are governed by the provisions of [Section 4.9](#49-certificate-revocation-and-suspension).

### 5.6.2 Subordinate CA Key Changeover

The key used by the Subordinate CA to issue Subscriber Certificates has a validity period equal to the lifecycle of the corresponding certificate.

When the Subordinate CA performs key changeover, a new Key Pair is generated and submitted to the Root Certification Authority (RCA) for certificate issuance, then made available for download by Relying Parties in accordance with the provisions of [Section 6.1.4](#614-ca-public-key-delivery-to-relying-parties).

Before the Subordinate CA key validity period expires, a new Key Pair may be generated and submitted to the Root Certification Authority (RCA) for the issuance of a new certificate, with the Registration Authority immediately notified. Upon completion, the new Private Key is used to issue Subscriber Certificates, while the old key continues to sign CRLs until the end of the old key's lifecycle.

When the old key of the Subordinate CA has security concerns and its validity period has not yet expired, revocation of the old certificate must first be requested from the Root Certification Authority (RCA) before a new Key Pair can be generated and a new certificate issued. Upon completion, the new Private Key is used to issue Subscriber Certificates and CRLs, and Subscribers and the Registration Authority are immediately notified. All Subscriber Certificates and CRLs previously signed using the old Private Key of the Subordinate CA become invalid, and Subscribers must regenerate new Key Pairs and apply to the Subordinate CA for the issuance of new certificates.

### 5.6.3 Root Certification Authority (RCA) Key Changeover

The key used by the Root Certification Authority (RCA) to issue subordinate certificates has a validity period equal to the lifecycle of the corresponding certificate, not to exceed 9132 days (approximately 25 years). A Root CA newly created on or after July 1, 2026 is valid for no more than 10 years from the date of its submission to a Root Store Program.

Before the key validity period of the Root Certification Authority (RCA) expires, a new Key Pair and self-signed certificate are generated, and the new self-signed certificate is immediately published, with subordinate Certification Authorities immediately notified. The old key continues to sign CRLs until the end of the old key's lifecycle.

When the Root Certification Authority (RCA) has security concerns about a key whose certificate validity period has not yet expired, the certificate must first be revoked before a new Key Pair and self-signed certificate can be generated, with subordinate Certification Authorities immediately notified. At this point, all subordinate Certification Authority certificates become invalid, and they must regenerate new Key Pairs and apply to the Root Certification Authority (RCA) for the issuance of new certificates.

When the Private Key of the Root Certification Authority (RCA) is compromised, all subordinate Certification Authority certificates shall be revoked, and the subordinate Certification Authorities shall be notified to proceed with revoking all Subscriber Certificates and to notify business application systems to cease using certificates issued by the subordinate Certification Authorities.

## 5.7 Compromise and disaster recovery

### 5.7.1 Incident and compromise handling procedures

#### 5.7.1.1 Incident Response and Disaster Recovery Plan

If the Subordinate CA key is compromised or lost (even if it has not yet been confirmed whether compromise is possible), the following procedures must be carried out:

- All Subscribers and the Root Certification Authority (RCA) must be notified within 24 hours of becoming aware, via email or in writing.
- A new Key Pair is generated in accordance with [Section 6.1](#61-key-pair-generation-and-installation) and submitted to the Root Certification Authority (RCA) for the issuance of a new certificate.
- All issued certificates are revoked. The new signing key is used to sign the CRL, which includes information on all issued unexpired certificates (including revoked certificates issued before the Key Compromise).
- New certificates are issued to each Subscriber in accordance with the procedures of [Section 4.3](#43-certificate-issuance).
- Incident information is reported and disclosed to Relying Parties and Application Software Suppliers.

If the Root Certification Authority (RCA) key is compromised or lost, the following procedures must be carried out:

- All subordinate Certification Authorities must be notified within 24 hours of becoming aware, via email or in writing, to proceed with revoking all Subscriber Certificates.
- All issued certificates are revoked.
- A new Key Pair and self-signed certificate are generated in accordance with [Section 6.1](#61-key-pair-generation-and-installation).
- New certificates are issued to subordinate Certification Authorities.
- Incident information is reported and disclosed to Relying Parties and Application Software Suppliers.

This Certification Center must investigate and report to the PMA on the cause of the Key Compromise or loss, and the measures taken to prevent the same situation from recurring.

This Certification Center has established incident response handling procedures and a Disaster Recovery plan, documenting business continuity plans and Disaster Recovery procedures in writing. The content includes notification procedures for software vendors (e.g., browser vendors), Subscribers, and Relying Parties when disasters, security compromises, and operational interruption events occur. These procedures are tested, reviewed, and updated at least annually by this Certification Center.

This Certification Center defines an "Incident" as: any non-compliance with or violation of this CP/CPS, the CA/Browser Forum Baseline Requirements (such as S/MIME BR), or Root Store Policies (including the Apple Root Program Policy). Once this Certification Center becomes aware of any incident, it follows the reporting procedures of the CCADB Incident Reporting Guidelines: within 72 hours of becoming aware of the event, this Certification Center discloses a Preliminary or Full Incident Report in CCADB (including Bugzilla), or responds to a Preliminary Incident Report previously created for the incident by a third party reporter; a Full Incident Report is posted within 14 days of the incident’s initial disclosure. Thereafter, the report is updated on or before the "Next update" date recorded in the bug’s "Whiteboard" field; where no such date is recorded, at least every 7 days; and within 3 days of an Action Item being changed, completed, or delayed. For reports whose "Whiteboard" field contains "revocation-delay", updates are provided no less frequently than every 7 days. Comments and questions are answered within 7 days. These activities continue until the incident is closed.

#### 5.7.1.2 Mass Certificate Revocation Plan

This Certification Center has established a mass certificate revocation plan that details the procedures for handling mass certificate revocation events. The content includes "Source Confirmation," "Impact Scope Confirmation," "Internal Notification and Incident Response Team Organization," "Response Actions and Procedures," "Plan Training, Testing, and Continuous Improvement," and "Third-Party Assessment." Annual simulation exercises are conducted, and experiences gained from exercises or actual incidents are incorporated into the plan for continuous improvement and enhancement of response capabilities.

### 5.7.2 Computing resources, software, and/or data are corrupted

This Certification Center has established recovery procedures for computer resources, software, and data that have been damaged, and conducts exercises annually.

If the computer equipment of this Certification Center is damaged or inoperable but the signing key has not been compromised, priority is given to restoring the repository, followed by rebuilding certificate issuance, revocation, and management capabilities; each service is restored within the Recovery Time Objective (RTO) set out in the Company's Business Continuity Plan (BCP).

### 5.7.3 Entity private key compromise procedures

When a Subscriber's key is suspected of being compromised, the procedures specified in [Section 4.9.3](#493-procedure-for-revocation-request) shall be followed.

When a Certification Authority's key is suspected of being compromised, the procedures specified in [Section 5.7.1](#571-incident-and-compromise-handling-procedures) shall be followed.

### 5.7.4 Business continuity capabilities after a disaster

In the event of a natural disaster or other disaster where certificate status services cannot be restored within 24 hours, the Off-site Backup / Disaster Recovery Site facilities will be activated, and certificate status services will be restored within 24 hours after activation.

## 5.8 CA or RA termination

When this Certification Center terminates its services, it shall comply with the relevant provisions of the Electronic Signatures Act.

When this Certification Center ceases system operations for any reason, the impact on system operations must be minimized, and the relevant certificate operations must be securely transferred to another Certification Authority for continued operation.

Upon normal business termination, or contract termination, or corporate reorganization without security concerns:

- The competent authority shall be notified 30 days before the service termination date.
- Each Root Store Program is notified at least 120 days before any transfer of ownership or operational control.
- Subscribers shall be notified and the repository shall be updated 3 months before the service termination date regarding the service termination and the assumption of related business by another Certification Authority.
- Under an operationally secure environment, the relevant Private Keys and certificates of this Certification Center being terminated shall be transferred to the assuming Certification Authority.
- The Certificate Policy, Certification Practice Statement, related Certification Authority operational manuals, Subscriber agreements and registration data, Audit Logs, Archive Records, certificate status data, and other documents necessary for business succession shall be transferred to the assuming Certification Authority.
- After the transfer is completed, any remaining copies of the relevant Private Keys held by this Certification Center are destroyed, and a formal announcement shall be made to Subscribers that certificate operations have been transferred to the assuming Certification Authority for continued operation.
- Upon abnormal business termination (court-declared bankruptcy or illegality), this Certification Center must notify Subscribers of the facts within 24 hours of becoming aware and must execute the procedures for normal business termination to minimize the impact.
- When this Certification Center ceases business, the relevant rights and obligations shall also be handled in accordance with the Subscriber agreements.

# 6 TECHNICAL SECURITY CONTROLS

## 6.1 Key pair generation and installation

### 6.1.1 Key pair generation

Generation of Key Pairs for this Certification Center itself:

- A key generation script is established and followed.
- This Certification Center generates Key Pairs using hardware cryptographic modules validated as meeting at least FIPS 140-2 Level 3, FIPS 140-3 Level 3, or an appropriate Common Criteria Protection Profile or Security Target at EAL 4 or higher in accordance with [Section 6.2.1](#621-cryptographic-module-standards-and-controls). After the Private Key is generated within the hardware cryptographic module, it remains stored therein and is not disclosed.
- The Key Pair generation process is witnessed by a Qualified Auditor, and the entire process is recorded on video. After generation, the Qualified Auditor issues a report opining that this Certification Center followed its key ceremony (Key Generation Script) during its key and certificate generation process and the controls used to ensure the integrity and confidentiality of the Key Pair.

Generation of Key Pairs by Subscribers:

- Subscribers generate their Key Pairs in a secure manner on their own and properly safeguard their Private Keys; this Certification Center does not generate Subscriber Private Keys on their behalf.
- This Certification Center SHALL reject a Certificate Request if one or more of the following conditions are met:
  1. The Key Pair does not meet the requirements set forth in [Section 6.1.5](#615-key-sizes) and/or [Section 6.1.6](#616-public-key-parameters-generation-and-quality-checking);
  2. There is clear evidence that the specific method used to generate the Private Key was flawed;
  3. This Certification Center is aware of a demonstrated or proven method that exposes the Applicant's Private Key to compromise;
  4. The Applicant's Private Key has previously been reported to this Certification Center as compromised through the procedures in [Section 4.9.3](#493-procedure-for-revocation-request) and [Section 4.9.12](#4912-special-requirements-re-key-compromise), or this Certification Center has otherwise been made aware that the Applicant's Private Key has suffered a Key Compromise, such as through the provisions of [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate);
  5. This Certification Center is aware of a demonstrated or proven method to easily compute the Applicant's Private Key based on the Public Key (such as a Debian weak key).

### 6.1.2 Private key delivery to subscriber

Subscriber Private Keys are generated by the certificate Subscribers themselves; therefore, there is no delivery requirement. Parties other than the Subscriber do not archive the Subscriber's Private Key without the Subscriber's authorization. If this Certification Center or its Registration Authority becomes aware that a Subscriber's Private Key has been communicated to a person or organization not authorized by the Subscriber, this Certification Center revokes all certificates that include the Public Key corresponding to the communicated Private Key.

### 6.1.3 Public key delivery to certificate issuer

The Public Key is transmitted to this Certification Center via a PKCS#10 certificate request file. The transmission method must use a securely protected channel. Proof of Private Key possession shall be verified in the manner described in [Section 3.2.1](#321-method-to-prove-possession-of-private-key).

### 6.1.4 CA public key delivery to relying parties

This Certification Center shall publish the certificates it issues to the repository for Subscribers and Relying Parties to query and download.

### 6.1.5 Key sizes

This Certification Center’s key sizes and algorithm requirements are as follows:

For RSA key pairs:
* For Keys corresponding to CA Certificates (including Root, Subordinate and Cross Certificates) signed on or after September 15, 2026, the modulus size, when encoded, shall be at least 4096 bits; and
* For Keys corresponding to CA Certificates (including Root, Subordinate and Cross Certificates) signed before September 15, 2026, the modulus size, when encoded, shall be at least 2048 bits; and
* For Keys corresponding to Subscriber Certificates, the modulus size, when encoded, shall be at least 2048 bits; and
* The modulus size, in bits, must be evenly divisible by 8.
* Effective September 15, 2027, this Certification Center shall not issue S/MIME Subscriber Certificates containing `emailProtection` in the `extKeyUsage` extension from any CA if the CA Certificate's RSA Key modulus size, when encoded, is less than 3072 bits.

For ECDSA key pairs:
* The key must represent a valid point on the NIST P-256, NIST P-384, or NIST P-521 elliptic curve.

For EdDSA key pairs:
* The key must represent a valid point on the Curve25519 or Curve448 elliptic curve.

Where a Root Store Program requires a larger minimum key size for a Root CA certificate submitted for inclusion than is stated above — the Apple Root Program requires a minimum of RSA 4096 bits or ECDSA NIST P-384 — this Certification Center complies with that larger minimum, irrespective of the dates stated in this Section, in accordance with [Section 9.15](#915-compliance-with-applicable-law).

No other algorithms or key sizes are permitted.
### 6.1.6 Public key parameters generation and quality checking

For RSA key pairs: this Certification Center SHALL confirm that the value of the public exponent is an odd number equal to 3 or more. Additionally, the public exponent SHOULD be in the range between 2^16 + 1 and 2^256 - 1. The modulus SHOULD also have the following characteristics: an odd number, not the power of a prime, and have no factors smaller than 752.

For ECDSA key pairs: this Certification Center SHOULD confirm the validity of all keys using either the ECC Full Public Key Validation Routine or the ECC Partial Public Key Validation Routine.

For EdDSA key pairs: no stipulation.
### 6.1.7 Key usage purposes (as per X.509 v3 key usage field)

For certificates issued by this Certification Center, key usage purposes refer to the Key Usage and Extended Key Usage extensions described in [Section 7.1.2](#712-certificate-content-and-extensions-application-of-rfc-6818).
## 6.2 Private key protection and cryptographic module engineering controls

### 6.2.1 Cryptographic module standards and controls

This Certification Center uses a Hardware Security Module (HSM) validated as meeting at least FIPS 140-2 Level 3, FIPS 140-3 Level 3, or an appropriate Common Criteria Protection Profile or Security Target at EAL 4 or higher as the protection device for Private Keys, with Multi-person (m-of-n) Control capability.

### 6.2.2 Private key (n out of m) multi-person control

The Private Key activation data of this Certification Center is managed through Multi-person (m-of-n) Control using a Secret Sharing method, which is a Perfect Secret form of Secret Sharing that can be used for secure activation, backup, and recovery of Private Keys.

Smart Cards and personal passwords protecting Private Key-related information are managed by personnel with separate independent duties and stored in a secure environment with appropriate security controls.

### 6.2.3 Private key escrow

The Private Keys of this Certification Center are not permitted to be escrowed, nor does this Certification Center provide Private Key escrow services for Subscribers.

### 6.2.4 Private key backup

- The Private Key of this Certification Center is stored in the Hardware Security Module (HSM) and is backed up using the Multi-person (m-of-n) Control method described in [Section 6.2.2](#622-private-key-n-out-of-m-multi-person-control), with the Private Key encrypted before backup. The encryption key secret sharing information is stored on high-security Smart Cards.
- Smart Cards storing encryption key secret sharing information are kept in a dual-controlled secure environment, sealed and maintained by security control personnel.
- At least 2 copies of the encryption key secret sharing information are retained: one stored at a secure location within this Certification Center, and another stored at a secure Off-site Backup / Disaster Recovery Site.

### 6.2.5 Private key archival

The Private Keys of this Certification Center are not archived.

### 6.2.6 Private key transfer into or from a cryptographic module

The Private Key of this Certification Center is generated and stored within the Hardware Security Module (HSM). Only during key backup recovery can the Private Key be imported into another HSM. Export from the Cryptographic Module is handled in accordance with [Section 6.2.4](#624-private-key-backup).

### 6.2.7 Private key storage on cryptographic module

The Private Key of this Certification Center is stored in encrypted form in a Hardware Security Module (HSM) validated as meeting at least FIPS 140-2 Level 3, FIPS 140-3 Level 3, or an appropriate Common Criteria Protection Profile or Security Target at EAL 4 or higher, with Multi-person (m-of-n) Control capability.

### 6.2.8 Method of activating private key

The Private Key stored in the Cryptographic Module must be activated by 2 or more authorized Certificate Officers after identity authentication. Activation is performed through Smart Card-based authentication of Certificate Officer identity, and the activation procedure controls must comply with the provisions of [Section 5.2](#52-procedural-controls).

### 6.2.9 Method of deactivating private key

After the Private Key is activated, it is deactivated by either manually shutting down the Cryptographic Module after identity authentication or by automatic logout by the system after 15 minutes of inactivity, to prevent unauthorized use of the Private Key.

### 6.2.10 Method of destroying private key

When the Private Key usage period of this Certification Center expires, the key is destroyed in the following year in the presence of a Qualified Auditor. The memory locations storing the old Private Key in the Hardware Security Module (HSM) are zeroized to destroy the old Private Key in the HSM.

In addition to destroying the old Private Key in the HSM, backup copies of the old Private Key (three generations retained) are also physically destroyed when the backup expires. However, if the key backup copies must be used for restoration and the restored keys include expired keys, those expired keys are immediately deleted.

### 6.2.11 Cryptographic module rating

The Hardware Security Module (HSM) used by this Certification Center must be validated as meeting at least FIPS 140-2 Level 3, FIPS 140-3 Level 3, or an appropriate Common Criteria Protection Profile or Security Target at EAL 4 or higher. CNS 15135 or ISO/IEC 19790 may be used only as an additional standard, at security level 3, and not in place of the validation above. Any such Common Criteria Protection Profile or Security Target shall include requirements to protect the Private Key and other assets against known threats.

## 6.3 Other aspects of key pair management

### 6.3.1 Public key archival

When certificates issued by this Certification Center reach the end of their lifecycle, the certificates will be archived, and the Public Keys will be archived simultaneously.

### 6.3.2 Certificate operational periods and key pair usage periods

The Public Key and Private Key validity periods of this Certification Center are the same.

- The maximum Key Pair validity period for the Root Certification Authority (RCA) is 9132 days (approximately 25 years), including where the RCA's Public Key is also certified in a Cross Certificate. A Root CA newly created on or after July 1, 2026 is valid for no more than 10 years from the date of its submission to a Root Store Program.
- Key Pair validity periods for Subscribers: the maximum is 825 days.

## 6.4 Activation data

### 6.4.1 Activation data generation and installation

The activation data for the signing Private Key is individually generated by multiple smart cards, using a multi-person control duty separation (Duty Separation) mechanism. The activation data in the smart cards is accessed by card readers, and the smart card's Personal Identification Number (hereinafter referred to as PIN) is used for identity authentication when accessing the activation data.

### 6.4.2 Activation data protection

Activation data is protected by the controlling smart card set. The smart card PIN is kept by the custodian and shall not be recorded on any media. If the number of failed login attempts exceeds 3, the smart card shall be locked. When a smart card is transferred, the new custodian must set a new PIN.

### 6.4.3 Other aspects of activation data

No stipulation.

## 6.5 Computer security controls

### 6.5.1 Specific computer security technical requirements

This Certification Center and related auxiliary systems provide the following security control functions through the operating system, or through a combination of operating system, software, and physical protective measures:

- Identity authentication and multi-factor login capability.
- Customizable access control.
- Security audit capability.
- Access control restrictions for various certificate services and Trusted Roles.
- Identification and authentication of Trusted Roles and identities.
- Communication and database security.
- Secure and trusted channels for Trusted Roles and related identity identification.
- Process integrity and security control protection.

This Certification Center issues publicly trusted certificates trusted by browsers or computer operating systems; therefore, it has implemented information security control measures in accordance with the NCSSR.

### 6.5.2 Computer security rating

The computer system security of the systems used in the operations of this Certification Center shall have passed Common Criteria (CC, ISO/IEC 15408) GPOSPP (General Purpose Operating Systems Protection Profile) validation, or EAL4+ validation, or be approved for use through an internal security assessment.
## 6.6 Life cycle technical controls

### 6.6.1 System development controls

The system development of this Certification Center complies with the ISO 27001 standards.

The hardware and software of this Certification Center use only components that comply with the security policy. Hardware devices, network connections, or software components unrelated to operations are not installed. Each use includes a check for malicious code.

### 6.6.2 Security management controls

This Certification Center operates in compliance with ISO 27001 and the WebTrust Principles and Criteria for Certification Authorities.

When the software of this Certification Center is installed or updated, it is confirmed that the correct version has been provided by the developer and has not been modified. After system installation, the integrity of the software is verified at each startup.

This Certification Center records and controls changes to system configuration and functionality.

### 6.6.3 Life cycle security controls

This Certification Center annually reviews whether the current algorithms or keys are at risk of being compromised.

## 6.7 Network security controls

The Root Certification Authority (RCA) certificate system is an off-line, standalone management system that can only be operated manually by authorized operational personnel with the relevant business authority.

The certificate management system of this Certification Center requires authorization before operational personnel with the relevant business authority may perform management operations. When performing management operations, the certificate management system authenticates the identity of the operational personnel, and operations are permitted only after successful authentication.

To prevent network intrusion and sabotage, the hosts of this Certification Center are installed and configured with firewalls, intrusion prevention systems, and antivirus systems to enhance network security, system vulnerability scans are performed at least once every 3 months, penetration testing is performed in accordance with [Section 5.4.8](#548-vulnerability-assessments), and system patch updates are completed within the timeframes set out in the following table. This Certification Center classifies identified vulnerabilities using CVSS scoring together with a product context impact assessment, and ensures that review, response, and remediation are completed within the timeframes specified in the following table.:

| Severity | Reference criteria | Review deadline | Response deadline | Remediation / mitigation deadline |
|---|---|---|---|---|
| Critical | CVSS >= 9.0, or capable of immediately affecting core trust services, certificate issuance, or a large number of customers | Within 1 working day | Within 7 working days | Within 7 calendar days (or immediate temporary mitigation) |
| High | CVSS 7.0-8.9, capable of causing significant service disruption or data disclosure | Within 1 working day | Within 7 working days | Within 30 calendar days |
| Medium | CVSS 4.0-6.9, limited impact or requiring specific conditions to exploit | Within 1 working day | Within 7 working days | Within 90 calendar days |

Other vulnerabilities that do not reach the severity levels above are addressed in routine patching or version updates. Where a vulnerability is confirmed to be exploited in the wild, its severity is raised to at least "High" even if originally assessed as Medium or Low, and the accelerated handling process is initiated.

The hosts and internal databases of this Certification Center are connected only to the internal network and isolated by firewalls. Only internal host connections are permitted, and identity authentication is required to confirm that the person or system accessing the resources is authorized.

A remote connection that enables privileged access to the CA infrastructure of this Certification Center is permitted only where all of the following conditions are satisfied:

- **Originating workstation.** The connection originates from a notebook computer issued and controlled by the Company and dedicated to this purpose. The workstation is subject to the Company's information security monitoring, its operating system patches and anti-virus signatures are updated on a scheduled basis, and the transfer of files to or from the workstation requires an individually assigned USB device. The workstation is also bound, by its registered network interface, to the remote access account, and no other workstation may be used to connect.
- **Channel.** The connection is made through an encrypted virtual private network (VPN) channel. The channel is granted for a limited period and terminates when the workstation is shut down; no persistent channel is maintained.
- **Authentication.** The connection is authenticated using multi-factor authentication consisting of a smart card and a password.
- **Network boundary control.** The connection is made to the Company's VPN gateway, which is a network boundary control asset located within the Company's network, is secured in accordance with the NCSSR, and mediates the connection to the operational network segment in which the certificate systems reside.

Remote access does not confer any operational authority. The authorization and identity authentication requirements stated earlier in this Section apply to management operations performed remotely in the same manner as to operations performed on site, and the Root Certification Authority (RCA) certificate system remains off-line and is not reachable by any remote connection.

The repository is connected to the Internet, providing certificate, CRL, and OCSP query services on a 24x7 basis.

## 6.8 Time-stamping

The systems of this Certification Center are continuously synchronized with a trusted time source using the Network Time Protocol (NTP), to ensure the accuracy of the time values for various operations of this Certification Center, including but not limited to the following time values:

- Certificate issuance time.
- Certificate revocation time.
- CRL issuance time.
- OCSP issuance time.
# 7 CERTIFICATE, CRL, AND OCSP PROFILES

## 7.1 Certificate profile

The certificate serial numbers used by this Certification Center are encoded in a non-sequential, greater-than-zero and less-than-2^159 custom format, containing at least 64 bits of output generated by a Cryptographically Secure Pseudorandom Number Generator (CSPRNG).

Root CA certificates issued before the profile requirements of this Statement took effect and still within their validity period retain their original content, including their serial number, signature algorithm, key size (including the provisions of Section 6.1.5), and extensions.

### 7.1.1 Version number(s)

The version of certificates issued by this Certification Center and the certificates issued to Subscribers is X.509 v3, whose fields are as follows (field definitions comply with the [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) standard):

| Field | Description |
|-------|-------------|
| Version | Fixed as v3 |
| Serial Number | Certificate serial number |
| Signature Algorithm | The signature algorithm used to sign the certificate. Supported: sha256WithRSAEncryption, sha384WithRSAEncryption |
| Signature Value | The signature value generated by the issuer's signature |
| Issuer | Subject information of the CA corresponding to this certificate |
| Validity Not Before | Certificate start date |
| Validity Not After | Certificate expiration date |
| Subject | Subject DN of the certificate, see Section [3.1.1](#311-types-of-names) |
| Public Key | The public key corresponding to the certificate. Certification Authority certificates contain RSA keys; Subscriber Certificates may contain RSA, ECDSA, or EdDSA (Ed25519, Ed448) keys, with key sizes and parameters per [Section 6.1.5](#615-key-sizes) and algorithm object identifiers per [Section 7.1.3.1](#7131-subjectpublickeyinfo) |
| Extensions | See [Section 7.1.2](#712-certificate-content-and-extensions-application-of-rfc-6818) |

Fields not listed in the table above are not used by this Certification Center; the certificates it issues contain neither `issuerUniqueID` nor `subjectUniqueID`.

### 7.1.2 Certificate content and extensions; application of [RFC 6818](https://datatracker.ietf.org/doc/html/rfc6818)

The certificate extensions used by this Certification Center comply with the [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) standard and the requirements of [BR Section 7.1.2](https://cabforum.org/working-groups/smime/requirements/#712-certificate-content-and-extensions-application-of-rfc-6818).

#### 7.1.2.1 Root CA certificates

The Root CA (RCA) certificates of this Certification Center are self-signed. RCA certificates newly issued on or after the effective date of this Statement conform to the extension requirements in the table below; RCA certificates issued before these profile requirements took effect and still within their validity period retain their original content.

| Certificate Extension | Criticality | Description |
|-----------------------|-------------|-------------|
| basicConstraints | Critical | The `cA` field is set to true; `pathLenConstraint` is not set. |
| keyUsage | Critical | The `keyCertSign` and `cRLSign` bits are set; the RCA Private Key of this Certification Center is not used to sign OCSP responses, so `digitalSignature` is not set. |
| subjectKeyIdentifier | Non-critical | Its value is the `keyIdentifier` carried in the authorityKeyIdentifier extension of the certificates issued by that RCA. |
| authorityKeyIdentifier | Non-critical | Contains only the `keyIdentifier` field, whose value is identical to the subjectKeyIdentifier of the same certificate; it contains neither `authorityCertIssuer` nor `authorityCertSerialNumber`. |

Extensions other than those listed above are not used by this Certification Center.

#### 7.1.2.2 Subordinate CA certificates

For Subordinate CA certificates issued by this Certification Center, their extension fields must comply with the table below:

| Certificate Extension | Criticality | Description |
|-----------------------|-------------|-------------|
| certificatePolicies | Non-critical | Includes policyIdentifiers in accordance with [Section 7.1.6.3](#7163-subordinate-ca-certificates), and may include a CPS policy qualifier (id-qt-cps) whose value is an HTTP or HTTPS URL. |
| cRLDistributionPoints | Non-critical | Contains the HTTP URL of the CA's CRL service. |
| authorityInformationAccess | Non-critical | Contains the HTTP URL of the Issuing CA Certificate (accessMethod = id-ad-caIssuers), and MAY contain the HTTP URL of the Issuing CA OCSP responder (accessMethod = id-ad-ocsp). |
| basicConstraints | Critical | The cA field SHALL be set true, and pathLenConstraint is set to 0. For Cross Certificates, pathLenConstraint is not set. |
| keyUsage | Critical | Bit positions for keyCertSign and cRLSign SHALL be set, and may contain digitalSignature. |
| extKeyUsage | Non-critical | Does not assert `anyExtendedKeyUsage` (OID: 2.5.29.37.0). The EKU asserts either `id-kp-emailProtection` (OID: 1.3.6.1.5.5.7.3.4) together with `id-kp-clientAuth` (OID: 1.3.6.1.5.5.7.3.2), or `id-kp-emailProtection` alone. Under Appendix A of the Apple Root Program Policy those two combinations correspond to the Legacy S/MIME and Secure Email Trust Purposes respectively, and each is dedicated to a single Trust Purpose. |
| authorityKeyIdentifier | Non-critical | SHALL contain a keyIdentifier field and SHALL NOT contain authorityCertIssuer or authorityCertSerialNumber fields. |
| subjectKeyIdentifier | Non-critical | Contains a value used in the keyIdentifier field of the authorityKeyIdentifier extension in Certificates issued by the Subordinate CA. |

Extensions other than those listed above are not used by this Certification Center.

The following two Cross Certificates listed in Section 7.1.4.3.2 were issued before the BR took effect on September 1, 2023 (the certificate issued by TWCA Root Certification Authority to TWCA Global Root CA on October 28, 2014, and the certificate issued by TWCA Global Root CA to TWCA Global Root CA G2 on December 9, 2022) and retain their original content: their basicConstraints extension sets cA to true and does not set pathLenConstraint; they contain no extKeyUsage extension; their certificatePolicies extension contains only anyPolicy with an id-qt-cps qualifier; and their authorityInformationAccess extension contains only the id-ad-ocsp access method. Cross Certificates issued on or after September 1, 2023, including the Cross Certificate issued by TWCA Global Root CA to TWCA SMIME Root CA G1, conform to this section.

#### 7.1.2.3 Subscriber certificates

The Extension settings for Subscriber Certificates issued by the Subordinate CA are as follows. The table below lists only the extensions actually used by this Certification Center; extensions not listed are not used:

| Certificate Extension | Criticality | Description |
|-----------------------|-------------|-------------|
| authorityKeyIdentifier | Non-critical | Uses the SHA-1 algorithm. |
| subjectKeyIdentifier | Non-critical | Uses the SHA-1 or SHA-256 algorithm. |
| cRLDistributionPoints | Non-critical | Contains the CRL download location; every URI uses the HTTP scheme. |
| subjectAltName | Non-critical | MUST and can only contain `rfc822Name` representing subscriber's Mailbox Address; this Certification Center does not use the `otherName` of type `id-on-SmtpUTF8Mailbox` permitted by [BR Section 7.1.4.2.1](https://cabforum.org/working-groups/smime/requirements/#71421-subject-alternative-name-extension). |
| authorityInformationAccess* | Non-critical | Contains CA Issuers (accessMethod=1.3.6.1.5.5.7.48.2) (required), Online Certificate Status Protocol (accessMethod=1.3.6.1.5.5.7.48.1) (optional); every URI uses the HTTP scheme. |
| certificatePolicies | Non-critical | Contains certificatePolicies:policyIdentifier, with the values specified in [Section 7.1.6.4](#7164-subscriber-certificates); no policyQualifiers are included. |
| basicConstraints | Non-critical | cA=false; pathLenConstraint is not set. |
| keyUsage | Critical | Depends on the certificate profile and key algorithm:<br>**1. Strict Profile**<br>- RSA keys: digitalSignature, keyEncipherment; dataEncipherment MUST NOT be present.<br>- ECC keys: digitalSignature, keyAgreement; keyEncipherment MUST NOT be present.<br>**2. Multipurpose Profile**<br>- RSA keys: digitalSignature, nonRepudiation (optional), keyEncipherment, dataEncipherment (optional).<br>- ECC keys: digitalSignature, nonRepudiation (optional), keyAgreement (optional); keyEncipherment MUST NOT be present.<br>**3. EdDSA keys (same for the Strict and Multipurpose Profiles)**<br>- EdDSA keys (Ed25519, Ed448): digitalSignature, nonRepudiation (optional).<br>No other bit positions are set for any profile or key algorithm (per item e of [BR Section 7.1.2.3](https://cabforum.org/working-groups/smime/requirements/#7123-subscriber-certificates)). |
| extKeyUsage | Non-critical | Depends on the certificate profile:<br>- Strict Profile: emailProtection (1.3.6.1.5.5.7.3.4) only; clientAuth MUST NOT be present.<br>- Multipurpose Profile: emailProtection (1.3.6.1.5.5.7.3.4) (required), clientAuth (1.3.6.1.5.5.7.3.2) (optional). |

\* Authority Information Access: Starting from March 15, 2024, the Online Certificate Status Protocol is no longer required information.

#### 7.1.2.4 All certificates

All other Extensions must comply with the [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) standard and the requirements of [BR Section 7.1.2.4](https://cabforum.org/working-groups/smime/requirements/#7124-all-certificates).

#### 7.1.2.5 Application of RFC 5280

Precertificates are not issued by this Certification Center.

### 7.1.3 Algorithm object identifiers

#### 7.1.3.1 SubjectPublicKeyInfo

The key identifiers used by this Certification Center when issuing certificates are as follows:

| Key Algorithm | Object Identifier (OID) |
|---------------|------------------------|
| rsaEncryption | {iso(1) member-body(2) us(840) rsadsi(113549) pkcs(1) pkcs-1(1) rsaEncryption(1)} (1.2.840.113549.1.1.1) |
| ecPublicKey | {iso(1) member-body(2) us(840) ansi-X9-62(10045) keyType(2) ecPublicKey(1)} (1.2.840.10045.2.1) |
| Ed25519 | {iso(1) identified-organization(3) 101 id-Ed25519(112)} (1.3.101.112) |
| Ed448 | {iso(1) identified-organization(3) 101 id-Ed448(113)} (1.3.101.113) |

#### 7.1.3.2 Signature AlgorithmIdentifier

The signature algorithm object identifiers used by this Certification Center when issuing certificates are as follows:

| Signature Algorithm | Object Identifier (OID) |
|---------------|------------------------|
| sha256WithRSAEncryption | {iso(1) member-body(2) us(840) rsadsi(113549) pkcs(1) pkcs-1(1) sha256WithRSAEncryption(11)} (1.2.840.113549.1.1.11) |
| sha384WithRSAEncryption | {iso(1) member-body(2) us(840) rsadsi(113549) pkcs(1) pkcs-1(1) sha384WithRSAEncryption(12)} (1.2.840.113549.1.1.12) |

All Certification Authority keys of this Certification Center are RSA keys; this Certification Center therefore signs certificates, CRLs, and OCSP responses only with the RSA signature algorithms listed above. Subscribers may request certificates for RSA, ECDSA, or EdDSA keys; the public key algorithms are listed in [Section 7.1.3.1](#7131-subjectpublickeyinfo).

### 7.1.4 Name forms

#### 7.1.4.1 Name encoding

The certificates of this Certification Center and Subscribers use X.500 Distinguished Name (DN) naming conventions for the certificate subject and issuer names. The attribute types of these names comply with the relevant provisions of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280).

For all certificates issued by this Certification Center, the binary DER encoding of the Issuer DN field MUST be byte-for-byte identical to the binary DER encoding of the Subject DN field in the Issuing CA's certificate. All CA Certificates whose Subject DNs compare as equal under Section 7.1 of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280), including expired and revoked Certificates, have byte-for-byte identical Subject DN encodings.

#### 7.1.4.2 Subject information: subscriber certificates

For Subscriber Certificates issued by this Certification Center, each attribute in the subject shall not use incomplete, inapplicable, or default values.

##### 7.1.4.2.1 Subject alternative name extension

Certificates MUST have a subjectAltName (hereinafter referred to as SAN) extension, and the SAN extension MUST contain at least one `rfc822Name` Mailbox Address.

##### 7.1.4.2.2 Subject distinguished name fields

The Distinguished Names of Subscriber Certificates issued by this Certification Center are as follows:

**Organization-validated Certificate**

The table below lists only the attributes actually used by this Certification Center; attributes not listed are not used.

| Distinguished Name (DN) | Description | DN Content Example |
| --- | --- | --- |
| Country(C) | Country of the certificate subject | TW |
| Organization(O) | Certificate Applicant organization information | My Company |
| CommonName(CN) | Distinguished name of the certificate Applicant; must be a Mailbox Address contained in the Subject Alternative Name (SAN) extension | test@twca.com.tw |
| OrganizationIdentifier(ORGID) | Organization identifier for businesses, organizations, or government entities. Its definition and format refer to BR Section 7.1.4.2.2 and [Appendix A](https://cabforum.org/working-groups/smime/requirements/#appendix-a---registration-schemes):<br>1. For businesses and organizations, the VAT scheme is used: "VATTW-" plus the 8-digit Unified Business Number (UBN), e.g., VATTW-70759028.<br>2. Government entities, which have no identifier from the Registration Schemes above, use the GOV scheme in accordance with Note 2 of BR Section 7.1.4.2.2: the value is "GOVTW" with no registration reference appended. | VATTW-70759028<br>GOVTW |

Note 1: Field definitions are primarily governed by BR Section 7.1.4, and the certificate policy field must contain the Organization-validated OID defined by CA/B in [Section 7.1.6.4](#7164-subscriber-certificates) of this document.

Note 2: Pursuant to BR Section 7.1.4.2.4, Organization-validated certificates SHALL NOT contain `givenName`, `surname`, `pseudonym`, and `title` attributes.

##### 7.1.4.2.3 Subject DN attributes for mailbox-validated profile

Not applicable. This Certification Center does not issue Mailbox-validated certificates; see [Section 3.2](#32-initial-identity-validation).

##### 7.1.4.2.4 Subject DN attributes for organization-validated profile

As set out in [Section 7.1.4.2.2](#71422-subject-distinguished-name-fields). This Certification Center issues Organization-validated certificates only.

##### 7.1.4.2.5 Subject DN attributes for sponsor-validated profile

Not applicable. This Certification Center does not issue Sponsor-validated certificates; see [Section 3.2.4](#324-authentication-of-individual-identity).

##### 7.1.4.2.6 Subject DN attributes for individual-validated profile

Not applicable. This Certification Center does not issue Individual-validated certificates; see [Section 3.2.4](#324-authentication-of-individual-identity).

#### 7.1.4.3 Subject information: root certificates and subordinate CA certificates

The self-signed certificates issued by the Root Certification Authority (RCA) and the certificates of the Subordinate CA are issued in accordance with the certificate policy, ensuring that all subject information is correct prior to issuance.

##### 7.1.4.3.1 Subject distinguished name fields

The organizationName in the subject of this Certification Center's CA certificates is "TAIWAN-CA" or "TAIWAN-CA Inc.", both of which represent the Company's legal English name "TAIWAN-CA INC."; "TAIWAN-CA" omits the company-type suffix "INC.".

The Distinguished Names of the Subordinate CA certificates are:

| Distinguished Name (DN) |
|-------------------------|
| C=TW, O=TAIWAN-CA Inc., OU=User CA, CN=TWCA InfoSec User CA |
| C=TW, O=TAIWAN-CA, CN=TWCA SMIME Certification Authority |

The Distinguished Names of the Root Certification Authority (RCA) certificates are:

| Distinguished Name (DN) |
|-------------------------|
| C=TW, O=TAIWAN-CA, OU=Root CA, CN=TWCA Root Certification Authority |
| C=TW, O=TAIWAN-CA, OU=Root CA, CN=TWCA Global Root CA |
| C=TW, O=TAIWAN-CA, OU=Root CA, CN=TWCA Global Root CA G2 |
| C=TW, O=TAIWAN-CA, CN=TWCA SMIME Root CA G1 |

##### 7.1.4.3.2 Certificate hierarchy mapping

The trust paths and scope of applicability of the certificate hierarchy governed by this Statement are as follows.

**Current issuance hierarchy**

| Tier | Certificate Common Name (CN) | Description |
|---|---|---|
| Root Certification Authority (RCA) | TWCA Global Root CA | Self-signed certificate; the trust anchor of the current S/MIME issuance hierarchy. |
| Subordinate CA | TWCA InfoSec User CA | Issued by "TWCA Global Root CA". Currently issues S/MIME certificates (Organization-validated type, in both the multipurpose and strict profiles). |
| Subscriber Certificate (EE) | — | Profiles are set out in [Section 7.1.2.3](#7123-subscriber-certificates) and [Section 7.1.4.2](#7142-subject-information-subscriber-certificates). |

**Successor issuance hierarchy**

Issuance of S/MIME certificates is being migrated from the current issuance hierarchy to the following hierarchy:

| Tier | Certificate Common Name (CN) | Description |
|---|---|---|
| Root Certification Authority (RCA) | TWCA Global Root CA G2 | Self-signed certificate, dedicated to the S/MIME Trust Purposes. |
| Subordinate CA | TWCA InfoSec User CA | Issued by "TWCA Global Root CA G2". |
| Subscriber Certificate (EE) | — | Profiles are set out in [Section 7.1.2.3](#7123-subscriber-certificates) and [Section 7.1.4.2](#7142-subject-information-subscriber-certificates). |

| Tier | Certificate Common Name (CN) | Description |
|---|---|---|
| Root Certification Authority (RCA) | TWCA SMIME Root CA G1 | Self-signed certificate, dedicated to the S/MIME Trust Purposes. |
| Subordinate CA | TWCA SMIME Certification Authority | Issued by "TWCA SMIME Root CA G1". |
| Subscriber Certificate (EE) | — | Profiles are set out in [Section 7.1.2.3](#7123-subscriber-certificates) and [Section 7.1.4.2](#7142-subject-information-subscriber-certificates). |

**Cross Certificates**

To extend the compatibility of the trust path, this Certification Center also issues the following Cross Certificates:

| Subject of the Cross Certificate | Issuer of the Cross Certificate |
|---|---|
| TWCA Global Root CA G2 | TWCA Global Root CA |
| TWCA SMIME Root CA G1 | TWCA Global Root CA |
| TWCA Global Root CA | TWCA Root Certification Authority |

**Scope of applicability**

All operational practices, validation procedures, and certificate and CRL profiles set out in this Statement apply to each Root CA certificate and each Subordinate CA certificate listed in [Section 7.1.4.3.1](#71431-subject-distinguished-name-fields) (including the Cross Certificates listed above), and to all S/MIME Subscriber Certificates issued by them. Every certificate containing the `id-kp-emailProtection` Extended Key Usage is issued and managed in accordance with this Statement. This Statement does not cover any CA certificate outside the foregoing lists.

##### 7.1.4.3.3 Transition of multi-Trust-Purpose Root CA certificates to single-purpose operation

"TWCA Global Root CA G2" and "TWCA SMIME Root CA G1", the trust anchors of the successor issuance hierarchy set out in [Section 7.1.4.3.2](#71432-certificate-hierarchy-mapping), are dedicated to the S/MIME Trust Purposes.

"TWCA Global Root CA", the trust anchor of the current issuance hierarchy, is in addition to the S/MIME Trust Purposes covered by this Statement also the starting point of the trust path for the Company's TLS hierarchy (whose operational practices are set out in the Company's separately published "TAIWAN-CA INC. CYBER Certification Authority Certificate Policy and Certification Practice Statement (TWCA CYBER CA CP/CPS)"); "TWCA Global Root CA" is also the issuer of the Cross Certificates for "TWCA Global Root CA G2" and "TWCA SMIME Root CA G1"; and "TWCA Root Certification Authority" is the issuer of the Cross Certificate for "TWCA Global Root CA". Those two Root CA certificates are therefore the starting point of the trust path for both Trust Purposes.

This Certification Center proceeds as follows:

1. Issuance of S/MIME certificates is migrated to the successor issuance hierarchy set out in [Section 7.1.4.3.2](#71432-certificate-hierarchy-mapping). Under [Section 6.1.5](#615-key-sizes), from September 15, 2027 a CA certificate whose RSA key has a modulus length of less than 3072 bits no longer issues S/MIME Subscriber Certificates containing `emailProtection`; this Certification Center completes the migration in line with that timetable.
2. By December 31, 2028, one of the trust bits of "TWCA Root Certification Authority" and "TWCA Global Root CA" is removed, or those root certificates are sunset; the related requests are submitted to the CCADB early enough for this to be completed by that date.
3. Until the migration is complete, this Certification Center operates each Trust Purpose associated with those two Root CA certificates in accordance with this Statement and with the TWCA CYBER CA CP/CPS respectively.
4. Progress of the migration is disclosed in Bugzilla, and this Statement is revised in accordance with [Section 9.12](#912-amendments).

### 7.1.5 Name constraints

Certificates issued by this Certification Center do not use the nameConstraints extension.

### 7.1.6 Certificate policy object identifier

Certificates issued by this Certification Center include the Certificate Policy Object Identifier defined by the Certificate Policy in the certificatePolicies extension within the certificate.

#### 7.1.6.1 Reserved Certificate Policy Identifiers

The following Certificate Policy identifiers are reserved for use by CABF SBR:

| Object Identifier | Purpose |
|-------------------|-------|
| {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) smime-baseline(5) organization-validated(2) multipurpose(2)} (2.23.140.1.5.2.2) | Used for S/MIME certificates of the Multipurpose profile |
| {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) smime-baseline(5) organization-validated(2) strict(3)} (2.23.140.1.5.2.3) | Used for S/MIME certificates of the Strict profile |

#### 7.1.6.2 Root Certification Authority Certificates

Root Certification Authority (RCA) certificates do not contain the Certificate Policies extension.

#### 7.1.6.3 Subordinate CA Certificates

Subordinate CA certificates contain the Certificate Policies extension, using the following Certificate Policy identifiers:

| Certificate Type | Object Identifier |
|------------------|-------------------|
| S/MIME CA Certificate | anyPolicy (2.5.29.32.0) |

#### 7.1.6.4 Subscriber Certificates

Subscriber Certificates issued by the Subordinate CA contain the Certificate Policies extension, using the following Certificate Policy identifiers:

| Certificate Type | Object Identifier |
|------------------|-------------------|
| S/MIME Certificate (Multipurpose profile) | {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) smime-baseline(5) organization-validated(2) multipurpose(2)} (2.23.140.1.5.2.2); {ISO(1) identified-organization(3) dod(6) internet(1) private(4) enterprise(1) TWCA(40869) certificates(1) policies(1) SMIME(28)} (1.3.6.1.4.1.40869.1.1.28) |
| S/MIME Certificate (Strict profile) | {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) smime-baseline(5) organization-validated(2) strict(3)} (2.23.140.1.5.2.3); {ISO(1) identified-organization(3) dod(6) internet(1) private(4) enterprise(1) TWCA(40869) certificates(1) policies(1) SMIME(28)} (1.3.6.1.4.1.40869.1.1.28) |

### 7.1.7 Usage of policy constraints extension

Certificates issued by this Certification Center do not use the policyConstraints extension.

### 7.1.8 Policy qualifiers syntax and semantics

The certificatePolicies extension of the Subordinate CA certificates issued by this Certification Center may contain a CPS policy qualifier (id-qt-cps); Subscriber Certificates contain no policy qualifiers (see [Section 7.1.2.3](#7123-subscriber-certificates)).

### 7.1.9 Processing semantics for the critical certificate policies extension

No stipulation.

## 7.2 CRL profile

The service URL can be obtained from the CRL Distribution Points (cRLDistributionPoints) extension of Subscriber Certificates. The frequency at which this Certification Center issues CRLs is specified in [Section 4.9.7](#497-crl-issuance-frequency).

For each Certification Authority, this Certification Center issues a single CRL whose scope covers all certificates issued by that Certification Authority, signed with that Certification Authority's Private Key; this Certification Center does not issue partitioned CRLs. CRLs covering Subscriber Certificates contain an Issuing Distribution Point extension; CRLs covering Subordinate CA certificates do not.

### 7.2.1 Version number(s)

This Certification Center issues CRLs in X.509 v2 format, compliant with [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280), with the following fields:

| Field | Description |
|-------|-------------|
| Version Number | Fixed as v2 |
| Issuer | Subject DN of the Issuing CA. Its encoding is byte-for-byte identical to the encoding of the `subject` field of the CA certificate that issued this CRL |
| This Update | CRL issuance time (`thisUpdate`) |
| Next Update | The date by which the next CRL will be issued (`nextUpdate`). For CRLs covering Subscriber Certificates, no more than 10 days after `thisUpdate`; for CRLs covering Subordinate CA certificates, no more than 12 months after `thisUpdate`. The currently scheduled value is 1 day in both cases. This Certification Center may adjust these configured values as operationally required, provided that the adjusted values remain within the limits stated above |
| Signature Algorithm | The signature algorithm used for issuing the CRL. This Certification Center supports: sha256WithRSAEncryption, sha384WithRSAEncryption. Its encoded value is byte-for-byte identical to `tbsCertList.signature` |
| Revoked Certificates List | List of revoked certificates, including certificate serial number and revocation time; for CRL entry extensions, see [Section 7.2.2](#722-crl-and-crl-entry-extensions) |
| Extensions | CRL extensions; see [Section 7.2.2](#722-crl-and-crl-entry-extensions) |
| Signature Value | Signature value generated by the issuer's signing |

Fields not listed in the table above are not used by this Certification Center.

### 7.2.2 CRL and CRL entry extensions

The CRLs issued by this Certification Center contain the following Extensions:

| Extension | Criticality | Description |
|-----------|--------|-------------|
| CRL Number | Non-critical | The CRL Number (crlNumber) extension. This extension MUST contain an INTEGER greater than or equal to zero (0) and less than 2^159, conveying a strictly increasing sequence. |
| Authority Key Identifier | Non-critical | Identifies the Issuing CA |
| Issuing Distribution Point | Critical | Present only in CRLs issued by the Subordinate CA covering Subscriber Certificates; with its distributionPoint field recording the publication address of that CRL. CRLs issued by a Root Certification Authority covering Subordinate CA certificates do not contain this extension |
| Reason Code | Non-critical | Identifies the reason for certificate revocation (see description below) |

The permitted revocation reasons for Subscriber Certificates are: Key Compromise (1), Affiliation Changed (3), Superseded (4), Cessation of Operation (5), and Privilege Withdrawn (9). Reason codes not listed above are not used; where the reason for revocation of a Subscriber Certificate is not one of those listed, the reasonCode entry extension is omitted, whereas CRL entries for CA certificates always record a revocation reason.

The revocation reason codes for CA certificates (including Cross Certificates) are as follows, corresponding to the reasons listed in [Section 4.9.1.2](#4912-reasons-for-revoking-a-subordinate-ca-certificate):

- keyCompromise (1): the Private Key of that CA has been compromised, or a method that can compromise that Private Key is known.
- affiliationChanged (3): the Subject information in that CA certificate has changed.
- superseded (4): that CA certificate has been replaced by a new certificate, or was not issued in accordance with, or no longer complies with, the BR or this Statement.
- cessationOfOperation (5): that CA has ceased operations or is no longer in use.
- privilegeWithdrawn (9): that CA certificate has been misused.

unspecified (0) and certificateHold (6) are not used for CA certificates. The revocationReason in OCSP responses is the same as in the CRL.

This Certification Center does not use the certificateHold (6) revocation reason for Root CA certificates or Subordinate CA certificates, including Cross Certificates.

The usage scenarios for each Reason Code are described below:

| Reason Code | Description |
|-------------|-------------|
| Key Compromise (1) | The CA obtains evidence that the Private Key has been compromised. The CA is made aware of a demonstrated or proven method that can compromise the Private Key. There is clear evidence that the method of generating the Private Key was flawed. The CA is made aware of a demonstrated or proven method to compute the Private Key from the Public Key (e.g., Debian Weak Key). When anyone (not limited to the Subscriber) requests certificate revocation and can prove current possession of the Private Key (per the proof method specified in the CA's CPS), the CA must revoke all certificates with the same Public Key, not limited to the requesting Subscriber's certificates. When a Subscriber requests certificate revocation but does not prove current possession of the Private Key, the CA may revoke that Subscriber's certificate, but shall not treat this as evidence that the Private Key has been compromised; this Certification Center blocks further issuance of certificates with this Public Key. |
| Affiliation Changed (3) | The Subscriber requests certificate revocation for this reason. The CA reissues a certificate due to a change in subject identity information, and there is no other reason for revocation. |
| Superseded (4) | The Subscriber requests certificate revocation for this reason. The CA revokes the certificate due to mailbox validation or compliance issues, and the issue is unrelated to Key Compromise or privilege withdrawal. |
| Cessation of Operation (5) | The Subscriber no longer owns or is no longer authorized to use the Mailbox Address in the certificate. The Subscriber is no longer affiliated with the Legal Entity or organization named in the certificate, or that Legal Entity or organization is no longer in operation. The CA is made aware that the Mailbox Address in the certificate can no longer be legally used, such as by court order. |
| Privilege Withdrawn (9) | The CA obtains evidence that the certificate has been misused. The CA is made aware that the Subscriber has violated the Subscriber agreement or Terms of Use. The CA is made aware that information in the certificate has changed. The CA determines or is made aware that information in the certificate is incorrect. The CA is made aware that the certificate application was not authorized. |

The DER encoding of the `issuer` field of a CRL issued by this Certification Center MUST be byte-for-byte identical to the encoding of the `subject` field of the CA certificate that issued that CRL.

## 7.3 OCSP profile

The service URL can be obtained from the Authority Information Access Extension of the Subscriber Certificate. The OCSP service provided by this Certification Center has the following characteristics:

- The signing certificate used for response messages is prohibited from using the SHA-1 algorithm and must be issued by this Certification Center.
- The signature value of response messages is prohibited from using the SHA-1 algorithm.
- The certificate statuses supported in response messages are: good, revoked, and unknown. For queries regarding unassigned (or unissued) certificate serial numbers (Unassigned Serial Numbers), the OCSP responder MUST NOT return a "good" status; it MUST return "revoked" or "unknown".
- When a status request is received for a certificate whose issuer is not served by the OCSP responder (including any certificate not issued by this Certification Center), the responder returns an "unauthorized" error response as defined in Section 2.3 of [RFC 6960](https://datatracker.ietf.org/doc/html/rfc6960#section-2.3).
- If an OCSP response is for a Root CA or Subordinate CA Certificate and that certificate has been revoked, then the `revocationReason` field within the `RevokedInfo` of the `CertStatus` MUST be present.
- The OCSP responses of this Certification Center are signed with the Private Key corresponding to a Delegated Responder certificate, that is, a certificate issued separately by the CA that issued the certificate being queried, dedicated to signing that CA's OCSP responses. That Delegated Responder certificate is issued by the issuer of the certificate being queried; its Extended Key Usage contains only OCSP signing (`id-kp-OCSPSigning`, OID: 1.3.6.1.5.5.7.3.9), and it contains the `id-pkix-ocsp-nocheck` extension (OID: 1.3.6.1.5.5.7.48.1.5).
- For other details, refer to [Section 4.9.9](#499-on-line-revocationstatus-checking-availability).

### 7.3.1 Version number(s)

The Online Certificate Status Protocol (OCSP) version of this Certification Center is 1.0, compliant with [RFC 6960](https://datatracker.ietf.org/doc/html/rfc6960). The OCSP response messages issued by this Certification Center contain the following fields:

| Field | Description |
|-------|-------------|
| Version | Fixed as v1 |
| Responder ID | In byKey form; its value is the SHA-1 hash of the OCSP responder certificate's public key (subjectPublicKey) |
| Produced At | OCSP response signing time |
| Certificate Status | This Certification Center supports the following certificate statuses: good, revoked, unknown. For queries regarding unassigned (or unissued) certificate serial numbers, it MUST NOT return a "good" status; it MUST return "revoked" or "unknown". |
| Validity Period | The validity period of the OCSP response, including ThisUpdate and NextUpdate times; for the validity interval, the currently configured value and the update timing, see [Section 4.9.9](#499-on-line-revocationstatus-checking-availability) |
| Signature Algorithm | The signature algorithm used for issuing the OCSP response. This Certification Center supports: sha256WithRSAEncryption, sha384WithRSAEncryption |
| Signature Value | Signature value generated by the OCSP responder signing the OCSP response |
| Signer Certificate | The certificate of the OCSP responder that signed this response, carried in the `certs` field of the response so that Relying Parties can verify the signature. It is issued by the CA that issued the certificate being queried and its Extended Key Usage contains only `id-kp-OCSPSigning`; it is therefore a Delegated Responder certificate as defined in RFC 6960. See [Section 7.3](#73-ocsp-profile) |

### 7.3.2 OCSP extensions

The Extensions used in the Online Certificate Status Protocol (OCSP) of this Certification Center comply with the [RFC 6960](https://datatracker.ietf.org/doc/html/rfc6960) specification; the singleExtensions of an OCSP response do not contain the reasonCode (OID: 2.5.29.21) extension.

# 8 COMPLIANCE AUDIT AND OTHER ASSESSMENTS

## 8.1 Frequency or circumstances of assessment

This Certification Center conducts at least 1 external audit per year and at least 1 internal audit per quarter. This Certification Center MUST upload the annual external audit report to CCADB within three (3) months of the end of the audit period.

Any key lifecycle event of the Root Certification Authority (RCA) and of the Subordinate CA — including key pair generation, backup, storage, recovery, transport and destruction — MUST be included within the scope of the annual external audit. Where such an event is not covered by the annual audit, this Certification Center MUST submit the audit or witness report for that event to the principal root programs (Application Software Suppliers), or to the CCADB, within ninety (90) days of the event.

## 8.2 Identity/qualifications of assessor

The audit personnel conducting internal and external audits for this Certification Center must possess at least knowledge of certification authority and information system security auditing, have more than 2 years of audit-related experience or certificate operations experience, and must be familiar with the operational specifications of this Statement, as well as have knowledge and experience in application systems and computer hardware/software systems. If the competent authority has relevant regulations regarding the qualification of audit personnel, those regulations shall prevail.

When conducting external audits, the commissioned audit firm must comply with the requirements of [BR Section 8.2](https://cabforum.org/working-groups/smime/requirements/#82-identityqualifications-of-assessor) and [CCADB Policy Section 5.3](https://www.ccadb.org/policy#53-audit-firm-and-audit-team-qualifications) and possess nationally recognized formal audit qualifications or internationally recognized audit credentials to provide fair and objective audit services. When conducting audits, this Certification Center will first verify the qualifications of the audit personnel, and after the audit is completed, the audit report will also list the audit credentials and certifications held by the audit personnel.

## 8.3 Assessor's relationship to assessed entity

Internal auditors performing audits for this Certification Center have independent roles and responsibilities separate from the audited units, with no conflicts of interest that could affect the objectivity of the audit, and they carry out assessments with an independent, impartial, and objective attitude.

External audits of this Certification Center will be conducted by a commissioned audit firm to audit the operations of this Certification Center.

## 8.4 Topics covered by assessment

The audit covers the following items:

- Whether the Certification Practice Statement and related operational standards have been established and published, including operational standards established in accordance with the Certification Practice Statement.
- Whether certificate management and related operations are performed in accordance with the Certification Practice Statement and related operational standards, to meet the integrity of certification services and the security control requirements of this Certification Center's environment.
- Whether this Statement complies with the requirements of the BR and the Root Store Programs.

The audit standards followed by this Certification Center are:

- WebTrust Principles and Criteria for Certification Authorities Version 2.2.2 or later.
- WebTrust Principles and Criteria for Certification Authorities – S/MIME Certificates Version 1.0.8 or later.
- WebTrust Principles and Criteria for Certification Authorities – Network Security Version 2.0.5 or later.

## 8.5 Actions taken as a result of deficiency

Upon completion of a full audit and assessment of this Certification Center's operations, if any non-compliance with the Certification Practice Statement is identified, the auditor shall list each deficiency according to its severity and notify this Certification Center. Upon receipt of the details, this Certification Center will handle them in accordance with its incident response procedures.

Every audit finding (including any qualification, qualified opinion, other matter, or non-conformity identified during an audit), and any other non-compliance that violates this CP/CPS, relevant baseline requirements (such as S/MIME BR), or Root Store Policies, is treated as an "Incident". This Certification Center commits to reporting and managing it in accordance with the CCADB Incident Reporting Guidelines and timelines: disclosing a Preliminary or Full Incident Report in CCADB (including Bugzilla) within 72 hours of becoming aware, posting a Full Incident Report within 14 days of the initial disclosure, and thereafter updating the report on or before the "Next update" date recorded in the bug’s "Whiteboard" field, or where no such date is recorded at least every 7 days, and within 3 days of an Action Item being changed, completed, or delayed, until the deficiency is fully corrected and the incident is closed. This Certification Center must propose corrective and preventive measures for the deficiencies and track subsequent improvement progress.

## 8.6 Communication of results

This Certification Center will publish previous WebTrust audit reports in the Repository. Additionally, the Company displays the international seals obtained on its official website; clicking the seal icon also allows viewing of the WebTrust audit reports.

## 8.7 Self audits

This Certification Center monitors its own adherence to this Statement and the BR and controls its service quality by performing self-audits on at least a quarterly basis, against a randomly selected sample including a minimum of the greater of thirty (30) certificates or three percent (3%) of the certificates issued by it during the period commencing immediately after the previous self-audit sample was taken.

This Certification Center uses a Linting process to verify the technical accuracy of the certificates within the selected sample set, independently of any previous linting performed on the same certificates.

## 8.8 Review of delegated parties

This Certification Center establishes its own Registration Authority and does not delegate the acceptance of certificate applications, identity verification, or certificate issuance to any third party; see [Section 1.3.2](#132-registration-authorities). Accordingly, the requirements of this section concerning the review of delegated parties are not applicable to this Certification Center.

## 8.9 Detailed Controls Report (hereinafter referred to as DCR)

Root Store Programs require a DCR for audit periods starting on or after July 1, 2027. This Certification Center's audit period runs from January 1 to December 31 each year; accordingly, this Certification Center MUST require the external auditor to prepare a DCR for audit periods starting on or after January 1, 2028 (that is, beginning with the audit period from January 1, 2028 to December 31, 2028). The requirements are as follows:
1. The contract terms with the auditor MUST permit this Certification Center to share the DCR with major Root Store Programs (Application Software Suppliers).
2. The Policy Management Authority (PMA) and CA management complete their review of the DCR before the attestation letter is finalized; and, at the time the corresponding audit report is submitted to the CCADB, add a formal attestation as a Case Comment on the 'CASE PROGRESS' tab of that "Add/Update Root Request" case, confirming that the DCR has been reviewed, that its content is accurate, and that corrective and preventive measures have been formulated for any control deficiencies identified.
3. This Certification Center MUST retain the DCR and all related review records for at least 7 years.
4. This Certification Center MUST ensure that, for each requirement tested, the DCR contains at least the following four core elements required by Root Store Programs:
   - The specific requirement or criterion being assessed.
   - The Company's control(s) that address the requirement.
   - The auditor's test procedures used to evaluate the control(s).
   - The results of the auditor's tests.

   For a WebTrust audit, this Certification Center MUST ensure the auditor prepares the report in accordance with the Detailed Controls Report process defined by CPA Canada.
5. Upon request by Root Store Programs, this Certification Center MUST provide the DCR report, and MUST provide it within 30 days of receiving the request.

# 9 OTHER BUSINESS AND LEGAL MATTERS

## 9.1 Fees

### 9.1.1 Certificate issuance or renewal fees

This Certification Center issues certificates to Subscribers and collects certificate fees from the Subscribers. Certificate fees are specified in the certificate application form, certificate quotation, Subscriber agreement, or published on this Certification Center's website.

### 9.1.2 Certificate access fees

No charge.

### 9.1.3 Revocation or status information access fees

No charge.

### 9.1.4 Fees for other services

No stipulation.

### 9.1.5 Refund policy

If a Subscriber applies for a refund after completing the certificate application but before the certificate has been issued, a processing fee of NTD 3,000 will be deducted, and the remainder will be refunded without interest. If the Subscriber applies for a refund after the certificate has been issued, the fees for the months used will be deducted proportionally, and then a processing fee of NTD 3,000 will be deducted, with the remainder refunded without interest.

## 9.2 Financial responsibility

### 9.2.1 Insurance coverage

Regarding risk management related to certification management operations, in addition to earthquake and fire insurance already obtained for buildings and hardware facilities, to diversify business operational risks, a general liability insurance policy of USD 2 million and a professional liability insurance policy of USD 5 million have been obtained.

### 9.2.2 Other assets

The financial operations audit related to the certificate business conducted by this Certification Center is regularly performed annually by a fair and objective third-party organization.

### 9.2.3 Insurance or warranty coverage for end-entities

- The verification service items and content provided by this Certification Center are all specified in [Section 1.4.1](#141-appropriate-certificate-uses) of this Statement. Content not specified in this Statement is excluded from indemnification liability.
- This Certification Center shall not be liable for damages arising from processing Subscriber registration data and certificate issuance, unless it has failed to follow this Statement, has violated applicable laws, or the damage is attributable to its intentional act or negligence.
- This Certification Center shall not be liable for damages caused to Subscribers due to force majeure events (e.g., earthquakes) or other causes not attributable to this Certification Center (e.g., war).
- If operational personnel of this Certification Center intentionally or negligently fail to follow this Statement, the Certificate Policy, and related operational specifications in performing registration, certificate issuance and revocation operations, or violate relevant legal regulations resulting in damage to Subscribers, this Certification Center shall compensate the Subscriber for damages in accordance with regulations, with the maximum compensation limited as specified in [Section 9.8](#98-limitations-of-liability) on limitation of liability.
- During the period after a request to revoke a Subscriber's certificate is submitted by this Certification Center or other authorized parties, until this Certification Center actually publishes the revocation of that Subscriber's certificate (recorded in the CRL), if legal disputes arise from the use of that Subscriber's certificate, this Certification Center shall not be liable for damages if it has performed processing operations in accordance with this Statement and related operational specifications.
- This Certification Center shall not be liable for damages caused by the use of illegally forged or erroneous certificates by Subscribers.
- The limitation period for Subscribers' damage claims shall be governed by relevant laws and regulations.

## 9.3 Confidentiality of business information

### 9.3.1 Scope of confidential information

Confidential Information includes:

- Private Keys and passwords used for the operations of this Certification Center.
- Key share data controlling the Private Keys of this Certification Center.
- Personal data of the certificate Applicant representatives and agents when Subscribers apply for certificates.
- Auditable and traceable records generated or maintained by this Certification Center.
- Audit records and documents generated by audit personnel during the audit process.
- Operations-related documents classified as confidential.

### 9.3.2 Information not within the scope of confidential information

The Certificate Policy, this Statement, certificates issued by this Certification Center, CRLs issued by this Certification Center, and external audit results are all publicly available information.

### 9.3.3 Responsibility to protect confidential information

Unless one of the following conditions is met, the Subscriber's basic registration data and identity verification-related data shall never be disclosed to management authorities or any other person:

- As required by laws and regulations and authorized by the management authority through legal procedures.
- When a court or arbitration institution with lawful jurisdiction processes disputes or arbitration arising from certificates and requests through legal procedures.

## 9.4 Privacy of personal information

### 9.4.1 Privacy plan

This Certification Center operates in accordance with the "Personal Data Protection Act and related regulations" and other relevant government regulations. Specific personal data and privacy management are specified in the certificate application form. The Company's "Personal Data Protection Policy and Privacy Statement" is published on the official website at https://www.twca.com.tw/privacy.

The company obtained the BS 10012 Personal Information Management System certificate in November 2013. The transition to BS 10012:2017 was conducted in July 2018, and the ISO/IEC 27701 Privacy Information Management System certificate was obtained on July 6, 2020; both have been continuously maintained as valid to date.

### 9.4.2 Information treated as private

All personal information about an individual that is not publicly available in the contents of a certificate is treated as private. Other matters are as specified in [Section 9.4.1](#941-privacy-plan).

### 9.4.3 Information not deemed private

No stipulation.

### 9.4.4 Responsibility to protect private information

In accordance with the Personal Data Protection Act of the Republic of China and relevant regulations, this Certification Center shall protect the personal information collected, processed, or used by it with appropriate security safeguards and a reasonable degree of care. This Certification Center has designated a personal data protection manager, and requires all employees and outsourcing service providers who handle personal information on behalf of this Certification Center to strictly comply with the personal information protection policies. This Certification Center shall not disclose any personal information of users to third parties, except as otherwise provided in this Statement or required by law.

### 9.4.5 Notice and consent to use private information

Except where the law provides otherwise, this Certification Center uses a Subscriber's personal information only to provide certificate issuance and management services. Before using personal information for any other purpose, this Certification Center gives the Subscriber notice and obtains the Subscriber's consent. Outsourcing service providers that handle personal information on behalf of this Certification Center must follow the same rules.

### 9.4.6 Disclosure pursuant to judicial or administrative process

As specified in [Section 9.3.3](#933-responsibility-to-protect-confidential-information).

### 9.4.7 Other information disclosure circumstances

As specified in [Section 9.3.3](#933-responsibility-to-protect-confidential-information).

## 9.5 Intellectual property rights

- The key pairs and key shares produced by this Certification Center are the intellectual property of the company.
- The certificates and CRLs issued by this Certification Center are the intellectual property of the company.
- The key pairs of Subscribers are the intellectual property of the Subscribers; however, when the Public Key is issued as a certificate by this Certification Center, that certificate is the intellectual property of the company.
- This Certification Center will ensure the accuracy of Subscriber names but does not guarantee the ownership of Intellectual Property Rights recorded in the Subject Distinguished Name of Subscriber Certificates.
- The intellectual property of documents written by this Certification Center in the course of performing certificate management operations is owned by the company.
- The Intellectual Property Rights of this Statement are owned by the company.
- This Statement may be freely downloaded from the Repository of this Certification Center and is publicly available for examination.
- **Licensing of this Statement**: this Certification Center makes this Statement available to Root Store Program operators (including but not limited to Apple, Google, Microsoft, and Mozilla) and to the general public under the terms of the Creative Commons Attribution-NoDerivatives 4.0 International licence (CC BY-ND 4.0, https://creativecommons.org/licenses/by-nd/4.0/ ). That licence applies to each historic version of this Statement.
- This Certification Center shall not bear any legal liability for any consequences arising from improper use of this Statement.

## 9.6 Representations and warranties

### 9.6.1 CA representations and warranties

- The Certificate Beneficiaries include:
  1. The Subscriber that is a party to the Subscriber Agreement or Terms of Use for the Certificate;
  2. All Application Software Suppliers with whom the Root CA has entered into a contract for inclusion of its Root Certificate in software distributed by such Application Software Supplier; and
  3. All Relying Parties who reasonably rely on a Valid Certificate.
- This Certification Center represents and warrants to the Certificate Beneficiaries that, during the period when the Certificate is valid, it has complied with the relevant Baseline Requirements (such as S/MIME BR) and this Certificate Policy and/or Certification Practice Statement in issuing and managing the Certificate.
- The Root CA (RCA) SHALL be responsible for the performance and warranties of the Subordinate CA, for the Subordinate CA's compliance with this Statement, and for all liabilities and indemnification obligations of the Subordinate CA under this Statement, as if the Root CA were the Subordinate CA issuing the Certificates.
- This Certification Center must fulfill its responsibility to properly safeguard Subscriber registration data, certificate data, and related certificate operation information, and to prevent Confidential Information from being leaked, misused, tampered with, or used without authorization.
- This Certification Center shall accept Subscriber Certificate applications, certificate re-keys, and certificate revocation requests in accordance with the Certificate Policy and Certification Practice Statement, verify the correctness and completeness of relevant information sent by Subscribers to this Certification Center, perform certificate issuance and certificate revocation operations, and deliver relevant response messages to Subscribers.
- When issuing Subscriber Certificates, this Certification Center must verify the correctness and legality of application documents and Subscriber identity.
- When there are security concerns regarding the Private Key of the Subordinate CA, the Subordinate CA must notify Subscribers and the Root Certification Authority (RCA). When there are security concerns regarding the Private Key of the RCA, the RCA must notify all Subordinate CAs.
- When issuing certificates, this Certification Center shall securely deliver the issued certificates to the Repository in accordance with this Statement.
- When revoking Subscriber Certificates, this Certification Center shall generate CRLs in accordance with this Statement and securely deliver them to the Repository.
- This Certification Center shall provide certificate application procedures and a Subscriber agreement prior to the Subscriber's certificate application, detailing the operational specifications for certificate application, re-key, revocation, and usage, as well as the relevant rights and obligations.
- The Private Keys used by this Certification Center for issuing certificates and CRLs must be used independently and shall not be shared with other functions. If there are other requirements for message signing and encryption, different Private Keys must be used.
- The Certificate Warranties specifically include, but are not limited to, the following. For items 1 to 4, this Certification Center warrants that, at the time of issuance, it implemented the relevant verification procedure, followed that procedure when issuing the Certificate, and accurately described that procedure in this Statement:
  1. Right to Use Mailbox Address: verifying that the Applicant either had the right to use, or had control of, the Mailbox Addresses listed in the Certificate's `subject` field and `subjectAltName` extension (or was delegated such right or control by someone who had such right to use or control); see [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control).
  2. Authorization for Certificate: verifying that the Subject authorized the issuance of the Certificate and that the Applicant Representative is authorized to request the Certificate on behalf of the Subject; see [Section 3.2.6](#326-validation-of-authority).
  3. Accuracy of Information: verifying the accuracy of all of the information contained in the Certificate (with the exception of the `subject:serialNumber` attribute); see [Section 3.2.2](#322-validation-of-mailbox-authorization-or-control) and [Section 3.2.3](#323-authentication-of-organization-identity).
  4. Identity of Applicant: where the Certificate contains Subject Identity Information, verifying the identity of the Applicant in accordance with [Section 3.2](#32-initial-identity-validation); see [Section 3.2.3](#323-authentication-of-organization-identity).
  5. Subscriber Agreement: where this Certification Center and the Subscriber are not Affiliated, the Subscriber and this Certification Center are parties to a legally valid and enforceable Subscriber Agreement that satisfies the BR; where they are the same entity or are Affiliated, the Applicant Representative acknowledged the Terms of Use.
  6. Status: this Certification Center maintains a 24 x 7 publicly-accessible Repository with current information regarding the status (valid or revoked) of all unexpired Certificates.
  7. Revocation: this Certification Center will revoke the Certificate for any of the reasons specified in the BR.

### 9.6.2 RA representations and warranties

As specified in [Section 9.6.1](#961-ca-representations-and-warranties).

### 9.6.3 Subscriber representations and warranties

Subscribers of this Certification Center are Legal Entities or organizations. Before issuing a Certificate, this Certification Center obtains the Applicant's agreement to the Subscriber Agreement, for the express benefit of this Certification Center and the Certificate Beneficiaries. The Subscriber Agreement applies to the Certificate to be issued pursuant to the certificate request, and this Certification Center has implemented a process to ensure that each Subscriber Agreement is legally enforceable against the Applicant. The Subscriber Agreement imposes the following obligations and warranties on the Applicant:

1. Accuracy of Information: to provide accurate and complete information at all times to this Certification Center, both in the certificate request and as otherwise requested by this Certification Center in connection with the issuance of the Certificate.
2. Protection of Private Key: to take all reasonable measures to assure control of, keep confidential, and properly protect at all times the Private Key that corresponds to the Public Key included in the Certificate (and any associated activation data or device, such as a password or token).
3. Acceptance of Certificate: to review and verify the Certificate contents for accuracy, and to confirm that the Public Key and Private Key are a matching key pair.
4. Use of Certificate: to use the Certificate only for the Mailbox Addresses listed in the Certificate, and to use the Certificate solely in compliance with all applicable laws and solely in accordance with the Subscriber Agreement.
5. Reporting and Revocation: to immediately request revocation of the Certificate, and cease using it and its associated Private Key, if there is any actual or suspected misuse or compromise of the Private Key associated with the Public Key included in the Certificate; and to immediately request revocation of the Certificate, and cease using it, if any information in the Certificate is or becomes incorrect or inaccurate.
6. Termination of Use of Certificate: to immediately cease all use of the Private Key corresponding to the Public Key included in the Certificate upon revocation of that Certificate for reasons of Key Compromise.
7. Responsiveness: to respond to this Certification Center's instructions concerning Key Compromise or Certificate misuse within 24 hours.
8. Acknowledgment and Acceptance: to acknowledge and accept that this Certification Center is entitled to revoke the Certificate immediately if the Applicant violates the terms of the Subscriber Agreement or if revocation is required by this Statement or the BR.

Subscribers shall also observe the following:

- When applying for a certificate from this Certification Center, the Subscriber must fully understand and agree to the rights and obligations in the application form and agreement, as well as the content of this Statement and related specifications.
- The Subscriber shall bear the risk and liability arising from the use of the certificate before the revocation status has been published.
- If this Certification Center is unable to operate normally due to unforeseen circumstances, the Subscriber shall promptly seek other means to complete legal acts with others, and shall not use the inability of this Certification Center to operate normally as a defense against others.
- Subscribers or technical personnel managing the email system shall have the capability to replace certificates within 24 hours or 5 days to avoid email communication disruption due to certificate revocation.
- In accordance with [Section 4.9.1](#491-circumstances-for-revocation), when circumstances meeting the grounds for certificate revocation occur, this Certification Center completes the revocation, depending on the revocation reason classification, within 24 hours (e.g., Key Compromise) or 5 days (e.g., incorrect certificate content) of becoming aware of them. Subscribers shall not request an extension of the revocation deadline, and shall cooperate to complete certificate replacement within that deadline. This Certification Center will proactively revoke the certificate when the revocation deadline expires without further notice.

### 9.6.4 Relying party representations and warranties

- Relying Parties shall obtain the Subordinate CA and the Root Certification Authority (RCA) self-signed certificates in accordance with this Statement.
- Relying Parties shall use the Subordinate CA certificate and the RCA self-signed certificate to establish and verify the certificate chain, to determine whether to trust Subscriber Certificates.
- When verifying certificates, Relying Parties shall use the RCA self-signed certificate to verify whether the digital signature of the Subordinate CA certificate was signed by the RCA's Private Key, and verify through the CRL whether the certificate has been revoked.
- When verifying Subscriber Certificates, Relying Parties shall use the Subordinate CA certificate to verify whether the digital signature of the Subscriber Certificate was signed by the Subordinate CA's Private Key, and verify through the CRL or OCSP service whether the certificate has been revoked.
- When using CRLs issued by this Certification Center, the Relying Party shall first verify the digital signature and check the Next Update time recorded in the CRL. If the Next Update time has passed, the latest CRL should be obtained. When using the OCSP service, the digital signature of the OCSP response should first be verified.
- Relying Parties shall select a secure computing environment and trustworthy applications. If user rights are compromised due to factors inherent in the computing environment or applications, the Relying Party shall bear the responsibility.
- If this Certification Center is unable to operate normally due to unforeseen circumstances, Relying Parties shall promptly seek other means to complete legal acts with others, and shall not use the inability of this Certification Center to operate normally as a defense against others.
- By accepting the use of certificates issued by this Certification Center, the Relying Party acknowledges understanding and agreement with the terms regarding the legal liability of this Certification Center, and shall rely on the certificate within the scope specified in this Statement.

### 9.6.5 Representations and warranties of other participants

No stipulation.

## 9.7 Disclaimers of warranties

- This Certification Center shall not be liable for damages arising from processing Subscriber registration data and certificate issuance, unless it has failed to follow this Statement, has violated applicable laws, or the damage is attributable to its intentional act or negligence.
- This Certification Center shall not be liable for damages to Subscribers and Relying Parties caused by force majeure events (e.g., earthquakes) or other causes not attributable to this Certification Center (e.g., war).
- If this Certification Center fails to properly safeguard the Subscriber's registration and certificate-related Confidential Information, resulting in information being leaked, misused, tampered with, or used without authorization, causing damage to third parties, this Certification Center shall be liable for damages.
- After receiving a certificate revocation request, this Certification Center shall investigate and provide a preliminary response within 24 hours, and the time from receipt of the request to published revocation shall not exceed the timeframe specified in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate). After the certificate revocation operation is completed, the Certificate Revocation List (CRL) shall be issued and published in the Repository at the frequency specified in [Section 4.9.7](#497-crl-issuance-frequency). Before the certificate revocation status is published, the Subscriber shall take appropriate action to minimize the impact on Relying Parties and bear all liability arising from the use of the certificate. For revocation operational specifications, please refer to [Section 4.9](#49-certificate-revocation-and-suspension).

## 9.8 Limitations of liability

When Subscribers and Relying Parties suffer damage events arising from the issuance or use of certificates, the liability for damages that this Certification Center shall bear is limited to the scope defined by relevant laws and regulations, the Subscriber agreement, or the company's insurance liability limit.

## 9.9 Indemnities

Notwithstanding any limitation this Certification Center places on its liability to Subscribers and Relying Parties, this Certification Center understands and acknowledges that the Application Software Suppliers that have agreed to distribute this Certification Center's Root CA certificate do not assume any obligation or potential liability of this Certification Center under the [BR](https://cabforum.org/working-groups/smime/requirements/), or that might otherwise exist because of the issuance or maintenance of certificates or reliance on them by Relying Parties or others.

Accordingly, this Certification Center shall defend, indemnify, and hold harmless each Application Software Supplier for any and all claims, damages, and losses suffered by that Application Software Supplier related to a certificate issued by this Certification Center, regardless of the cause of action or legal theory involved. This Certification Center is not a government entity and does not invoke the exception available under the [BR](https://cabforum.org/working-groups/smime/requirements/) to a CA that is a government entity.

This obligation does not apply to a claim, damage, or loss suffered by an Application Software Supplier related to a certificate issued by this Certification Center where that claim, damage, or loss was directly caused by that Application Software Supplier's software:

- displaying as not trustworthy a certificate that is still valid;
- displaying as trustworthy a certificate that has expired; or
- displaying as trustworthy a certificate that has been revoked, but only where the revocation status was at the relevant time available online from this Certification Center and the application software either failed to check that status or ignored an indication of revoked status.

The limitations, disclaimers, and exclusions stated in [Section 9.2.3](#923-insurance-or-warranty-coverage-for-end-entities), [Section 9.7](#97-disclaimers-of-warranties), [Section 9.8](#98-limitations-of-liability), and [Section 9.16.5](#9165-force-majeure) govern this Certification Center's liability to Subscribers and Relying Parties, and do not limit, condition, or qualify the obligation stated in this Section.

## 9.10 Term and termination

### 9.10.1 Term

This Statement becomes effective upon approval by the competent authority in accordance with the Electronic Signatures Act and publication in the Repository of this Certification Center.

### 9.10.2 Termination

Upon approval and publication of a new version of this Statement by the competent authority, the current version is terminated.

### 9.10.3 Effect of termination and survival

The effectiveness of this Statement is maintained until the last certificate issued in compliance with this Statement expires or is revoked.

## 9.11 Individual notices and communications with participants

This Certification Center will establish communication channels with Subscribers by appropriate means, including but not limited to the following: telephone, fax, or email.

## 9.12 Amendments

### 9.12.1 Procedure for amendment

- The responsible management unit for this Statement is the Policy Management Authority (PMA), which reviews and updates this Statement at least once every 365 days, incrementing the version number and adding a dated entry to the "Document History" section, even if no other changes are made to this Statement. Revision methods include revisions through supplementary documents or direct revision of the content of this Statement.
- Material changes to the implementation commitments recorded in this Statement are reflected through version increments and changelog entries, so that external parties can determine when substantive changes have occurred. This Statement accurately reflects the current practices, systems, and operational constraints of this Certification Center.
- If the Certificate Policy is revised or the object identifier is changed, this Statement will be revised accordingly.
- If changes are required due to changes in legal regulations, updates to international standards (e.g., [BR](https://cabforum.org/working-groups/smime/requirements/)), or other factors, this Statement will also be revised accordingly.
- After the revision of this Statement is reviewed and approved by the competent authority, it will be published in the Repository as specified in [Chapter 2](#2-publication-and-repository-responsibilities).

### 9.12.2 Notification mechanism and period

- For suggestions to update this Statement, please mail or email the detailed suggestion documents to the contact point in [Section 1.5.2](#152-contact-person), to be reviewed by the PMA.
- After the revision of this Statement is reviewed and approved by the competent authority, it will be published in the Repository of this Certification Center for download.
- Unless otherwise specified, this Certification Center uses the method specified in [Section 9.11](#911-individual-notices-and-communications-with-participants) as the amendment notification mechanism with Subscribers.

### 9.12.3 Circumstances under which OID must be changed

The Certificate Policy Object Identifiers referenced in this Statement will not be changed when the content of this Statement is amended; only the version identification code of this Statement will be incremented.

## 9.13 Dispute resolution provisions

If Subscribers have disputes regarding the services of this Certification Center or the use of certificates issued by it, the following provisions apply:

- The disputing parties shall, in good faith and through reasonable means, endeavor to resolve the dispute through negotiation.
- If the disputing parties are unable to reasonably resolve the dispute through negotiation within 30 days, they must appoint a competent and impartial third-party mediator to mediate and resolve the dispute.
- If the disputing parties are unable to agree on the mediator's negotiation and ruling within 60 days, both parties agree that the Taipei District Court shall be the court of first instance jurisdiction.
- The allocation of costs incurred during dispute negotiation and litigation proceedings shall be handled in accordance with the negotiation or relevant legal regulations.
- If a cross-border or cross-regional dispute cannot be resolved by the above methods, it must be handled in accordance with the relevant cross-border or cross-regional dispute arbitration regulations.

## 9.14 Governing law

The content of this Statement and the execution and interpretation of the related business of this Certification Center shall comply with the relevant laws and regulations of the competent authority and the relevant laws of this country.

## 9.15 Compliance with applicable law

- This Statement and this Certification Center shall comply with the Electronic Signatures Act of this country, its enforcement rules, and other applicable laws and regulations.
- This Certification Center complies with the latest version of the [BR](https://cabforum.org/working-groups/smime/requirements/). If there is any inconsistency between this Statement and the BR, the BR shall prevail; where the BR conflicts with domestic law, the matter is handled in accordance with [Section 9.16.3](#9163-severability).
- In addition to the BR, this Certification Center is bound by the latest version of the [CCADB Policy](https://www.ccadb.org/policy), by its own policy documents as disclosed in the CCADB, and by the policy of each Root Store Program listed in [Section 1.1](#11-overview). Where a new version of the CCADB Policy is published without a future effective date, this Certification Center complies with it within 14 calendar days of its publication.
- Where those requirements apply at the same time, they rank as follows: first, domestic law; second, whichever requirement is the stricter on the matter concerned; and last, this Statement. This Statement may not be relied upon to do anything that a stricter requirement prohibits. Where domestic law conflicts with those requirements, the matter is handled in accordance with [Section 9.16.3](#9163-severability).
- Where this Certification Center is uncertain which requirement applies to a particular practice, it seeks clarification from the Root Store Program concerned before taking the action in question, by a case comment in the CCADB or by the contact address that Program has designated for CA Owners, and retains the enquiry and the reply received. Where the requirements of two or more Root Store Programs cannot both be met, this Certification Center resolves the matter with the Programs concerned before proceeding. Any resulting amendment to this Statement is handled in accordance with [Section 9.12](#912-amendments).

## 9.16 Miscellaneous provisions

### 9.16.1 Entire agreement

No stipulation.

### 9.16.2 Assignment

No stipulation.

### 9.16.3 Severability

If certain provisions of this Statement are inapplicable and must be revised, the remaining provisions shall remain effective and unaffected by the inapplicable provision, until a new version of this Statement is updated and published.

In the event of a conflict between the [BR](https://cabforum.org/working-groups/smime/requirements/) and a law, regulation or government order (hereinafter "Law") of any jurisdiction in which this Certification Center operates or issues Certificates, this Certification Center may modify the conflicting requirement only to the minimum extent necessary to make the requirement valid and legal in that jurisdiction, and only for operations or Certificate issuances that are subject to that Law. Before issuing any Certificate under the modified requirement, this Certification Center shall:

1. immediately include in this section a detailed reference to the Law requiring the modification of the BR and the specific modification implemented by this Certification Center; and
2. notify the CA/Browser Forum of the information newly added to this Statement under item 1 by sending a message to public@cabforum.org and receive confirmation that it has been posted to the Public Mailing List and is indexed in the Public Mail Archives available at https://cabforum.org/pipermail/public/ (or such other email addresses and links as the CA/Browser Forum may designate).

Any such modification shall be discontinued if and when the Law no longer applies, or the BR is modified to make it possible to comply with both the BR and the Law simultaneously; the corresponding change in practice, amendment of this Statement, and notice to the CA/Browser Forum as described above shall be made within 90 days. Where domestic law conflicts with the policy of a Root Store Program listed in [Section 1.1](#11-overview), this Certification Center also notifies that Root Store Program. A conflict of requirements that does not involve domestic law is handled in accordance with [Section 9.15](#915-compliance-with-applicable-law).

Updates to this Statement shall be handled in accordance with [Section 9.12](#912-amendments).

### 9.16.4 Enforcement (attorneys' fees and waiver of rights)

No stipulation.

### 9.16.5 Force majeure

This Certification Center shall not be liable for damages due to force majeure events (e.g., earthquakes) or other causes not attributable to this Certification Center (e.g., war).

## 9.17 Other provisions

No stipulation.

# Appendix I: Glossary

**Internet**

A collection of many different computer networks interconnected with one another, which are able to exchange information with each other through standard communication protocols.

**(Electronic) Message**

Refers to a record consisting of text, sound, images, symbols, or other data, produced in electronic, magnetic, or other forms not directly perceivable by human senses, which is sufficient to express its intended meaning and is intended for electronic processing.

**RSA Algorithm**

An asymmetric cryptographic algorithm proposed by Ron Rivest, Adi Shamir, and Leonard Adleman in 1977, whose security strength is built upon the difficulty of factoring large numbers into prime factors.

**Elliptic Curve Cryptography (ECC)**

A public key cryptographic algorithm based on the mathematics of elliptic curves, proposed by Neal Koblitz and Victor Miller in 1985, whose security strength is built upon the difficulty of solving the elliptic curve discrete logarithm problem.

**ECC P-256 Curve**

An elliptic curve standard established by NIST in FIPS 186-3, which defines the relevant parameters of the elliptic curve p, a, b, G, n, h, in which the x and y coordinates of the base point G of the curve are each 256 bits in length.

**Electronic Signature**

Refers to a data message existing in electronic form, attached to an electronic document, which can be used to identify and confirm the identity of the signatory of the electronic document, and a message generated by the signatory using digital, voice, fingerprint, or other bio-optical technological characteristics; being attached to an electronic message, it has the same effect as a signature and can be used to identify and confirm the identity of the signatory of the electronic document and to verify the integrity of the signed message.

**Encrypt/Encipher**

Refers to the use of mathematical algorithms or other methods to process an electronic document into scrambled code, so as to ensure the security of data transmission.

**Decrypt/Decipher**

The process of restoring an encrypted message, which has been rendered unrecognizable to humans, back into a message whose meaning is recognizable to humans, by means of the relevant mathematical algorithms or other methods.

**Digital Signature**

A Digital Signature is a type of Electronic Signature, which refers to a data message formed by using an Asymmetric Cryptosystem and a Hash Function to compress a digital message of a certain length and then encrypting it with the signatory's Private Key; the corresponding Public Key can verify the encrypted digital message, thereby forming a data message that can be used to identify the identity of the signatory and the authenticity of the electronic document.

**Private Key**

Refers to one of a pair of matching digital data used to create and verify a Digital Signature, which is retained by the signatory; in addition to being used to create Digital Signatures, this digital data may also be used to decrypt electronic messages.

**Public Key**

In digital signatures under an asymmetric cryptographic algorithm, refers to the one of a pair of matching digital data used to create and verify Digital Signatures that is made publicly available; it can be used to verify the correctness of message data signed by the signatory, and, when performing message confidentiality functions, it can be used to encrypt the transmitted message.

**\<Public Key\> Certificate**

A computer-based digital record issued by a Certification Authority, containing the Applicant's registered distinguished name, Public Key, the validity period of that Public Key, the registered distinguished name and signature of the Certification Authority, and other related information used for identification, which is used to confirm the identity of the signatory and to prove that the signatory possesses the matching Public Key and Private Key.

**Certification Authority (CA)**

Refers to an institution that provides Digital Signature creation and electronic certification services, namely an entity in a fair and objective position that verifies the correctness of the identity information of certificate applicants, as well as the association and legitimacy between the Applicant and the Public Key and Private Key to be verified, and issues Public Key Certificates accordingly.

**Certification Practice Statement (CPS)**

The operational rules and application procedures announced by a Certification Authority to the parties it serves regarding the management of certificate issuance, revocation, inquiry, and other operations, containing the Public Key infrastructure and security mechanisms for certificate operations, operational rules and procedures, the security mechanisms implemented in the Certification Authority's software and hardware, the management of rights and responsibilities, and related provisions.

**Asymmetric Cryptosystem**

A computer-based mathematical algorithm capable of generating and using a pair of mathematically related secure keys. The Private Key is used to sign messages, and the corresponding Public Key is used to verify the signed messages; the Public Key may also be used to encrypt messages, and the corresponding Private Key is used to decrypt the encrypted messages.

**Hash Function**

A mathematical algorithm that can convert a long string of bits into a bit message of fixed length. The same message input processed through the compression function will always produce the same output, and it is impossible to derive the input message from the resulting output.

**Automated Certificate Management Environment (ACME)**

A communication protocol used to automate certificate-related management operations (such as certificate application) between a Certification Authority (CA) and its clients, allowing users to automate the deployment of public key infrastructure at very low cost. The protocol primarily transmits formatted JSON messages over HTTPS, and the relevant standard is defined in [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555).

**Certificate Signing Request (CSR)**

An encoded file that enables a certificate Applicant to transmit the Public Key and certificate-related information to a Certification Authority in a standardized manner for certificate issuance. The file specifically proves that the Applicant is the holder of the Private Key.

**Issue a Certificate**

Refers to the process whereby a Certification Authority, in accordance with its Certification Practice Statement, examines the identity qualifications and relevant documents of the Public Key Certificate Applicant, verifies the matching relationship between the Applicant's Public Key and Private Key, and then issues a Public Key Certificate or other certificate.

**Public Suffix List (PSL)**

A public resource created by Mozilla, located at https://publicsuffix.org/ ; the list consists of two parts: one is the TLD (Top Level Domain) list provided by ICANN, and the other is the PRIVATE list provided by individuals or organizations.

**Mozilla Root Store Policy (MRSP)**

A set of rules and guidelines defined by the Mozilla organization for its Firefox web browser and other related products. The policy is intended to ensure that root Certification Authorities (CAs) trusted by Mozilla browsers comply with a series of standards and best practices, so as to safeguard the security and privacy of users.

**Bugzilla**

A web-based issue tracking and management application for browser-related issues maintained by Mozilla; when a CA experiences a significant deficiency, it must be reported here. Located at https://bugzilla.mozilla.org/. 

**Secure/Multipurpose Internet Mail Extensions (S/MIME)**

An Internet standard that extends the MIME protocol in terms of security, enabling MIME entities (such as digital signatures and encrypted information) to be encapsulated into secure objects, thereby adding message authenticity, integrity, and confidentiality services to e-mail applications. As defined in the BR, there are multiple different types of certificates. This Certification Center only issues Organization-validated certificates, which include multipurpose and strict profiles. For further details on the profiles, refer to the [BR](https://cabforum.org/working-groups/smime/requirements/).

**Common CA Database (CCADB)**

A public database and collection of policies jointly maintained by multiple browser vendors, used to collect and manage disclosure information of trusted Certification Authorities (CAs) (including certificate policies and certification practice statements, audit reports, incident reports, etc.). Its related policy requirements are known as the CCADB Policy, published at https://www.ccadb.org/policy .


# Appendix II: Acronyms and Abbreviations

The acronyms and abbreviations used in this Practice Statement are listed in the following table:

| Acronym | Full Name |
|---|---|
| ACME | Automated Certificate Management Environment |
| ANSI | American National Standards Institute |
| CA | Certification Authority |
| CABF | CA/Browser Forum |
| CC | Common Criteria |
| CCADB | Common CA Database |
| CN | Common Name |
| CP | Certificate Policy |
| CPS | Certification Practice Statement |
| CRL | Certificate Revocation List |
| CSR | Certificate Signing Request |
| DN | Distinguished Name |
| DCR | Detailed Controls Report |
| EAL | Evaluation Assurance Level |
| ECC | Elliptic Curve Cryptography |
| EKU | Extended Key Usage |
| FIPS | Federal Information Processing Standard |
| ISO/IEC | The International Organization for Standardization / The International Electrotechnical Commission |
| ITSEC | Information Technology Security Evaluation Criteria |
| MRSP | Mozilla Root Store Policy |
| OCSP | Online Certificate Status Protocol |
| OID | Object Identifier |
| PIN | Personal Identification Number |
| PKCS | Public Key Cryptography Standard |
| PKI | Public Key Infrastructure |
| PMA | Policy Management Authority |
| PSL | Public Suffix List |
| RA | Registration Authority |
| RCA | Root Certification Authority |
| RIR | Regional Internet Registry |
| RSA | Rivest, Shamir, Adleman |
| S/MIME | Secure/Multipurpose Internet Mail Extensions |
| BR | Baseline Requirements for the Issuance and Management of Publicly-Trusted S/MIME Certificates |
| SAN | Subject Alternative Name |
| SHA | Secure Hash Algorithm |
| TCSEC | Trusted Computer System Evaluation Criteria |
| URL | Uniform Resource Locator |
