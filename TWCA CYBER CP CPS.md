# TAIWAN-CA INC. CYBER Certification Authority Certificate Policy and Certification Practice Statement (TWCA CYBER CA CP/CPS)

**(Version 2.3.1)**

Effective Date: 2026/11/1

## Document History

| Version | Effective Date | Revision Description |
|---------|--------------|----------------------|
| 1.0 | October 30, 2022 | Initial version. |
| 1.1 | February 29, 2024 | Adjusted Sections 7.1.2.2, 7.1.2.3, and 7.1.4.3.1. |
| 2.0 | April 9, 2025 | Revised in accordance with the "Required Items for Digital Signature Certification Practice Statements" promulgated under the new Electronic Signatures Act. |
| 2.0.1 | November 15, 2025 | 3.2.2: Added validation record validity periods. 3.2.2.4, 3.2.2.5, 3.2.2.8, 3.2.2.9: Adjusted domain validation methods and added MPIC and DNSSEC requirements. 3.3.1, 6.3.2: Added certificate validity period limits. 5.7.1.2: Added mass revocation plan. 7.1.4.3.1: Tabulated certificate names. |
| 2.2 | June 8, 2026 | Merged CP/CPS and added international compliance declarations. 3.2.2: Removed unused validation methods, added long-lived validation methods, and tabulated them. 3.2.2.8, 4.2.4: Disclosed CAA parameter (`accounturi`, `validationmethods`) processing per Ballot SC-098v2. 4.1, 4.3, 4.7, 4.9: Added ACME automation. 5.2: Added developer role. 6.7: Added vulnerability response and remediation timelines. |
| 2.3 | October 31, 2026 | Revised in accordance with root program review comments and the latest CA/Browser Forum requirements; added the TWCA CYBER Root CA G3 certificate hierarchy. |
| 2.3.1 | November 1, 2026 | 7.1.2.2, 7.1.4.3.2, 7.1.4.3.3: Added the Cross Certificate issued by TWCA CYBER Root CA to TWCA CYBER Root CA G3, and the Cross Certificate re-issued by TWCA Global Root CA to TWCA CYBER Root CA on October 31, 2026; added the date of issuance to the Cross Certificate table. |

## Summary

The key items of the TAIWAN-CA INC. CYBER Certification Authority Certificate Policy and Certification Practice Statement are described as follows:

### Certificates Issued

Certificates issued by the TAIWAN-CA INC. CYBER Certification Authority (hereinafter referred to as "this Certification Center") are issued to Subscribers' domain hosts, enabling Relying Parties to identify the host name and the managing organization, serving as certificates for domain host identity authentication. Certificate types include "SSL Certificates" and "EV SSL Certificates." Unless otherwise specified, "Subscriber Certificates" in this document refers to both types of certificates.

#### Certificate Types and Applicable Scope

| Certificate Type | Applicable Scope |
|-----------------|-----------------|
| SSL Certificate | Used to protect online communication security and reduce the risk of information being maliciously intercepted or tampered with. Through organization validation and domain validation, it provides website host identity authentication (Server Authentication), ensuring that users connect to genuine and legitimate servers. It is applicable to network environments requiring high security, such as e-commerce websites on the Internet. |
| EV SSL Certificate | Used to protect online communication security and reduce the risk of information being maliciously intercepted or tampered with. Through enhanced organization validation and domain validation, it provides website host identity authentication (Server Authentication), ensuring that users connect to genuine and legitimate servers. It is applicable to network environments requiring very high security, such as financial transaction websites on the Internet. |

**Note:**

Internationally, SSL certificates are defined at four different levels: from highest to lowest, they are EV (Extended Validation), OV (Organization-Validated), DV (Domain-Validated), and IV (Individual-Validated). The "SSL Certificates" issued by this Certification Center are OV-level certificates, while "EV SSL Certificates" are EV-level certificates. This Certification Center does not issue DV or IV level certificates.

The Extended Key Usage (hereinafter referred to as EKU) extension field of Subscriber Certificates issued by this Certification Center contains only the following usages:

- id-kp-serverAuth and id-kp-clientAuth; or
- id-kp-serverAuth

Subscriber Certificates issued by this Certification Center in accordance with this Statement require applicants to pass the "Organization Validation Procedure" and the "Domain Validation Procedure" ("Domain Name Validation Procedure" or "IP Address Verification") prescribed by this Certification Center, to confirm the Applicant's identity and ownership of the host name. Verifying a domain host's certificate using the Public Key of this Certification Center can be used to verify the mutual trust relationship between this Certification Center and the domain host. If the digital signature on the certificate is verified as correct, it can be confirmed that the domain host's certificate was indeed issued by this Certification Center, and the name identification information recorded in the certificate is valid, having passed the initial verification procedure of this Certification Center's Registration Authority.

### Important Legal Liability Matters

- If a Subscriber encounters grounds for certificate revocation (such as Key Compromise or loss), the Subscriber shall immediately notify this Certification Center and carry out certificate revocation procedures. However, the Subscriber shall bear the risks and liabilities arising from the use of the certificate before the revocation status is published.
- This Certification Center shall not be liable for damages arising from processing Subscriber registration data and certificate issuance, unless it has failed to follow this Statement, has violated applicable laws, or the damage is attributable to its intentional act or negligence.
- This Certification Center shall not be liable for damages to Subscribers caused by force majeure events (e.g., earthquakes) or other causes not attributable to this Certification Center (e.g., war).
- This Certification Center shall be liable for damages if it fails to properly safeguard Subscriber registration and certificate-related data, resulting in information leakage, unauthorized use, tampering, or arbitrary use causing damage to third parties.
- Upon receiving a certificate revocation request, this Certification Center shall investigate and provide a preliminary response within 24 hours, and the time from receiving the request to published revocation shall not exceed the time frame specified in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate). After the certificate revocation operation is completed, the Certificate Revocation List shall be issued and published in the Repository at the frequency specified in [Section 4.9.7](#497-crl-issuance-frequency). Before the certificate revocation status is published, the Subscriber shall take appropriate actions to reduce the impact on Relying Parties and shall bear all liabilities arising from the use of the certificate. For detailed revocation operation specifications, please refer to [Section 4.9](#49-certificate-revocation-and-suspension).
- In the event of a damage compensation incident between this Certification Center and the Subscriber arising from certificate issuance or usage, the liability of both parties shall be limited to the scope prescribed by relevant laws and regulations and the contract.
- By accepting and using certificates issued by this Certification Center, Relying Parties acknowledge and agree to the terms regarding this Certification Center's legal liability and shall rely on such certificates within the scope specified in this Statement.

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
- This Certification Center conducts internal audits at least once per quarter and commissions an accounting firm to conduct at least one external audit per year to ensure that its operations comply with this Statement. For detailed audit operation specifications, please refer to [Chapter 8](#8-compliance-audit-and-other-assessments).

# 1 INTRODUCTION

## 1.1 Overview

TAIWAN-CA INC. (hereinafter referred to as "the Company" or "TWCA") was jointly established with investment from Taiwan Stock Exchange Corporation (TWSE), Taiwan Depository & Clearing Corporation (TDCC), Financial Information Service Co., Ltd. (FISC), and HiTRUST Inc.

The TAIWAN-CA INC. CYBER Certification Authority Certificate Policy and Certification Practice Statement (hereinafter referred to as "this Statement") is a combined Certificate Policy (CP) and Certification Practice Statement (CPS) description, established in accordance with the "Required Items for Digital Signature Certification Practice Statements" promulgated by the competent authority of this country. It primarily describes how the TAIWAN-CA INC. CYBER Certification Authority (hereinafter referred to as "this Certification Center") conducts certificate issuance and management operations.

In addition to domestic laws and regulations, this Certification Center, to ensure the global trustworthiness of issued certificates and to maintain Internet communication security and user trust, expressly declares compliance with the following international standards and the latest requirements of browser root certificate policies:

- **CA/Browser Forum (hereinafter referred to as CABF)**: The latest versions of the Baseline Requirements for the [Issuance and Management of Publicly-Trusted TLS Server Certificates](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) (hereinafter referred to as BR) and the [Guidelines for the Issuance and Management of Extended Validation Certificates](https://cabforum.org/working-groups/server/extended-validation/guidelines/) (hereinafter referred to as EVG), published at https://cabforum.org/.
- **Browser Policies**: Including but not limited to the [Chrome Root Program Policy](https://googlechrome.github.io/chromerootprogram/), [Mozilla Root Store Policy](https://www.mozilla.org/en-US/about/governance/policies/security-group/certs/policy/), [Apple Root Program Policy](https://github.com/apple/apple-root-program/blob/main/policy.md), and [Microsoft Trusted Root Program](https://github.com/TrustedRootProgram/Program-Requirements/blob/main/Requirements.md).
- **CCADB Policy**: Complies with the [Common CA Database (hereinafter referred to as CCADB) Policy](https://www.ccadb.org/policy) co-maintained by multiple browser vendors.

To establish a secure and trustworthy online transaction environment, ensuring that information is not easily forged, tampered with, or stolen during network transmission, and to reliably authenticate domain host names and their associated Legal Entities or organizations for identification by Relying Parties, TWCA has established a Public Key Infrastructure (TWCA Public Key Infrastructure; TWCA PKI, hereinafter referred to as "this Infrastructure") and has set up a Trust Anchor Root Certification Authority (Root Certification Authority; RCA), which issues certificates to Subordinate Certification Authorities, which in turn issue certificates to Subscribers.

## 1.2 Document name and identification

The name of this Statement is "TAIWAN-CA INC. CYBER Certification Authority Certificate Policy and Certification Practice Statement." For the certificate policy identifiers used by this Certification Center, please refer to [Section 7.1.6](#716-certificate-policy-object-identifier).

### 1.2.1 Revisions

This Statement complies with and conforms to the [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) and [EVG](https://cabforum.org/working-groups/server/extended-validation/guidelines/). This Certification Center reviews the above standards and updates this Statement at least once every 365 days, incrementing the version number and adding a dated changelog entry, even if no other changes are made. In addition, if any inconsistency is found between this Statement and the above standards or domestic laws, this Certification Center will make amendments, or raise objections to CABF as appropriate. For the history of version changes, please refer to the "Document History" section of this Statement.

## 1.3 PKI Participants

This Certification Center includes the following members:

- Certification Authority (CA)
- Registration Authority (RA)
- Subscriber
- Relying Party
- Policy Management Authority (PMA)

The Certification Authority is divided by hierarchy and purpose into the "Root Certification Authority" (Root CA, abbreviated as RCA) and the "Subordinate Certification Authority" (Subordinate CA), collectively referred to as "this Certification Center."

This Statement will describe in [Chapter 3](#3-identification-and-authentication) and [Chapter 4](#4-certificate-life-cycle-operational-requirements) how this Certification Center conducts Subscriber Certificate issuance and management operations, and how Subscribers and Relying Parties apply for and use certificates; [Chapter 5](#5-management-operational-and-physical-controls) describes the management guidelines for the Root Certification Authority and the Subordinate Certification Authority.

### 1.3.1 Certification Authorities

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

### 1.3.2 Registration Authorities

The Registration Authority (RA) is primarily responsible for verifying the identity of applicants (Subscribers) and the related information required for certificate issuance, to serve as the basis for this Certification Center to issue Subscriber Certificates.

This Certification Center establishes its own Registration Authority and does not delegate it to a third party.

#### 1.3.2.1 Enterprise Registration Authorities

This Certification Center does not designate an Enterprise Registration Authority (Enterprise RA) to verify certificate requests, and does not accept a certificate request authorized by an Enterprise RA.

All certificate requests are verified by the Registration Authority of this Certification Center. Validation of ownership or control of domain names and IP addresses is performed in accordance with [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control) and [Section 3.2.2.5](#3225-authentication-for-an-ip-address); validation of organization identity is performed in accordance with [Section 3.2.2.1](#3221-identity). This Certification Center does not substitute an Applicant organization's own verification results, internal records, or attestations for those validations.

Because no Enterprise RA is designated, the acceptance conditions that the [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) impose on certificate requests authorized by an Enterprise RA (including the requirement that the requested Fully-Qualified Domain Names fall within the Enterprise RA's verified Domain Namespace, and that the Subject name be that of the delegated enterprise, an Affiliate of it, or a Subject for which it acts as agent), and the associated contractual limitation and monitoring obligations, do not arise for this Certification Center. See also [Section 8.8](#88-review-of-delegated-parties). Should this Certification Center decide to designate an Enterprise RA, this Statement will be amended in accordance with [Section 9.12](#912-amendments) before any such designation takes effect.

### 1.3.3 Subscribers

A Subscriber is the entity recorded in the certificate Subject name, who holds the Private Key corresponding to the Public Key in the certificate.

The Subscribers of this Certification Center are Legal Entities or organizations that apply for certificates.

### 1.3.4 Relying Parties

A Relying Party is an entity that uses the Public Key in the certificate issued by this Certification Center to verify the validity of the digital signature messages of Subscriber Certificates issued by this Certification Center.

Relying Parties use the identity information recorded in Subscriber Certificates to identify the domain host name and the information of its associated Legal Entity or organization.

Relying Parties shall use the information recorded in the certificates issued by this Certification Center to determine whether to rely on the certificate or whether it can be used for a specific purpose.

### 1.3.5 Other Participants

No stipulation.

## 1.4 Certificate Usage

### 1.4.1 Appropriate Certificate Uses

Certificates issued by this Certification Center to Subscribers are primarily used for website authentication, ensuring the authenticity of domain host identity and establishing a secure encrypted transmission channel with the connecting party. Certificate types and applicable scope are as follows:

| Certificate Type | Applicable Scope |
|-----------------|-----------------|
| SSL Certificate | Used to protect online communication security and reduce the risk of information being maliciously intercepted or tampered with. Through organization validation and domain validation, it provides website host identity authentication (Server Authentication), ensuring that users connect to genuine and legitimate servers. It is applicable to network environments requiring high security, such as e-commerce websites on the Internet. |
| EV SSL Certificate | Used to protect online communication security and reduce the risk of information being maliciously intercepted or tampered with. Through enhanced organization validation and domain validation, it provides website host identity authentication (Server Authentication), ensuring that users connect to genuine and legitimate servers. It is applicable to network environments requiring very high security, such as financial transaction websites on the Internet. |

**Note:**

Internationally, SSL certificates are defined at four different levels: from highest to lowest, they are EV (Extended Validation), OV (Organization-Validated), DV (Domain-Validated), and IV (Individual-Validated). The "SSL Certificates" issued by this Certification Center are OV-level certificates, while "EV SSL Certificates" are EV-level certificates. This Certification Center does not issue DV or IV level certificates.

The EKU extension field of Subscriber Certificates issued by this Certification Center contains only the following combinations of usages, where each usage is represented by its corresponding Object Identifier (OID):

1. **Server Authentication**: Singly contains the Extended Key Usage `id-kp-serverAuth` (OID: 1.3.6.1.5.5.7.3.1).
2. **Legacy TLS**: Simultaneously contains the Extended Key Usages `id-kp-serverAuth` (OID: 1.3.6.1.5.5.7.3.1) and `id-kp-clientAuth` (OID: 1.3.6.1.5.5.7.3.2).

This Certification Center expressly declares that starting from March 1, 2027, it will cease issuing certificates containing both `id-kp-serverAuth` and `id-kp-clientAuth`. Subscriber Certificates issued thereafter will singly contain `id-kp-serverAuth`.

Subscriber Certificates are issued by this Certification Center in accordance with this Statement. Applicants must pass the "Organization Validation Procedure" and the "Domain Validation Procedure" prescribed by this Certification Center to confirm the Applicant's identity and ownership of the host name. The validation procedures are as follows:

- **Organization Validation Procedure**
   - When authenticating the identity of a Legal Entity or organization, the identity of its representative shall first be authenticated, and documents sufficient to prove the registration or existence of the Legal Entity or organization shall be verified.
   - Application documents may be submitted in paper or electronic form.
   - The information provided in the application documents is verified against third-party public information or other supporting information to confirm that the content of the application documents is consistent with the verified content. For details, please refer to [Section 3.2.2.1](#3221-identity).
- **Domain Validation Procedure**
   - Domain host name authentication procedure: Must pass at least one of the validation methods defined in [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control).
   - IP address verification: Must pass at least one of the validation methods defined in [Section 3.2.2.5](#3225-authentication-for-an-ip-address).
- **Natural Person Authentication Procedure**: Applications from natural persons are not accepted.

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

For any questions regarding this Statement, or for Certificate Problem Reports (such as concerns about Key Compromise or certificate mis-issuance), please provide detailed information and contact details through the following contact:

| Item | Details |
|------|---------|
| Company Name | TAIWAN-CA INC. (TWCA) |
| Contact Person | Customer Service Center |
| Address | 10th Floor, 85, Yen-Ping South Road, Zhongzheng District (100), Taipei, Taiwan, R.O.C. |
| Telephone | 886-2-23708886 |
| Email | ca@twca.com.tw |

To report a Key Compromise, certificate misuse, impersonation, fraud, or other inappropriate conduct, please send an email to ca@twca.com.tw; this Certification Center accepts such reports 24 x 7. A report of Key Compromise shall include proof as described in [Section 4.9.12](#4912-special-requirements-re-key-compromise).

### 1.5.3 Person Determining CPS suitability for the policy

The Certification Practice Statement established by this Certification Center is approved by the PMA.

### 1.5.4 CPS approval procedures

In accordance with the Electronic Signatures Act, the Certification Practice Statement established by this Certification Center must be approved by the competent authority before this Statement may be publicly published and certificate issuance services may be provided.

## 1.6 Definitions and Acronyms

Please refer to [Appendix I](#appendix-i-glossary) and [Appendix II](#appendix-ii-acronyms-and-abbreviations).

Where a section of this Statement states "No Stipulation", it means that this Statement imposes no requirements related to that section, as that term is used in [RFC 3647](https://datatracker.ietf.org/doc/html/rfc3647). Where a section states "Not applicable", it means that the subject matter of that section does not arise given the operational model of this Certification Center.

# 2 PUBLICATION AND REPOSITORY RESPONSIBILITIES

## 2.1 Repositories

The Repository of this Certification Center provides querying or downloading of certificates, Certificate Revocation Lists (CRL), Certificate Policy and Certification Practice Statement, and other certificate operation-related information. It also provides Online Certificate Status Protocol (OCSP) services.

The Repository URL is: https://www.twca.com.tw/repository

The Repository addresses for CRL and OCSP are specified in certificate extension fields. For detailed information, please refer to [Chapter 7](#7-certificate-crl-and-ocsp-profiles).

## 2.2 Publication of information

The information published by this Certification Center includes the following:

- Previous versions of this Statement.
- Certificates and related information of this Certification Center.
- Issued certificates.
- CRL.
- OCSP services.
- Certificate test websites, including test websites for valid certificates, expired certificates, and revoked certificates, the locations of which are published on CCADB.
- Historical audit reports.
- Organization Registration Agency List (see [Section 3.2.2.7](#3227-data-source-accuracy)).

## 2.3 Time or frequency of publication

This Statement, upon completion of revisions and approval by the Policy Management Authority (PMA), will be submitted to the competent authority for approval. This Certification Center shall publish it in the Repository within 7 working days of receiving the approval document.

Certificates of this Certification Center, once issued, together with the certificate chain and related certificate information, shall be published in the Repository within 7 working days for querying by Subscribers or Relying Parties. The CRL issuance frequency is in accordance with the provisions of [Section 4.9.7](#497-crl-issuance-frequency).

This Certification Center reviews and updates this Statement at least once every 365 days, incrementing the version number and adding a dated entry to the "Document History" section, even if no other changes are made to this Statement.

## 2.4 Access controls on repositories

The Repository is made publicly available in read-only mode for querying by Subscribers or Relying Parties. However, to prevent malicious attacks or tampering, access controls are enforced when updating Repository information or when traffic is abnormal.
# 3 IDENTIFICATION AND AUTHENTICATION

## 3.1 Naming

### 3.1.1 Types of names

Certificates issued by this Certification Center, including CA Certificates and Subscriber Certificates, use Subject Distinguished Names (Subject DN) and Issuer Distinguished Names (Issuer DN) that comply with the X.500 Distinguished Name (DN) naming convention. The Common Name (CN) or Subject Alternative Name (SAN) shall not use internal names or reserved IP addresses. The attributes and content of such names comply with the relevant provisions of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280), BR, and EVG.

### 3.1.2 Need for names to be meaningful

The Subject Distinguished Name recorded in the Subscriber Certificate shall comply with the naming requirements of applicable laws and regulations. It must be sufficient to identify a specific Legal Entity or organizational unit and Domain Name, and must be identifiable by Relying Parties.

### 3.1.3 Anonymity or pseudonymity of subscribers

This Statement does not allow Subscribers to use anonymous names, pseudonyms, aliases, or pen names. However, the use of Punycode encoding for Internationalized Domain Names (IDNs) is accepted.

### 3.1.4 Rules for interpreting various name forms

The interpretation rules for names recorded in certificates are defined in accordance with ITU-T X.520 name attribute definitions.

### 3.1.5 Uniqueness of names

This Certification Center shall verify the uniqueness of Subscriber Chinese and English names, Domain Names, and Legal Entity or organization identification names. The same Domain Name may not be used by different Legal Entities or organizations; however, multiple certificates for the same Domain Name may be issued to the same Legal Entity or organization.

When Subscriber Certificates have identical unique distinguished names, this Certification Center gives priority to the Subscriber who first registered and passed the organization identity and domain validation. If a later Applicant completes identity verification before the earlier Applicant, the later Applicant may be given priority.

In the event of a dispute regarding the use of a distinguished name, if a competent authority/institution confirms through legitimate documentation that the name belongs to another Applicant, this Certification Center shall revoke the registered Subscriber's right to use the unique distinguished name, revoke the issued certificate, and the Subscriber shall bear the relevant legal liability.

### 3.1.6 Recognition, authentication, and role of trademarks

This Certification Center respects the registered trademarks of Subscriber Chinese and English names. After verification, Subscribers are allowed to use such Chinese and English names; however, this Certification Center does not guarantee the recognition, verification, or uniqueness of the Subscriber's registered trademark. In the event of a trademark dispute, the Subscriber shall resolve the matter through legal channels.

## 3.2 Initial identity validation

### 3.2.1 Method to prove possession of private key

The Public Key in the certificate and the corresponding Private Key shall be generated by the Subscriber. The Subscriber shall submit a certificate request file in PKCS#10 format to this Certification Center as proof of possession of the Private Key. This Certification Center shall use the Subscriber's Public Key to verify the signature value within the request file, confirming that the Subscriber is the owner of the Private Key and that the Public Key and Private Key form a key pair.

### 3.2.2 Authentication of Organization and Domain Identity

Prior to issuing a Subscriber Certificate, an "Organization Validation Procedure" and a "Domain Validation Procedure" ("Domain Name Validation Procedure" or "IP Address Verification") must be performed to confirm whether the Applicant is a legitimate Legal Entity or organization, and to confirm whether the Applicant possesses ownership and control of the domain being applied for.

The maximum validity periods for Validation Records of the "Organization Validation Procedure" and "Domain Validation Procedure" of this Certification Center are as follows. If no valid Validation Record is found, the initial validation procedure shall be re-performed in accordance with the provisions of this section.

The maximum validity periods for Validation Records shall be progressively shortened in accordance with [BR Section 4.2.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#421-performing-identification-and-authentication-functions) as follows:

**Organization Validation Procedure — Validation Record Validity Period**

| Certificate NTB >= | Certificate NTB < | Maximum Validation Record Validity |
|---|---|---|
| — | March 15, 2026 | 825 days |
| March 15, 2026 | — | 398 days |

**Domain Validation Procedure — Validation Record Validity Period**

| Certificate NTB >= | Certificate NTB < | Maximum Validation Record Validity |
|---|---|---|
| — | March 15, 2026 | 398 days |
| March 15, 2026 | March 15, 2027 | 200 days |
| March 15, 2027 | March 15, 2029 | 100 days |
| March 15, 2029 | — | 10 days |

Each period above runs from the date on which the data or document relied upon for the validation was obtained; where a Validation Record relies on more than one item of data or document, the earliest of them governs.

#### 3.2.2.1 Identity

This procedure applies to the validation of Legal Entities or organizations. For purposes of this section, the unified term "organization" is used. Part A below applies to both SSL Certificates and EV SSL Certificates; Part B applies only to EV SSL Certificates and does not apply to SSL Certificates.

**A. Applicable to both SSL Certificates and EV SSL Certificates**

When performing identity validation of an organization, verification MUST be conducted against certification documents issued by the competent authority or other documents that can prove the existence of the organization. The identity of the representative MUST also be verified. Application documents may be submitted in paper or electronic form.

Where the Subject Identity Information is to include the name or address of an organization, this Certification Center verifies the identity and address of the organization and that the address is the Applicant's address of existence or operation. Verification uses documentation provided by, or information obtained through communication with, at least one of the following:

1. A government agency in the jurisdiction of the Applicant's legal creation, existence, or recognition;
2. A third party database that is periodically updated and assessed by this Certification Center as a Reliable Data Source under [Section 3.2.2.7](#3227-data-source-accuracy);
3. An Attestation Letter.

The same documentation or communication may be used to verify both the Applicant's identity and address. The address alone may additionally be verified using a utility bill, bank statement, credit card statement, government-issued tax document, or other form of identification that this Certification Center determines to be reliable.

For every document relied upon under Section 3.2.2 and its subsections (including application documents provided by the Applicant and documents obtained from government agencies, third-party databases, or other sources), Validation Specialists must manually inspect the document for alteration or falsification (checking for physical or digital edit artifacts). Additionally, Validation Specialists cross-check these documents against third-party publicly available organization registration agencies (such as the official commerce registration database of the Ministry of Economic Affairs) or other trusted evidentiary information to verify the Applicant's legal existence and identification information, and to confirm that the content of the application documents matches the latest registered content of the competent authority, thereby satisfying the identity validation requirements of [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) or [EVG](https://cabforum.org/working-groups/server/extended-validation/guidelines/).

For both SSL Certificates and EV SSL Certificates, this Certification Center verifies whether the Applicant, or the Applicant's Jurisdiction of Incorporation, Jurisdiction of Registration, or Place of Business, is identified on any government denied list, list of prohibited persons, or other list that prohibits doing business with such organization or person under the laws of this Certification Center's country of operation; on any export-control entity list; or whether its Jurisdiction of Incorporation, Jurisdiction of Registration, or Place of Business is in a country with which those laws prohibit doing business. The lists used, their legal basis, and the official means of querying them are recorded in the "Organization Registration Agency List" published by this Certification Center, see [Section 3.2.2.7](#3227-data-source-accuracy). Where any of those circumstances is found, the certificate is not issued.

**B. Additional requirements for EV SSL Certificates**

The items in this Part apply only to EV SSL Certificates.

This Certification Center issues EV SSL Certificates only to Private Organizations. An Applicant that is not a Private Organization (for example a Government Entity, Business Entity, or Non-Commercial Entity) is not issued an EV SSL Certificate; such an Applicant may apply for an SSL Certificate, which is handled under Part A. The Business Category field of an EV SSL Certificate carries the value "Private Organization"; see [Section 7.1.4.2.2](#71422-subject-distinguished-name-fields).

Before an EV SSL Certificate is issued, the following additional verification is completed for the applying organization (the "registration agency" referred to below means the organization registration agency, not the certificate Registration Authority):

1. The organization name must be the full legal name. Organizational prefixes or suffixes may be abbreviated, e.g., "Company Name Incorporated" may be abbreviated to "Company Name, Inc.", provided that the abbreviations used are not misleading in the Jurisdiction of Incorporation or Registration
2. Data recorded in the certificate fields relating to the Jurisdiction of Incorporation shall not contain information not recorded by the registration agency, and shall not contain information that is not relevant to the level of that registration agency. The Incorporating or Registration Agencies of this Certification Center's EV SSL Certificate Applicants all operate at the country level; accordingly, only the Jurisdiction of Incorporation Country Name is included, and no state or province or locality information is included. The accepted value for that field is disclosed per agency in the "Organization Registration Agency List" published by this Certification Center, see [Section 3.2.2.7](#3227-data-source-accuracy) and [Section 7.1.4.2.2](#71422-subject-distinguished-name-fields).
3. The organization Registration Number field of the certificate contains the organization Registration Number assigned by the applicable Incorporating or Registration Agency, that is, the Unified Business Number. Where an Applicant has no Unified Business Number, the EV SSL Certificate is not issued. The Unified Business Number must be obtained through the public inquiry channel of the applicable Incorporating or Registration Agency. The accepted format of the organization Registration Number is disclosed in the "Organization Registration Agency List" published by this Certification Center, see [Section 3.2.2.7](#3227-data-source-accuracy); prior to issuance, the number recorded must be confirmed to conform to a format listed in the latest published version of that List.
4. The business address recorded in the certificate fields must be the organization's physical business address, verified under item (ii) below.
5. Organization registration data and registration status are verified against the sources set out in item (i) below, confirming that the organization's registration status with that agency indicates a currently existing entity; where the agency expresses that status by a particular term, such as "Approved for Establishment" (核准設立), that term governs, and the criterion is recorded per agency in the "Organization Registration Agency List". Where the record obtained states dissolution, revocation, annulment, cancellation, suspension of business, closure of business, bankruptcy, or any other termination of existence, the certificate is not issued.
6. The address of the Applicant's Registered Office, that is, the company address shown in the registration record of the Incorporating Agency, is obtained from the sources set out in item (i) below (see [EVG Section 3.2.2.2.1](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32221-verification-requirements)).
7. The Applicant's physical existence, Verified Method of Communication, and operational existence are verified under items (ii), (iii), and (iv) below (see [EVG Section 3.2.2.4](https://cabforum.org/working-groups/server/extended-validation/guidelines/#3224-verification-of-applicants-physical-existence), [Section 3.2.2.5](https://cabforum.org/working-groups/server/extended-validation/guidelines/#3225-verified-method-of-communication), and [Section 3.2.2.6](https://cabforum.org/working-groups/server/extended-validation/guidelines/#3226-verification-of-applicants-operational-existence)).
8. The checks set out in item (v) below are performed; where the Applicant is identified on any such list, the EV SSL Certificate is not issued.
9. The Certificate Requester, Certificate Approver, and Contract Signer information must be provided; the Applicant roles are defined in [Section 4.2.1](#421-performing-identification-and-authentication-functions), and their names, titles, agency, and authority are verified under [Section 3.2.5](#325-validation-of-authority).

**(i) Verification of Legal Existence**

The organization's Legal Existence, Organization Name, and Registration Number are verified directly with, or obtained directly from, the agency with which the Applicant effects its incorporation or registration under law, or through a QGIS operated by, or on behalf of, that agency where the third party obtains the information directly from that agency.

This Certification Center determines, from the Applicant's type of organization, which agency is its Incorporating or Registration Agency. Where the Applicant is registered with more than one agency, its Legal Existence and Registration Number are verified with the agency that effected its incorporation; where the Applicant's establishment requires, under law, approval or a business licence from a competent authority, that authority may also serve as the Incorporating or Registration Agency for the purposes of this item. The agencies used, the types of organization to which each applies, their jurisdictions, and the accepted formats of the organization Registration Number are all recorded in the "Organization Registration Agency List" published by this Certification Center, see [Section 3.2.2.7](#3227-data-source-accuracy); an agency not listed in the latest published version of that List must not be used as a source for these three items. Where the Applicant's type of organization has no corresponding Incorporating or Registration Agency in that List, where no registration record for the Applicant is found with that agency, or where the registration status recorded by that agency does not indicate a currently existing entity, the EV SSL Certificate is not issued.

A QIIS is not used as the source for the Legal Existence, Organization Name, and Registration Number described in the preceding paragraph; a QIIS may be used only to obtain the contact details of that Incorporating or Registration Agency so that the Agency can be contacted directly. The permitted uses of each category of information source (QGIS, QTIS, and QIIS) for the checks in this section are set out in the table in [Section 3.2.2.7](#3227-data-source-accuracy).


**(ii) Physical Existence and Place of Business**

This Certification Center verifies that the physical address provided by the Applicant is an address where the Applicant or a Parent/Subsidiary Company conducts business operations and is the Applicant's Place of Business; a mail drop, P.O. box, or "care of" (C/O) address is not accepted as a Place of Business. Verification is performed as follows:

1. Where the Place of Business is in the same country as the Jurisdiction of Incorporation or Registration:
   - Where the QGIS used to verify legal existence contains a business address for the Applicant, that address may be relied upon to confirm the address stated in the Certificate Request, and the Applicant's representation that such address is its Place of Business may be relied upon.
   - Otherwise, where the Applicant is listed at the same Place of Business address in the current version of another QGIS, a QIIS, or a QTIS, this Certification Center confirms by reference to that source that the address is a valid business address for the Applicant or a Parent/Subsidiary Company.
   - Where the Applicant is not so listed, this Certification Center does not issue an EV SSL Certificate.
2. Where the Place of Business is not within the Republic of China (Taiwan), this Certification Center does not issue an EV SSL Certificate. Such an Applicant may apply for an SSL Certificate under Part A above.

Where information of the Applicant's Parent, Subsidiary, or Affiliate Company is used for the verification above, or for the Verified Method of Communication or operational existence verification below, this Certification Center also verifies the Applicant's relationship to that company, by one of the following:

- The relationship being identified in a QIIS or QGIS;
- An Independent Confirmation from that company;
- A contract between this Certification Center and that company that designates the Certificate Approver with EV Authority and is signed by the Contract Signer, provided that the employment and Signing Authority of the Contract Signer have been verified; or
- A properly authenticated corporate resolution that approves creation of the Subsidiary or the Applicant, which may be used only for the relationship between the Applicant and its Subsidiary.

**(iii) Verified Method of Communication**

To assist in communicating with the Applicant and confirming that the Applicant is aware of and approves issuance, this Certification Center verifies a telephone number, fax number, email address, or postal delivery address as a Verified Method of Communication with the Applicant, as follows:

1. Verifying that the Verified Method of Communication belongs to the Applicant, or a Parent/Subsidiary or Affiliate of the Applicant, by matching it with one of their Places of Business in records provided by the applicable phone company, or in a QGIS, QTIS, or QIIS; and
2. Confirming the Verified Method of Communication by using it to obtain an affirmative response sufficient to enable a reasonable person to conclude that the Applicant can be contacted reliably by that means.

**(iv) Operational Existence**

This Certification Center verifies that the Applicant has the ability to engage in business by verifying the operational existence of the Applicant, or its Affiliate/Parent/Subsidiary Company, by one of the following:

1. Verifying that it has been in existence for at least three years, as indicated by the records of an Incorporating Agency or Registration Agency;
2. Verifying that it is listed in a current QIIS or QTIS; or
3. Receiving authenticated documentation, directly from a Regulated Financial Institution, of an active current Demand Deposit Account held with that institution.

**(v) Denied Lists and Other Legal Block Lists**

This Certification Center verifies whether the Applicant, the Contract Signer, the Certificate Approver, or the Applicant's Jurisdiction of Incorporation, Registration, or Place of Business:

1. Is identified on any government denied list, list of prohibited persons, or other list that prohibits doing business with such organization or person under the laws of the country of this Certification Center's jurisdiction of operation; or
2. Has its Jurisdiction of Incorporation, Registration, or Place of Business in any country with which the laws of that jurisdiction prohibit doing business.

This Certification Center operates in the Republic of China (Taiwan) and takes reasonable steps to verify against the equivalent denied lists and export regulations published by the government of the Republic of China (Taiwan); where it has operations in any other country, the equivalent lists and export regulations of that country are also used. The lists used, their legal basis, and the official means of querying them are recorded in the "Organization Registration Agency List" published by this Certification Center, see [Section 3.2.2.7](#3227-data-source-accuracy). Where either condition above is found, the EV SSL Certificate is not issued.

All information sources used for the verification in items (i) through (v) above are recorded in the "Organization Registration Agency List" published by this Certification Center; its disclosure content and usage limits are set out in [Section 3.2.2.7](#3227-data-source-accuracy).

#### 3.2.2.2 DBA/Tradename

This Certification Center does not include a DBA or Tradename in certificates.

#### 3.2.2.3 Verification of Country

In accordance with the provisions of [Section 3.2.2.1](#3221-identity).

#### 3.2.2.4 Validation of Domain Authorization or Control

This Certification Center shall perform ownership verification on the Common Name (CN) and Subject Alternative Name (SAN) of the certificate being applied for by the Applicant, using at least one of the following "Domain Name Validation Procedures":

| Validation Method Name (Applicable BR Section) | Wildcard | Prune | CNAME | Description |
|---|---|---|---|---|
| **Email to a Constructed Address** ([BR 3.2.2.4.4](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32244-email-to-a-constructed-address)) | ✔ | ✔ | ✔ | This Certification Center sends an email containing a unique Random Value with a 30-day validity period to the designated recipient. This Certification Center then verifies the Random Value. The recipient email address is limited to: admin, administrator, webmaster, hostmaster, or postmaster, followed by "@" and the domain name to be validated. **Restrictions and requirements:** Effective March 15, 2028, this Certification Center does not use this validation method, and prior validations using this method and validation data gathered according to this method are not used to issue Subscriber Certificates. |
| **DNS Change Validation** ([BR 3.2.2.4.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32247-dns-change)) | ✔ | ✔ | ✔ | The Applicant creates a CNAME, TXT, or CAA resource record in the DNS service of the domain to be validated, naming it with the domain name to be validated or a label prefixed with an underscore character placed before the domain name to be validated, and places therein a Random Value provided by this Certification Center and unique to the certificate request. This Certification Center then verifies the record. The Random Value is valid for 30 days from its creation. **Restrictions and requirements:** This Certification Center will implement Multi-Perspective Issuance Corroboration (MPIC) for this validation method. |
| **Website Change Validation** ([BR 3.2.2.4.18](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322418-agreed-upon-change-to-website-v2)) | - | - | - | The Applicant places a Random Value provided by this Certification Center and unique to the certificate request in a file under the specified website directory of the domain to be validated: "/.well-known/pki-validation". This Certification Center then retrieves the file using the http or https scheme over an Authorized Port (port 80 (http), 443 (https), 25 (smtp), or 22 (ssh)) to verify. The Random Value is valid for 30 days from its creation. The HTTP response status code must indicate success (2xx). If redirected, only HTTP-layer redirects are permitted (HTTP response status codes limited to: 301, 302, 307, or 308), and the redirected URL must use the http or https scheme and be accessed over an Authorized Port. **Restrictions and requirements:** This Certification Center will implement Multi-Perspective Issuance Corroboration (MPIC) for this validation method. Wildcard Domain certificates shall not use this method for verification. |
| **Website Change Validation (ACME)** ([BR 3.2.2.4.19](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322419-agreed-upon-change-to-website---acme)) | - | - | - | The Applicant uses the HTTP challenge method in the ACME protocol (`http-01`, defined in [RFC 8555, Section 8.3](https://datatracker.ietf.org/doc/html/rfc8555#section-8.3)) to prove domain control, which is then verified by this Certification Center. The ACME token is valid for 30 days from its creation. The HTTP response status code must indicate success (2xx). If redirected, only HTTP-layer redirects are permitted (HTTP response status codes limited to: 301, 302, 307, or 308), and the redirected URL must use the http or https scheme and be accessed over an Authorized Port. **Restrictions and requirements:** This Certification Center will implement Multi-Perspective Issuance Corroboration (MPIC) for this validation method. Wildcard Domain certificates shall not use this method for verification. |
| **Long-Lived DNS Validation** ([BR 3.2.2.4.22](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322422-dns-txt-record-with-persistent-value)) | ✔ | ✔ | - | The Applicant uses the "persistent DNS TXT record" domain validation method (corresponding to the ACME `dns-persist-01` challenge type) by adding a TXT record in a specific format under the _validation-persist label in DNS. The record must contain account identification information (accounturi) recognized by this Certification Center. If a validity period (persistUntil) is set, the verification must occur within that period. After completion of this validation method, the validation data is valid for a maximum of 10 days. **Restrictions and requirements:** For the Issuer Domain Name, see [Section 4.2.4](#424-caa-record-parameter-processing). This Certification Center will implement Multi-Perspective Issuance Corroboration (MPIC) for this validation method. |

Effective November 15, 2026, this Certification Center selects the Authorization Domain Name (ADN) for each applied-for FQDN or Wildcard Domain Name in accordance with the process in [BR Section 3.2.2.4](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#3224-validation-of-domain-authorization-or-control). A check mark in the "Wildcard", "Prune", or "CNAME" column of the table above means that the validation method permits the corresponding step below:

1. Where the applied-for name is a Wildcard Domain Name, only a validation method with a check mark in the "Wildcard" column may be used, and the leftmost "*." is first removed.
2. Where the applied-for name is an FQDN and the validation method has a check mark in the "CNAME" column, the name may be replaced with the result of a DNS CNAME lookup of that name; this step may be repeated.
3. Where the validation method has a check mark in the "Prune" column, the leftmost Domain Label may be pruned, one label at a time, but not beyond the Base Domain Name of the name; this step may be repeated.
4. The name resulting from the above steps is used as the ADN.

For the Long-Lived DNS Validation method ([BR 3.2.2.4.22](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322422-dns-txt-record-with-persistent-value)), the `accounturi` value carried in the persistent DNS TXT record shall be the URL of the requesting ACME account, in the format `https://ssl2.twca.com.tw/acme_m2/acct/{accountID}`, where `{accountID}` is the account identifier assigned by this Certification Center at the time of ACME account registration. The same format applies to the `accounturi` parameter as it appears in CAA records; see [Section 4.2.4](#424-caa-record-parameter-processing).

In accordance with [BR Section 5.4.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#541-types-of-events-recorded), all Validation Records of this Certification Center include the information being validated (i.e., the applied Fully Qualified Domain Name (FQDN)), the Authorization Domain Name for which verification was completed, and the validation method used. Among the above validation methods, those that derive the Authorization Domain Name by pruning ([BR Section 3.2.2.4.4](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32244-email-to-a-constructed-address), [Section 3.2.2.4.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32247-dns-change), and [Section 3.2.2.4.22](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322422-dns-txt-record-with-persistent-value)) determine the Base Domain Name using the Public Suffix List.

When performing the "Domain Name Validation Procedure," this Certification Center's Primary Network Perspective DNS resolver must, for every DNS query associated with the validation of domain authorization or control, establish a complete validation chain to the IANA DNSSEC root trust anchor and perform DNSSEC validation; local policy is not used to disable that validation.

#### 3.2.2.5 Authentication for an IP Address

This Certification Center shall perform ownership verification on all IP addresses to be included in the certificate applied for by the Applicant, using at least one of the following "IP Address Verification Procedures":

| Validation Method Name (Applicable BR Section) | Description |
|---|---|
| **Website Change Validation** ([BR 3.2.2.5.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32251-agreed-upon-change-to-website)) | The Applicant places a Random Value provided by this Certification Center and unique to the certificate request in the specified website directory of the IP address to be validated: "/.well-known/pki-validation". This Certification Center then verifies it using the http or https scheme over an Authorized Port (see [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control)). The Random Value is valid for 30 days from its creation. **Restrictions and requirements:** This Certification Center will implement Multi-Perspective Issuance Corroboration (MPIC) for this validation method. |
| **Reverse IP Lookup Validation** ([BR 3.2.2.5.3](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32253-reverse-address-lookup)) | A reverse-IP lookup is performed on the IP address to obtain the associated domain name. The FQDN is then validated for control using a domain validation method permitted under [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control), thereby confirming the Applicant's control over the IP address. Effective November 15, 2026, the ADN for this method must be exactly the FQDN returned from the reverse-IP lookup, and the ADN selection process in [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control) does not apply. **Restrictions and requirements:** This Certification Center will implement Multi-Perspective Issuance Corroboration (MPIC) for this validation method. Effective March 15, 2027, this Certification Center does not use this validation method, and prior validations using this method and validation data gathered according to this method are not used to issue Subscriber Certificates. |
| **Website Change Validation (ACME)** ([BR 3.2.2.5.6](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32256-acme-http-01-method-for-ip-addresses)) | Verification is performed using the http-01 method of the ACME protocol, following the IP identifier validation procedure documented in [RFC 8738](https://datatracker.ietf.org/doc/html/rfc8738). **Restrictions and requirements:** This Certification Center will implement Multi-Perspective Issuance Corroboration (MPIC) for this validation method. |

#### 3.2.2.6 Wildcard Domain Validation

When a certificate containing a Wildcard Domain Name is requested, this Certification Center removes the wildcard character "*." from the requested domain name and validates authorization or control over the remaining domain name in accordance with the domain name validation procedures set forth in [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control).

The wildcard "*." must not sit directly in front of a public suffix. A public suffix is a name listed on the Public Suffix List (https://publicsuffix.org/ ) under which the general public may each register their own subdomains, for example `com`, `com.tw` and `org.tw`. This Certification Center therefore does not issue Wildcard Certificates such as `*.com` or `*.com.tw`, which would cover other people's domains. The pre-issuance certificate check described in [Section 4.3.1](#431-ca-actions-during-certificate-issuance) automatically compares the name against the Public Suffix List, and certificates that fail the check are not issued.

This Certification Center does not issue Wildcard EV SSL Certificates. Under [EVG Section 7.1.2.1](https://cabforum.org/working-groups/server/extended-validation/guidelines/#7121-subject-alternative-name-extension) and [Section 7.1.4.2.2](https://cabforum.org/working-groups/server/extended-validation/guidelines/#71422-subject-common-name-field), neither the `subjectAltName` extension nor the `subject:commonName` field of an EV SSL Certificate may contain a Wildcard Domain Name. Wildcard certificates are issued only as SSL Certificates; an EV SSL Certificate request containing a wildcard character is rejected during the checks described in [Section 4.2.1](#421-performing-identification-and-authentication-functions).

#### 3.2.2.7 Data Source Accuracy

Prior to using any data source as a Reliable Data Source, this Certification Center evaluates the source for its reliability, accuracy, and resistance to alteration or falsification, considering the age of the information provided, the frequency of updates to the information source, the data provider and the purpose of the data collection, the public accessibility of the data, and the relative difficulty in falsifying or altering the data. Databases used by this Certification Center as a Reliable Data Source do not include databases maintained by this Certification Center, its owners, or its affiliated companies whose primary purpose is to collect information for the purpose of fulfilling the validation requirements under [Section 3.2](#32-initial-identity-validation).

The information sources used by this Certification Center in the Organization Validation Procedure are all recorded in the "Organization Registration Agency List", which is published in this Certification Center's Repository (https://www.twca.com.tw/repository) prior to the use of that registration agency for verification and is updated whenever an information source is added, changed, or discontinued.

As regards the Incorporating or Registration Agencies for EV SSL Certificates referred to in [Section 3.2.2.1](#3221-identity), Part B, item (i), before adding an agency this Certification Center first confirms that it is a government agency that, under law, effects the incorporation or registration of a given type of organization, licenses its establishment, or issues its business licence, that it operates at the country level, and that a public inquiry channel operated by, or on behalf of, that agency, with the data obtained directly from it, shows the organization's Unified Business Number. An agency that does not meet every one of those criteria is not added. An agency that meets them is submitted, after the validation unit has completed its assessment, to the Policy Management Authority (PMA) for approval, and is published as described in the preceding paragraph after approval and before it is actually used. An agency for which that approval and publication have not been completed must not be used to verify those three items.

The sources in that List fall into three categories - QGIS (Qualified Government Information Source), QTIS (Qualified Government Tax Information Source), and QIIS (Qualified Independent Information Source). The qualifying criteria for each are set out in [Appendix I](#appendix-i-glossary).

In addition to those three categories, this Certification Center uses records provided by a telephone company to verify a Verified Method of Communication and a Reliable Method of Communication (under [EVG Section 3.2.2.5.2](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32252-acceptable-methods-of-verification) A (i)). Such a source falls into none of the three categories above, may be used only to verify those methods of communication, and is not used for any other check; the sources used are likewise recorded in the "Organization Registration Agency List".

In addition, for the verification of organization identity under [Section 3.2.2.1](#3221-identity), Part A, this Certification Center may use data provided by government agencies (under item 1 of [BR Section 3.2.2.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#3221-identity)). Such data falls into none of the three categories above, may be used only for the organization identity verification of SSL Certificates, and is not used for EV SSL Certificates; the data used is recorded in the "Organization Registration Agency List".

The sources permitted for each check are set out in the table below (Yes = permitted, No = not permitted); a category is not used for any purpose other than those listed:

| Check (governing provision) | Applies to | QGIS | QTIS | QIIS |
|---|---|---|---|---|
| Verification of the organization's identity and address (Section 3.2.2.1, Part A) | SSL, EV SSL | Yes | Yes | Yes |
| Legal Existence, Organization Name, and Registration Number (the three items required by [Section 3.2.2.1](#3221-identity), Part B, item (i), "Verification of Legal Existence") | EV SSL | Yes (Note 1) | No | No (Note 2) |
| Physical existence and Place of Business (Section 3.2.2.1, Part B, item (ii)) | EV SSL | Yes | Yes | Yes |
| Parent/Subsidiary/Affiliate relationship (Section 3.2.2.1, Part B, item (ii), final paragraph) | EV SSL | Yes | Yes | Yes |
| Verified Method of Communication (Section 3.2.2.1, Part B, item (iii)) (Note 4) | EV SSL | Yes | Yes | Yes |
| Operational existence - verified by way of a listing in a current directory (Section 3.2.2.1, Part B, item (iv), sub-item 2) | EV SSL | No (Note 3) | Yes | Yes |
| Reliable Method of Communication ([Section 3.2.5](#325-validation-of-authority), Part A) (Note 4) | SSL, EV SSL | Yes | Yes | Yes |
| Address of the Registered Office (Section 3.2.2.1, Part B, item 6) | EV SSL | Yes (Note 1) | No | No |
| Name, title, and employment of the Contract Signer and Certificate Approver ([Section 3.2.5](#325-validation-of-authority)) | EV SSL | Yes | Yes | Yes |
| Signing Authority of the Contract Signer and EV Authority of the Certificate Approver (Section 3.2.5, Part B, item 2) | EV SSL | Yes | Yes | Yes |
| Confirming Person and contact details for an Independent Confirmation From Applicant (Section 3.2.5, Part B) | EV SSL | Yes | Yes | Yes |
| Obtaining further explanation of discrepancies or outstanding items during Final Cross-Correlation and Due Diligence (Section 3.2.5, Part C) | EV SSL | Yes | Yes | Yes |
| English organization name | EV SSL | Yes (Note 5) | No | No |

Notes:

1. Only information provided by the Applicant's Incorporating or Registration Agency itself, or a QGIS operated by, or on behalf of, that Agency where the third party obtains the information directly from that Agency, is accepted (per [EVG Section 3.2.2.2.2](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32222-acceptable-method-of-verification) (1)). A QGIS that is not operated by that Agency (for example, a public database of another government body) is not used for those three items and may be used only for the other checks listed in the table.
2. A QIIS is not used as the source for those three items; it may, however, be used to obtain the address or telephone number of the Incorporating or Registration Agency so that this Certification Center can contact that Agency directly (per EVG Section 3.2.2.2.2 (1)).
3. Under [EVG Section 3.2.2.6.2](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32262-acceptable-methods-of-verification) (2), operational existence verified by way of a listing in a current directory may rely only on a QIIS or a QTIS, and not on any other QGIS. Sub-item (1) of the same Section, which confirms existence for at least three years from the records of the Incorporating or Registration Agency, relies directly on those Agency records and is not subject to this restriction.
4. In addition to the three categories in the table, this check may rely on records provided by a telephone company (per EVG Section 3.2.2.5.2 A (i)). Such a source may be used only for this check and for the Reliable Method of Communication under Section 3.2.5, Part A; the sources used are recorded in the "Organization Registration Agency List".
5. The English organization name is limited to one of the following sources and matches that source character for character: (1) the foreign-language company name stated in the articles of incorporation, as shown in the registration record of the Applicant's Incorporating or Registration Agency (a QGIS, per [EVG Appendix D](https://cabforum.org/working-groups/server/extended-validation/guidelines/#appendix-d---country-specific-interpretative-guidelines-normative), Section 1, item 3.A); (2) the English name registered with the International Trade Administration, MOEA, as an exporter or importer under the Foreign Trade Act (a QGIS, per EVG Appendix D, Section 1, item 3.C; a QGIS meets every element of a QIIS and may therefore serve as the source under that item) (see [EVG Section 7.1.4.2.1](https://cabforum.org/working-groups/server/extended-validation/guidelines/#71421-subject-organization-name-field)). Where no such name is found, the organization name in the certificate is the Chinese full legal name.

In accordance with [EVG Section 3.2.2.1.3](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32213-disclosure-of-verification-sources), the "Organization Registration Agency List" contains at least the following, where the fields listed in items 2 and 3 are used only in EV SSL Certificates and are not present in SSL Certificates:

1. Sufficient information to unambiguously identify each registration agency, including its name, jurisdiction, and website.
2. The accepted value or values for each of the `subject:jurisdictionLocalityName` (OID: 1.3.6.1.4.1.311.60.2.1.1), `subject:jurisdictionStateOrProvinceName` (OID: 1.3.6.1.4.1.311.60.2.1.2), and `subject:jurisdictionCountryName` (OID: 1.3.6.1.4.1.311.60.2.1.3) fields when an EV SSL Certificate is issued using information from that registration agency, indicating the jurisdiction(s) for which the agency is appropriate. This Certification Center populates only `subject:jurisdictionCountryName` (with the value "TW"), and the other two fields are disclosed as not used; see [Section 3.2.2.1](#3221-identity), Part B, item 2.
3. The acceptable form or syntax of the Registration Numbers assigned by each registration agency.
4. A revision history that includes a unique version number and date of publication for any addition, modification, or removal.

Before using a QIIS, this Certification Center follows a documented process to check the accuracy of the database, including reviewing the database provider's Terms of Use, and confirms that all of the following are met; a database that does not meet them is not used as a QIIS:

1. Industries other than the certificate industry rely on the database for accurate location, contact, or other information.
2. The database provider updates its data on at least an annual basis.
3. Neither this Certification Center nor its owners or affiliated companies maintain a controlling interest in the database, and no Registration Authority or subcontractor to whom this Certification Center has outsourced any portion of the vetting process (nor their owners or affiliated companies) maintains any ownership or beneficial interest in it.

This Certification Center does not use any data in a QIIS that it knows is self-reported and not verified by the QIIS as accurate.

#### 3.2.2.8 CAA Records

When verifying the Certification Authority Authorization (CAA) records for the Applicant's domain, this Certification Center checks, in accordance with [RFC 8659](https://datatracker.ietf.org/doc/html/rfc8659) (or its subsequent updates), via the Domain Name System (DNS) whether the domain has authorized issuance. If the CAA record authorizes this Certification Center, the certificate application may be approved; otherwise, it shall be rejected. During the verification process, the DNS resolver used by the Primary Network Perspective must, for every DNS query associated with a CAA record lookup, establish a complete validation chain from the IANA DNSSEC root trust anchor and perform DNSSEC validation; local policy is not used to disable that validation, and a DNSSEC validation error (for example SERVFAIL) is not treated as permission to issue. In addition, this Certification Center processes the `accounturi` and `validationmethods` parameters defined in [RFC 8657](https://datatracker.ietf.org/doc/html/rfc8657); the recognized Issuer Domain Name, and the supported parameter formats and matching practices, are described in [Section 4.2.4](#424-caa-record-parameter-processing). The verification method follows [BR Section 4.2.2.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#4221-caa-record-processing) and [Section 4.2.2.2](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#4222-dnssec-validation-requirements).

#### 3.2.2.9 Multi-Perspective Issuance Corroboration

For the validation methods marked as using MPIC in the tables in [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control) and [Section 3.2.2.5](#3225-authentication-for-an-ip-address), and for the "CAA record" verification performed when those methods are used, in addition to performing the verification from the Primary Network Perspective, this Certification Center repeats the same verification from several remote Network Perspectives located in different places and compares the results, so as to reduce the risk of obtaining an incorrect verification result through localized routing hijacking or DNS tampering.

This Certification Center implements Multi-Perspective Issuance Corroboration (MPIC) with the following operational practices:

1. **Geographic Distribution and Distance Limits:** The remote Network Perspectives deployed by this Certification Center use DNS resolvers that are geographically dispersed. The straight-line distance between each remote node and the Primary Network Perspective, as well as between different remote nodes, is maintained at a minimum of 500 kilometers. A perspective node may use a recursive DNS resolver that is not co-located with it, provided that the resolver falls within the same Regional Internet Registry (RIR) service region as the node relying upon it; for any pair of DNS resolvers used in a single Multi-Perspective Issuance Corroboration attempt, the straight-line distance is likewise at least 500 kilometers.
2. **DNSSEC Validation:** DNSSEC validation is performed by the Primary Network Perspective in accordance with [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control) (DNS queries associated with the validation of domain authorization or control) and [Section 3.2.2.8](#3228-caa-records) (CAA record lookups). Remote perspective nodes do not perform DNSSEC validation; their function is to repeat the query over a different network path and compare the result with that of the Primary Network Perspective.
3. **DNS Cache Isolation:** To avoid obtaining an incorrect query result from a tampered DNS cache, the DNS resolvers at each perspective node enforce strict cache isolation. Independent query contexts are required for each domain ownership or CAA validation query to prevent cached data from different requests or perspectives from interfering with each other.
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

Matters not set out in detail in this section are handled in accordance with [BR Section 3.2.2.9](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#3229-multi-perspective-issuance-corroboration).

### 3.2.3 Authentication of individual identity

Applications from natural persons are not accepted.

### 3.2.4 Non-verified subscriber information

All Subscriber information recorded in certificates issued by this Certification Center has been verified.

### 3.2.5 Validation of authority

**A. Applicable to both SSL Certificates and EV SSL Certificates**

This Certification Center establishes and executes a written authorizer verification process allowing organization Applicants to specify in electronic or written form the list of authorized individuals (Authorized Certificate Requesters) who may request certificates. This Certification Center registers this list in its management systems and restricts certificate issuance requests to those individuals on the list; revocation requests are handled under [Section 3.4](#34-identification-and-authentication-for-revocation-request) and [Section 4.9.2](#492-who-can-request-revocation). If a request is received from an individual not on this list, it must be rejected. Upon verified written request from the organization Applicant, this Certification Center must provide the Applicant with the current list of its authorized certificate requesters.

This Certification Center uses a Reliable Method of Communication to verify the authenticity of the Applicant Representative's certificate request and that Representative's authority. A Reliable Method of Communication is a postal/courier delivery address, telephone number, or email address that this Certification Center has verified using a source other than the Applicant Representative; contact details supplied only by the Applicant Representative within the certificate application are not used for this purpose.

Provided that a Reliable Method of Communication is used, this Certification Center may establish the authenticity of the certificate request directly with the Applicant Representative, or with an authoritative source within the Applicant's organization, such as the Applicant's main business offices, corporate offices, human resource offices, information technology offices, or other department that this Certification Center deems appropriate.

**B. Additional steps for EV SSL Certificates**

For EV certificates, in addition to Part A above, this Certification Center performs the following verifications for each request:

1. **Name, title and employment of the Contract Signer and the Certificate Approver**: this Certification Center verifies the name and title of the Contract Signer and of the Certificate Approver, and confirms that each is an employee of the Applicant. Employment may be confirmed by contacting the Applicant using a Verified Method of Communication, by an Independent Confirmation From Applicant, or through a QGIS or a QIIS. The employment of the Certificate Approver may also be verified by a certification from the Contract Signer, including one contained in a contract between this Certification Center and the Applicant signed by the Contract Signer, provided that the employment status and the Signing Authority of that Contract Signer have been verified under the following item. An Independent Confirmation From Applicant referred to in this Section is obtained under the procedure in [EVG Section 3.2.2.11.4](https://cabforum.org/working-groups/server/extended-validation/guidelines/#322114-independent-confirmation-from-applicant): it is received from a Confirming Person within the Applicant with authority to confirm the fact (someone other than the person who is the subject of the inquiry), in a manner that authenticates its source, and it is binding on the Applicant.

2. **Signing Authority of the Contract Signer and EV Authority of the Certificate Approver**: the following are verified:

   (1) that the Contract Signer is authorized by the Applicant to enter into the Subscriber Agreement, and any other relevant contractual obligations, on behalf of the Applicant, including a contract that designates one or more Certificate Approvers on behalf of the Applicant; and

   (2) that, as of the date of the EV SSL Certificate Request, the Certificate Approver is expressly authorized by the Applicant to submit, and to authorize a Certificate Requester to submit, the EV SSL Certificate Request on behalf of the Applicant; to provide, and to authorize a Certificate Requester to provide, the information requested from the Applicant by this Certification Center for issuance of the EV SSL Certificate; and to approve EV SSL Certificate Requests submitted by a Certificate Requester.

   Verification is performed by one of the following:

   - a properly authenticated corporate resolution, provided that the resolution is certified by the appropriate corporate officer of the Applicant (e.g., the secretary) and that this Certification Center can reliably verify that the certification was validly signed by that person and that that person has the requisite authority to provide it;
   - an Independent Confirmation From Applicant;
   - a contract between this Certification Center and the Applicant that designates the Certificate Approver with such EV Authority, provided that the contract is signed by the Contract Signer and that the employment and Signing Authority of that Contract Signer have been verified;
   - Prior Equivalent Authority, applied in accordance with [EVG Section 3.2.2.8.3](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32283-acceptable-methods-of-verification--authority) item (5), recording sufficient details to correctly identify the previous agreement and associate it with this EV application (such as the agreement title, the date of the Contract Signer's signature, the contract reference number, and the filing location); or
   - a QIIS or QGIS that identifies the Contract Signer or the Certificate Approver as a corporate officer, sole proprietor, or other senior official of the Applicant.

   The EV Authority of the Certificate Approver is never established on the Certificate Approver's own statement alone; it is confirmed through a source other than that person.

3. **Verification of signature**: the Subscriber Agreement is signed by an authorized Contract Signer and each EV SSL Certificate Request is signed by the Certificate Requester who submits it; a paper document bears a legally valid and enforceable seal or handwritten signature, and an electronic document bears a legally valid and enforceable electronic signature, in each case binding the Applicant to the terms of that document. This Certification Center authenticates the signature by one of the following: contacting the Applicant using a Verified Method of Communication for the attention of the signer and obtaining confirmation from that person that he or she signed the document on behalf of the Applicant; mailing a letter to the Applicant's or its agent's address as verified under this Statement for the attention of the signer, followed by a response through a Verified Method of Communication from that person; using a signature process that establishes the name and title of the signer in a secure manner, such as an appropriately secure login process that identifies the signer before signing or a digital signature made with reference to an appropriately verified certificate; or notarization by a notary, provided that this Certification Center independently verifies that the notary is legally qualified in the jurisdiction of the signer.

4. **Verification of approval**: where an EV SSL Certificate Request is submitted by a Certificate Requester, this Certification Center verifies before issuance that an authorized Certificate Approver reviewed and approved the request, by one of the following: contacting the Certificate Approver using a Verified Method of Communication and obtaining oral or written confirmation that the request has been reviewed and approved; or verifying the signature of the Certificate Approver on the request in the manner set out in the preceding item. Where a Pre-Authorized Certificate Approver arrangement is in place, this Certification Center first verifies the name and title of the Contract Signer and that he or she is an employee or agent of the Applicant, and verifies that Contract Signer's Signing Authority in accordance with item 2, before entering into a written agreement with the Applicant signed by the Contract Signer on the Applicant's behalf. That agreement is for a specified term and provides that, until the EV Authority is revoked, the Applicant is obligated under the Subscriber Agreement for all EV SSL Certificates requested or approved by that Certificate Approver; it also provides for authenticating the Certificate Approver, for periodic re-confirmation of the EV Authority, for the secure procedures by which revocation of that authority is notified, and for such other precautions as are reasonably necessary (per [EVG Section 3.2.2.8.4](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32284-pre-authorized-certificate-approver)); thereafter the agreement governs. For EV SSL Certificates requested through the self-service process or the ACME automated process, approval is given per account: the Applicant first enters into a written agreement in the pre-authorized manner described above, designating the holder of the account as the Certificate Approver, and this Certification Center completes the checks in items 1 to 3 of this Part and in [Part C](#325-validation-of-authority) before approving the account. After the account is approved, the digital signature made with the chip card used to log in to the account (self-service process), or the signature made with the ACME account Private Key bound to the account by an External Account Binding (EAB) key (ACME automated process), serves as that Certificate Approver's signature on, and approval of, each EV SSL Certificate Request submitted.

5. **Name, title and authority of the Certificate Requester**: the name and title of the Certificate Requester are confirmed by the Certificate Approver at the time of approval, or with the Applicant using a Verified Method of Communication; the authority of the Certificate Requester is confirmed through the list of Authorized Certificate Requesters and the Reliable Method of Communication in Part A, and the EV SSL Certificate Request it submits is approved by the Certificate Approver under item 4.

**C. Final Cross-Correlation and Due Diligence for EV SSL Certificates**

After all of the verification processes above are completed, a person who is not responsible for the collection of the information reviews all of the information and documentation assembled in support of the EV SSL Certificate application and looks for discrepancies or other details requiring further explanation. This Certification Center obtains and documents further explanation or clarification from the Applicant, the Certificate Approver, the Certificate Requester, a QIIS, and/or other sources of information, as necessary, to resolve those discrepancies or details. This Certification Center refrains from issuing the EV SSL Certificate until the entire corpus of information and documentation is such that issuance will not communicate factual information that this Certification Center knows, or the exercise of due diligence should discover, to be inaccurate; if satisfactory explanation or additional documentation is not received within a reasonable time, this Certification Center declines the EV SSL Certificate Request and notifies the Applicant accordingly.

Where some or all of the supporting documentation is in a language other than this Certification Center's normal operating language, this review is performed by employees under its control who have appropriate training, experience, and judgment in confirming organizational identification and authorization and who meet the qualification requirements of [Section 5.3.2](#532-background-check-procedures); where such employees do not possess the necessary language skills, this Certification Center may rely on language translations of the relevant portions of the documentation received from a Translator.

### 3.2.6 Criteria for Interoperation or Certification

This Certification Center discloses in the CCADB every Cross-Certified Subordinate CA Certificate that identifies a Certification Authority of this Certification Center as the Subject, where this Certification Center arranged for or accepted the establishment of the trust relationship; the disclosed information identifies the Subject certificate, the Issuing CA, and the certificate's validity period (per [BR Section 3.2.6](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#326-criteria-for-interoperation-or-certification)). The current Cross Certificates are listed in [Section 7.1.4.3.2](#71432-certificate-hierarchy-mapping).

This Certification Center discloses each Subordinate CA certificate it issues in the CCADB within 7 calendar days of issuance and before that Subordinate CA begins issuing certificates, and updates that disclosure within 7 calendar days after the Subordinate CA certificate is revoked (per Section 3.2 of the [CCADB Policy](https://www.ccadb.org/policy)).

## 3.3 Identification and authentication for re-key requests

### 3.3.1 Identification and authentication for routine re-key

As the duration of key usage increases, the risk of loss or compromise also increases. Subscribers should regularly re-key to ensure key security. The maximum validity period of Subscriber Certificates issued by this Certification Center is 200 days (the Private Key validity period is the same as the certificate validity period). The maximum validity period of Subscriber Certificates will be progressively shortened in accordance with [Section 6.3.2](#632-certificate-operational-periods-and-key-pair-usage-periods).

Re-keying a certificate means generating a new Public Key and Private Key pair before the certificate expires, and applying to this Certification Center for certificate issuance. This Certification Center will check whether a valid Validation Record exists. If no valid Validation Record is found, this Certification Center must re-perform the initial validation procedure in accordance with [Section 3.2](#32-initial-identity-validation).

### 3.3.2 Identification and authentication for re-key after revocation

After a Subscriber's certificate is revoked, the Subscriber must undergo the initial validation procedure specified in [Section 3.2](#32-initial-identity-validation) and re-apply for a new certificate.

## 3.4 Identification and authentication for revocation request

When a revocation event described in [Section 4.9.1](#491-circumstances-for-revocation) occurs, the person authorized to request revocation (as described in [Section 4.9.2](#492-who-can-request-revocation)) shall submit a revocation request to this Certification Center. This Certification Center adopts the following identification and authentication procedures for different business processes:

| Business Process | Description |
|---|---|
| **Manual Process** | This Certification Center or Registration Authority shall verify the identity of the Applicant (e.g., the original Applicant, the legal representative, or an authorized agent). In addition to identity verification, the authenticity of the request data shall be verified in accordance with [Section 3.2](#32-initial-identity-validation). Where the revocation request is not submitted by the original Applicant or the legal representative, or the authenticity of the request cannot be confirmed from the documents provided, the Legal Entity or organization shall be contacted to confirm the specific facts for certificate revocation. If processed through an agent, the authorization requirements of [Section 3.2.5](#325-validation-of-authority) must be satisfied. |
| **Self-Service Process** | The Applicant must log in using the originally established Self-Service issuance platform account. Upon login, the Applicant must use a smart card issued by this Certification Center to perform a digital signature. After the signature is verified by the system, identity authentication is deemed passed. The system will verify whether the account has the authority to manage the certificate in question. |
| **ACME Automated Process** | The revocation request must comply with the [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555) specification. The ACME Client must sign the revocation request message using the ACME account Private Key corresponding to the certificate. Upon receiving the request, this Certification Center will verify the digital signature using the ACME account Public Key bound in the database. The system verifies that the ACME account is the legitimate account that originally applied for the certificate; only after successful verification will the transaction request be accepted. In addition, in accordance with Section 7.6 of [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555#section-7.6), this Certification Center also accepts a revocation request signed with the Private Key corresponding to the certificate, or submitted by an ACME account holding valid authorizations for all identifiers in the certificate. |

# 4 CERTIFICATE LIFE-CYCLE OPERATIONAL REQUIREMENTS

## 4.1 Certificate Application

This Certification Center operates under different business processes: "Manual Certificate Issuance," "Self-Service Certificate Issuance," and "ACME Automated Certificate Issuance."

### 4.1.1 Who can submit a certificate application

The representative or agent of a Legal Entity or organization wishing to apply for a certificate serves as the certificate Applicant.

### 4.1.2 Enrollment process and responsibilities

Certificate applicants shall read the Subscriber agreement in advance and fully understand the rights and obligations associated with using the certificate. The Applicant may complete identity verification through the online registration system and confirm agreement to the relevant terms, or prepare and sign a certificate application form in writing and submit it to this Certification Center for processing of the certificate application.

Each certificate request (including a paper application form, an online application, and an ACME request) contains a certification by, or on behalf of, the Applicant that all of the information contained therein is correct; for applications through the ACME automated process, that certification is made in the contract entered into when the account is applied for.

Certificate applicants must generate the certificate key pair and the corresponding PKCS#10 certificate request file (hereinafter referred to as CSR) themselves, and submit it through a secure channel provided by this Certification Center.

## 4.2 Certificate application processing

This Certification Center operates under different business processes: "Manual Issuance Process," "Self-Service Issuance Process," and "ACME Automated Issuance Process."

### 4.2.1 Performing identification and authentication functions

The identification and authentication procedures for Subscriber Certificate applications are as follows:

The representative of the Legal Entity or organization, or an agent designated by the representative, serves as the certificate Applicant.

Overview of identification and authentication procedures for each business process:

| Business Process | Description |
|---|---|
| **Manual Process** | The Applicant does not need to establish an account in advance. For first-time applications, the Applicant shall submit certificate request information and identification materials through secure electronic channels (such as online portal, email, or APIs), and this Certification Center/Registration Authority (CA/RA) performs identity verification in a secure manner. The Applicant must generate the CSR and deliver it to this Certification Center through a secure channel. |
| **Self-Service Process** | The Applicant must establish a Self-Service issuance platform account. The Applicant must sign a contract with this Certification Center in advance, specifying the domain names in the contract. After review and approval by this Certification Center, a platform account is established and bound to the domain name whitelist. The Applicant must use a smart card issued by this Certification Center as login credentials; upon login, a digital signature is performed, and certificate operations may proceed only after successful signature verification. For certificate re-key, the Applicant logs into the issuance platform independently to perform the operation; for additional domain purchases, a separate contract must be signed with this Certification Center. The Applicant must generate the CSR and log into the issuance platform to complete the certificate application request via file upload. |
| **ACME Automated Process** | The Applicant must establish an automated issuance platform account. Before the first application, a contract must be signed specifying the domain names. The Applicant must provide organization registration documentation, register an automated account on the online platform, and upon review and approval by this Certification Center, the account is established and bound to the domain name whitelist. The Applicant must install an ACME Client in advance and obtain an External Account Binding (EAB) key to complete account association. This Certification Center binds the Subscriber identity with the ACME account Public Key. When executing ACME transactions, the ACME account Private Key must be used to sign the transaction messages; this Certification Center will accept the transaction request only after successful signature verification. For certificate re-key, within the contract validity period, the Applicant may use the ACME Client to obtain a new certificate directly from this Certification Center; for additional domain purchases, a separate contract must be signed with this Certification Center. The ACME Client automatically generates the key pair and CSR, and transmits the certificate request information to this Certification Center via the ACME protocol. |

The certificate Applicant submits the certificate request and a self-generated PKCS#10 format certificate request file (CSR) through secure electronic channels. This Certification Center performs verification by confirming the Applicant's electronic identity identification and the validation procedures defined in [Section 3.2](#32-initial-identity-validation).

**General Verification Requirements**

| Verification Requirement | Description |
|---|---|
| Validation Record validity check | This Certification Center performs validation in accordance with [Section 3.2](#32-initial-identity-validation). If no valid "Organization Validation Record" or "Domain Validation Record" is found, the complete validation procedure must be re-executed. Validation Record validity periods are referenced in [Section 3.2.2](#322-authentication-of-organization-and-domain-identity). |
| Key compliance | This Certification Center checks the Public Key in the CSR by querying the badkeys database (https://badkeys.info/) to ensure it is not a known weak key (e.g., Debian Weak Key). This Certification Center checks whether the Public Key is already in use by another Applicant: the same Applicant may use the same Public Key in more than one of its certificates, but different Applicants (for example, different Legal Entities or organizations) must not hold the same Public Key. Where this Certification Center finds that different Applicants hold the same Public Key, issuance is not permitted. If a check fails, the certificate is not issued. |
| Missing application information | Where a certificate request does not contain all the necessary information about the Applicant, this Certification Center obtains the remaining information from the Applicant or, having obtained it from a reliable, independent, third-party data source, confirms it with the Applicant (per [BR Section 4.2.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#421-performing-identification-and-authentication-functions)). For EV SSL Certificate requests, this Certification Center additionally confirms the data with the Certificate Approver or Contract Signer rather than the Certificate Requester (per [EVG Section 9.6.3](https://cabforum.org/working-groups/server/extended-validation/guidelines/#963-subscriber-representations-and-warranties)). |
| Subject name restriction | The issuance system of this Certification Center automatically verifies that the certificate Common Name (CN) or Subject Alternative Name (SAN) does not contain an Internal Name or a reserved IP address. |
| EV SSL Certificate restriction | When applying for an EV SSL Certificate, the CN or SAN dNSName shall not contain a Wildcard Domain, and the SAN shall not contain an IP address (iPAddress). |
| High Risk Certificate Requests | This Certification Center maintains documented procedures that identify High Risk Certificate Requests and require additional verification activity before approval; this requirement applies equally to EV SSL Certificates. Before each issuance, every process automatically checks the domain names against the malware and phishing lists published by Google Safe Browsing through the Google Safe Browsing API; where there is a match, the certificate is not issued. For EV SSL Certificates, the denied lists and legal block lists are checked in accordance with [Section 3.2.2.1](#3221-identity), Part B, item (v). Where a Domain Name in an EV SSL Certificate request contains mixed character sets, a Validation Specialist visually compares it with known high-risk domains; where a similarity is found, the request is flagged as high risk, undergoes enhanced manual verification by a Validation Specialist until the Applicant and the target in question are confirmed to be the same organization, and requires supervisory review before approval (per [EVG Section 3.2.2.7.1](https://cabforum.org/working-groups/server/extended-validation/guidelines/#32271-verification-requirements), item 2); where the risk cannot be resolved, the certificate is not issued. |

**Applicant roles for EV SSL Certificates**

The following Applicant roles are required for the issuance of an EV SSL Certificate (see [EVG Section 4.2.1](https://cabforum.org/working-groups/server/extended-validation/guidelines/#421-performing-identification-and-authentication-functions)); the name, title, agency, and authority of each role are verified under [Section 3.2.5](#325-validation-of-authority).

| Applicant Role | Description |
|---|---|
| Certificate Requester | A natural person who submits an EV SSL Certificate Request. That person is either the Applicant, employed by the Applicant, an authorized agent who has express authority to represent the Applicant, or a third party (such as an ISP or hosting company) that completes and submits an EV SSL Certificate Request on behalf of the Applicant. An EV SSL Certificate Request is submitted by an authorized Certificate Requester. |
| Certificate Approver | A natural person who approves an EV SSL Certificate Request. That person is either the Applicant or employed by the Applicant, and has express authority to represent the Applicant to act as a Certificate Requester and to authorize other employees or third parties to act as a Certificate Requester, and to approve EV SSL Certificate Requests submitted by other Certificate Requesters. An EV SSL Certificate Request is approved by an authorized Certificate Approver. |
| Contract Signer | A natural person who signs the Subscriber Agreement. That person is either the Applicant or employed by the Applicant, and has authority on behalf of the Applicant to sign Subscriber Agreements. A Subscriber Agreement applicable to a requested EV SSL Certificate is signed by an authorized Contract Signer. |
| Applicant Representative | Where this Certification Center and the Subscriber are affiliated, a natural person who acknowledges and agrees to the Terms of Use applicable to the requested EV SSL Certificate. That person is either the Applicant, employed by the Applicant, or an authorized agent who has express authority to represent the Applicant, and who has authority on behalf of the Applicant to acknowledge and agree to the Terms of Use. |

The Applicant may authorize one individual to occupy two or more of these roles, and may authorize more than one individual to occupy any of these roles.

**Review Result**

After verifying the application materials, this CA determines whether to accept the application, request supplementary materials, or reject the application based on the verification results. Upon decision to accept, the process proceeds to the issuance phase.

### 4.2.2 Approval or rejection of certificate applications

Applications that successfully complete the "Identification and Authentication Procedures" described in [Section 4.2.1](#421-performing-identification-and-authentication-functions) are deemed to have passed the review, and the Applicant obtains the status of a Subscriber of this Certification Center. If the Applicant fails to pass the above procedures, this Certification Center shall reject the certificate application.

To comply with international security standards, this Certification Center strictly prohibits the issuance of certificates containing the following attributes:

1. **Internal Names:** The Common Name (CN) or Subject Alternative Name (SAN) of the certificate shall not use internal names. Specifically, the domain suffix must be listed in the IANA Root Zone Database (https://www.iana.org/domains/root/db); if the domain ending is not on that list, it is considered a non-publicly resolvable internal name.
2. **Reserved IP Addresses:** The CN or SAN of the certificate shall not contain reserved IP addresses. The definition follows the IANA IPv4 Special-Purpose Address Registry and IANA IPv6 Special-Purpose Address Registry (https://www.iana.org/assignments/iana-ipv4-special-registry/iana-ipv4-special-registry.xhtml and https://www.iana.org/assignments/iana-ipv6-special-registry/iana-ipv6-special-registry.xhtml).
3. **IP Reverse Zone Suffix:** The CN or SAN of the certificate shall not contain a Domain Name that ends in in-addr.arpa or ip6.arpa.
4. **Onion Domain Names:** This Certification Center does not issue certificates containing Onion Domain Names.

### 4.2.3 Time to process certificate applications

No stipulation.

### 4.2.4 CAA Record Parameter Processing

The Issuer Domain Name that this Certification Center recognizes in CAA issue and issuewild records as permitting it to issue is twca.com.tw. When processing CAA records for an Applicant's domain, this Certification Center processes the `accounturi` and `validationmethods` parameters defined in [RFC 8657](https://datatracker.ietf.org/doc/html/rfc8657) when present, in addition to the issuer domain match performed under [RFC 8659](https://datatracker.ietf.org/doc/html/rfc8659). This Certification Center processes the issue, issuewild, and iodef property tags as specified in RFC 8659, and does not issue a certificate if it encounters an unrecognized property tag with the critical flag set.

**`accounturi` Parameter**

The only `accounturi` value accepted by this Certification Center is the URL of the requesting ACME account, in the following form:

```
https://ssl2.twca.com.tw/acme_m2/acct/{accountID}
```

where `{accountID}` is the account identifier assigned by this Certification Center at the time of ACME account registration. Matching is performed by byte-for-byte case-sensitive comparison against the ACME account URL of the account submitting the certificate request.

For certificate applications submitted through the Manual or Self-Service processes, the `accounturi` parameter cannot be matched, since these processes do not utilize ACME accounts. Accordingly, if every CAA `issue` (or `issuewild`, for Wildcard Certificates) record authorizing this Certification Center for the relevant domain includes a non-empty `accounturi` parameter, the certificate application shall be rejected.

**`validationmethods` Parameter**

The `validationmethods` parameter is processed in accordance with [RFC 8657](https://datatracker.ietf.org/doc/html/rfc8657) and [BR Section 4.2.2.1.2](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#42212-caa-parameters). The labels recognized by this Certification Center, mapped to the validation methods listed in [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control), are:

| Label | Validation Method | Reference |
|---|---|---|
| `ca-tbr-4` | Email to a Constructed Address (sunset March 15, 2028; see [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control)) | [BR 3.2.2.4.4](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32244-email-to-a-constructed-address) |
| `ca-tbr-7` | DNS Change Validation | [BR 3.2.2.4.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32247-dns-change) |
| `dns-01` | DNS Change Validation via ACME `dns-01` Challenge ([RFC 8555 §8.4](https://datatracker.ietf.org/doc/html/rfc8555#section-8.4)) | [BR 3.2.2.4.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32247-dns-change) |
| `ca-tbr-18` | Website Change Validation | [BR 3.2.2.4.18](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322418-agreed-upon-change-to-website-v2) |
| `ca-tbr-19` / `http-01` | Website Change Validation (ACME) | [BR 3.2.2.4.19](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322419-agreed-upon-change-to-website---acme) |
| `ca-tbr-22` / `dns-persist-01` | Long-Lived DNS Validation | [BR 3.2.2.4.22](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322422-dns-txt-record-with-persistent-value) |

Label matching is performed case-sensitively. A `validationmethods` parameter shall be deemed unsatisfied if none of its labels corresponds to the validation method actually used to validate domain control.

## 4.3 Certificate issuance

This Certification Center operates under different business processes: "Manual Process," "Self-Service Process," and "ACME Automated Process."

### 4.3.1 CA actions during certificate issuance

This Certification Center executes certificate issuance according to the following processes:

Overview of certificate issuance for each business process:

| Business Process | Description |
|---|---|
| **Manual Process** | The system automatically checks the digital signature of the CSR to confirm integrity and proof of Private Key ownership; simultaneously, it verifies that the Subject Distinguished Name (DN) and extension fields are consistent with the application form and do not contain internal names or reserved IP addresses. The reviewing personnel log into the management console through two-factor authentication and perform the organization and domain validation defined in [Section 3.2](#32-initial-identity-validation). A "dual-review system" is employed, where another personnel member confirms accuracy before issuance. This process shall not use the ACME-related validation methods ([BR Section 3.2.2.4.19](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322419-agreed-upon-change-to-website---acme), [BR Section 3.2.2.4.22](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322422-dns-txt-record-with-persistent-value) and [BR Section 3.2.2.5.6](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32256-acme-http-01-method-for-ip-addresses)). |
| **Self-Service Process** | The Subscriber logs into the Self-Service issuance platform account, generates the CSR, and initiates the certificate application request. The system automatically determines whether the organization and domain Validation Records are still valid. If the records are valid, the certificate is issued immediately; if invalid, the process is terminated and transferred to this Certification Center's personnel for manual review and validation. This process shall not use the ACME-related validation methods ([BR Section 3.2.2.4.19](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322419-agreed-upon-change-to-website---acme), [BR Section 3.2.2.4.22](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322422-dns-txt-record-with-persistent-value) and [BR Section 3.2.2.5.6](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32256-acme-http-01-method-for-ip-addresses)). |
| **ACME Automated Process** | The ACME Client automatically generates the key pair and CSR, transmitted through a TLS channel compliant with [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555). The ACME Server automatically verifies the signature, Private Key ownership, and domain whitelist compliance. If verification passes, the certificate is automatically issued; if it fails, the automated process is terminated and transferred to this Certification Center's personnel for manual account configuration. The domain validation methods used in this process are limited to [BR Section 3.2.2.4.19](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322419-agreed-upon-change-to-website---acme) (ACME `http-01`), [BR Section 3.2.2.4.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32247-dns-change) (ACME `dns-01`), and [BR Section 3.2.2.4.22](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#322422-dns-txt-record-with-persistent-value) (`dns-persist-01`); the IP address validation method is limited to [BR Section 3.2.2.5.6](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#32256-acme-http-01-method-for-ip-addresses) (ACME `http-01`). This Certification Center's ACME service supports ACME Renewal Information (ARI) as defined in [RFC 9773](https://datatracker.ietf.org/doc/html/rfc9773). |

**Pre-Issuance General Verification Requirements**

| Verification Requirement | Description |
|---|---|
| Certificate lint check | This Certification Center uses third-party tools (zlint and pkilint) for verification to ensure the certificate complies with [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280), CABF [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/), and [EVG](https://cabforum.org/working-groups/server/extended-validation/guidelines/) specifications. If the check fails, the certificate will not be issued. |
| CAA record check | This Certification Center performs a CAA record check before certificate issuance; for the recognized Issuer Domain Name, see [Section 4.2.4](#424-caa-record-parameter-processing). If the check fails, the certificate will not be issued. Refer to [Section 3.2.2.8](#3228-caa-records) for the specifications. |
| Public Suffix List check | For Wildcard Domain Names, the issuance system automatically compares the name against the Public Suffix List to confirm that the wildcard "*." does not sit directly in front of a public suffix. If the check fails, the certificate will not be issued. Refer to [Section 3.2.2.6](#3226-wildcard-domain-validation) for the specifications. |
| High Risk Certificate Request check | Before each issuance, the system automatically checks the request against the Google Safe Browsing lists in every process under [Section 4.2.1](#421-performing-identification-and-authentication-functions); where there is a match, the certificate is not issued. |

**Certificate Transparency**

This Certification Center uploads a Precertificate to CT (Certificate Transparency) log servers before issuing the final certificate. The certificate is issued only after SCTs (Signed Certificate Timestamps) meeting the Chrome and Apple CT policies have been obtained from distinct CT logs: at least 2 for a certificate validity period of 180 days or less, and at least 3 for a longer validity period; these SCTs come from at least 2 distinct log operators, and at least 1 of them comes from a log compliant with [RFC 6962](https://datatracker.ietf.org/doc/html/rfc6962). After issuance, the final certificate is also uploaded to the CT log servers.

**Certificate Validity Period Restriction**

The certificate start date (notBefore) in Subscriber Certificates issued by this Certification Center is not backdated. That is, the certificate start date will not be earlier than the actual time of certificate issuance.

### 4.3.2 Notification to subscriber by the CA of issuance of certificate

This Certification Center notifies the Subscriber by telephone or email upon completion of certificate issuance. Subscribers using ACME automated certificate issuance will not be separately notified.

## 4.4 Certificate acceptance

### 4.4.1 Conduct constituting certificate acceptance

Upon receiving a certificate issued by this Certification Center, the Subscriber shall perform the following procedures:

1. Confirm that the certificate content is consistent with the information provided at the time of application and that it contains the Subscriber's correct information.
2. Verify that the Public Key in the certificate matches the Public Key information in the PKCS#10 certificate request file.
3. The Subscriber must validate the certificate chain, checking the correctness, integrity, and validity of each certificate in the chain, whether the certificate has been revoked, whether the certificate validity period has expired, and whether it was indeed issued by this Certification Center.
4. If the above procedures cannot be completed, the Subscriber shall immediately notify this Certification Center to revoke the certificate and may re-initiate the certificate issuance procedure described in [Section 4.3](#43-certificate-issuance).

The Subscriber, upon receiving the applied-for certificate, must confirm full understanding of and agreement to the rights and obligations associated with certificate use. If the Subscriber disagrees, the certificate is deemed rejected, and this Certification Center shall revoke the certificate.

This Certification Center only accepts certificate modification requests from Subscribers within 7 days after certificate issuance.

### 4.4.2 Publication of the certificate by the CA

Upon completion of the certificate issuance procedure, this Certification Center publishes the Subscriber Certificate in the Repository.

### 4.4.3 Notification of certificate issuance by the CA to other entities

No stipulation.

## 4.5 Key pair and certificate usage

### 4.5.1 Subscriber private key and certificate usage

The purpose, applicable scope, and restrictions of Subscriber Certificates are in accordance with [Section 1.4](#14-certificate-usage).

Subscribers shall properly protect their Private Keys. In the event of suspected misuse, exposure, loss, or other security concerns, Subscribers must report to this Certification Center.

### 4.5.2 Relying party public key and certificate usage

Before relying on a Subscriber Certificate issued by this Certification Center, Relying Parties shall at a minimum perform the following procedures to determine whether to trust the certificate:

1. Obtain the self-signed certificate of this Certification Center's Root Certification Authority (RCA) through an appropriate and secure channel.
2. Verify that the RCA self-signed certificate, the Subordinate CA certificate, and the Subscriber Certificate have not expired.
3. Using the Public Key of the RCA self-signed certificate, verify that the digital signature on the Subordinate CA certificate is valid and has not been revoked.
4. Using the Public Key of the Subordinate CA certificate, verify that the digital signature on the Subscriber Certificate is valid.
5. Verify that the Subscriber Certificate has not been revoked by the Subordinate CA.

If the above verifications cannot be passed, it indicates that the Subscriber Certificate obtained by the Relying Party was not issued by this Certification Center, or the certificate is no longer valid, and the Relying Party should not trust the Subscriber Certificate.

## 4.6 Certificate renewal

Certificate renewal refers to re-issuing a certificate with the same key, a different serial number, and an extended validity period, while the Subscriber identification information remains unchanged.

This Certification Center does not provide certificate renewal service. A Subscriber who needs a new certificate before expiry of an existing certificate shall perform a certificate re-key (generating a new key pair) in accordance with [Section 4.7](#47-certificate-re-key).

### 4.6.1 Circumstance for certificate renewal

Not applicable (this Certification Center does not provide certificate renewal service).

### 4.6.2 Who may request renewal

Not applicable (this Certification Center does not provide certificate renewal service).

### 4.6.3 Processing certificate renewal requests

Not applicable (this Certification Center does not provide certificate renewal service).

### 4.6.4 Notification of new certificate issuance to subscriber

Not applicable (this Certification Center does not provide certificate renewal service).

### 4.6.5 Conduct constituting acceptance of a renewal certificate

Not applicable (this Certification Center does not provide certificate renewal service).

### 4.6.6 Publication of the renewal certificate by the CA

Not applicable (this Certification Center does not provide certificate renewal service).

### 4.6.7 Notification of certificate issuance by the CA to other entities

Not applicable (this Certification Center does not provide certificate renewal service).

## 4.7 Certificate re-key

Certificate re-key refers to generating a new Public Key and Private Key pair and applying to the Certification Authority for certificate issuance using the original registration information. The following describes each business process:

| Business Process | Description |
|---|---|
| **Manual Process** | The Applicant submits a certificate re-key request through secure electronic channels (such as online portal, email, etc.). The Applicant must generate the CSR and deliver it to this Certification Center through a secure channel. The validation personnel log into the management console through two-factor authentication and perform the organization and domain validation defined in [Section 3.2](#32-initial-identity-validation). A "dual-review system" is employed, where another personnel member confirms accuracy before issuance. |
| **Self-Service Process** | The Applicant completes the certificate re-key process through the Self-Service issuance platform account. The Applicant must use a smart card issued by this Certification Center as login credentials; upon login, a digital signature is performed, and certificate re-key operations may proceed only after successful signature verification. The Applicant must generate the CSR and complete the process by uploading the file on the platform. The system automatically determines whether the organization and domain Validation Records are still valid. If the records are valid, the certificate is issued immediately; if invalid, the process is terminated and transferred to this Certification Center's personnel for manual review and validation. |
| **ACME Automated Process** | The ACME Client automatically generates the key pair and CSR, transmitted through a TLS channel compliant with [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555). The ACME Server automatically verifies the signature, Private Key ownership, and domain whitelist compliance. If verification passes, the certificate is automatically issued; if it fails, the automated process is terminated and transferred to this Certification Center's personnel for manual account configuration. |

### 4.7.1 Circumstance for certificate re-key

In accordance with the provisions of [Section 3.3.1](#331-identification-and-authentication-for-routine-re-key).

### 4.7.2 Who may request certification of a new public key

Subscribers are authorized to re-key certificates.

### 4.7.3 Processing certificate re-keying requests

1. Identification and authentication of the Subscriber is performed in accordance with [Section 3.3](#33-identification-and-authentication-for-re-key-requests).
2. Certificate issuance is performed in accordance with [Section 4.3](#43-certificate-issuance).

### 4.7.4 Notification of new certificate issuance to subscriber

In accordance with the provisions of [Section 4.3.2](#432-notification-to-subscriber-by-the-ca-of-issuance-of-certificate).

### 4.7.5 Conduct constituting acceptance of a re-keyed certificate

In accordance with the provisions of [Section 4.4](#44-certificate-acceptance).

### 4.7.6 Publication of the re-keyed certificate by the CA

In accordance with the provisions of [Section 4.4.2](#442-publication-of-the-certificate-by-the-ca).

### 4.7.7 Notification of certificate issuance by the CA to other entities

In accordance with the provisions of [Section 4.4.3](#443-notification-of-certificate-issuance-by-the-ca-to-other-entities).

## 4.8 Certificate modification

Certificate modification refers to re-issuing a certificate (generating a new certificate serial number) to the Subscriber when the Public Key remains unchanged but the Subscriber identification information recorded in the certificate needs to be modified.

This Certification Center only accepts certificate modification requests from Subscribers within 7 days after certificate issuance. If more than 7 days have passed and the Subscriber's identification information or other information recorded in the certificate needs to be modified, the certificate shall be revoked in accordance with [Section 4.9](#49-certificate-revocation-and-suspension), and a new certificate shall be re-applied for in accordance with Sections [4.1](#41-certificate-application), [4.2](#42-certificate-application-processing), [4.3](#43-certificate-issuance), and [4.4](#44-certificate-acceptance).

### 4.8.1 Circumstance for certificate modification

Where, within 7 days after certificate issuance, the Subscriber requests correction of the Subscriber identification information recorded in the certificate. After 7 days, revocation and re-application apply in accordance with [Section 4.8](#48-certificate-modification).

### 4.8.2 Who may request certificate modification

The Subscriber, or an Authorized Certificate Requester recorded in accordance with [Section 3.2.5](#325-validation-of-authority).

### 4.8.3 Processing certificate modification requests

Identification and authentication of the Subscriber is performed in accordance with [Section 3.2](#32-initial-identity-validation), and verification and issuance are performed in accordance with [Section 4.2](#42-certificate-application-processing) and [Section 4.3](#43-certificate-issuance). The original certificate shall be revoked in accordance with [Section 4.9](#49-certificate-revocation-and-suspension).

### 4.8.4 Notification of new certificate issuance to subscriber

In accordance with [Section 4.3.2](#432-notification-to-subscriber-by-the-ca-of-issuance-of-certificate).

### 4.8.5 Conduct constituting acceptance of modified certificate

In accordance with [Section 4.4](#44-certificate-acceptance).

### 4.8.6 Publication of the modified certificate by the CA

In accordance with [Section 4.4.2](#442-publication-of-the-certificate-by-the-ca).

### 4.8.7 Notification of certificate issuance by the CA to other entities

In accordance with [Section 4.4.3](#443-notification-of-certificate-issuance-by-the-ca-to-other-entities).

## 4.9 Certificate revocation and suspension

When a revocation situation occurs, the relevant certificate shall be revoked and added to the CRL/OCSP. Revoked certificates must be included in all subsequently published CRL/OCSP records until the certificate expires.

### 4.9.1 Circumstances for revocation

#### 4.9.1.1 Reasons for Revoking a Subscriber Certificate

This Certification Center shall revoke a certificate within 24 hours, and use the corresponding CRLReason (see [Section 7.2.2](#722-crl-and-crl-entry-extensions)), if one or more of the following occurs:

1. The Subscriber requests in writing, without specifying a CRLReason, that this Certification Center revoke the certificate (unspecified (0), which results in no reasonCode extension being provided in the CRL).
2. The Subscriber notifies this Certification Center that the original certificate request was not authorized and does not retroactively grant authorization (privilegeWithdrawn (9)).
3. This Certification Center obtains evidence that the Subscriber's Private Key corresponding to the Public Key in the certificate suffered a Key Compromise (keyCompromise (1)).
4. This Certification Center is made aware of a demonstrated or proven method that can easily compute the Subscriber's Private Key based on the Public Key in the certificate, including but not limited to the weak keys referred to in [Section 6.1.1](#611-key-pair-generation) (such as Debian weak keys) (keyCompromise (1)).
5. This Certification Center obtains evidence that the validation of domain authorization or control for any Fully-Qualified Domain Name or IP address in the certificate should not be relied upon, including cases where CAA checking was not performed correctly or where issuance was not permitted according to the CAA records under [Section 3.2.2.8](#3228-caa-records) (superseded (4)).

Where a Root Store Program requests that this Certification Center revoke a certificate, this Certification Center revokes it within 24 hours of receiving that request, using the corresponding CRLReason.

This Certification Center must revoke a certificate within 5 days, using the corresponding CRLReason, if one or more of the following occurs:

6. The certificate no longer complies with the requirements of [Section 6.1.5](#615-key-sizes) and [Section 6.1.6](#616-public-key-parameters-generation-and-quality-checking) (superseded (4)).
7. This Certification Center obtains evidence that the certificate was misused (privilegeWithdrawn (9)).
8. This Certification Center is made aware that the Subscriber has violated one or more of its material obligations under the Subscriber Agreement or Terms of Use (privilegeWithdrawn (9)).
9. This Certification Center is made aware of any circumstance indicating that use of a Fully-Qualified Domain Name or IP address in the certificate is no longer legally permitted (e.g., a court or arbitrator has revoked a Domain Name Registrant's right to use the Domain Name) (cessationOfOperation (5)).
10. This Certification Center is made aware that a Wildcard Certificate has been used to authenticate a fraudulently misleading subordinate Fully-Qualified Domain Name (privilegeWithdrawn (9)).
11. This Certification Center is made aware of a material change in the information contained in the certificate (privilegeWithdrawn (9)).
12. This Certification Center is made aware that the certificate was not issued in accordance with the BR, the EVG, or this Statement (superseded (4)).
13. This Certification Center determines or is made aware that any of the information appearing in the certificate is inaccurate (privilegeWithdrawn (9)).
14. This Certification Center's right to issue certificates under the BR expires or is revoked or terminated, unless arrangements have been made to continue maintaining the CRL/OCSP Repository (unspecified (0)).
15. Revocation is required by this Statement for a reason that is not otherwise specified in this Section (unspecified (0)).
16. This Certification Center is made aware of a demonstrated or proven method that exposes the Subscriber's Private Key to compromise, or there is clear evidence that the specific method used to generate the Private Key was flawed (keyCompromise (1)).
17. The Private Key associated with the Subscriber's certificate has been lost or damaged.
18. Circumstances for certificate modification as described in [Section 4.8](#48-certificate-modification).

#### 4.9.1.2 Reasons for Revoking a Subordinate CA Certificate

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
2. This Certification Center.
3. The competent authority or a court.
4. Persons other than those listed above who suspect that a certificate key has been compromised or have other security concerns may also notify this Certification Center. This Certification Center will proceed with the certificate revocation procedure after confirming the report is valid. For contact information, please refer to [Section 1.5.2](#152-contact-person).

### 4.9.3 Procedure for revocation request

This Certification Center accepts certificate revocation requests 7 x 24. Applicants submit certificate revocation requests in accordance with [Section 3.4](#34-identification-and-authentication-for-revocation-request). For how to report a Key Compromise, certificate misuse, or other problems, see [Section 1.5.2](#152-contact-person). The certificate revocation procedure is described below for each business process:

| Business Process | Description |
|---|---|
| **Manual Process** | Persons authorized to request certificate revocation as defined in [Section 4.9.2](#492-who-can-request-revocation) submit the certificate revocation request. If the revocation request is submitted by the certificate Subscriber, identification is performed in accordance with [Section 3.4](#34-identification-and-authentication-for-revocation-request). Other certificate revocation requests are investigated based on the revocation reasons defined in [Section 4.9.1](#491-circumstances-for-revocation). After this Certification Center completes identification, the revocation operation is completed within the time limits specified in [Section 4.9.1](#491-circumstances-for-revocation). |
| **Self-Service Process** | The Subscriber logs into the Self-Service issuance platform account and submits a certificate revocation request, including the certificate information to be revoked and optionally selecting a Reason Code. The system immediately executes the certificate revocation operation. |
| **ACME Automated Process** | The ACME account owner (i.e., the Subscriber) may perform automated certificate revocation through the ACME Client. The request must comply with the [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555) specification, including the certificate information to be revoked and optionally selecting a Reason Code. The ACME Client must send a revocation request message signed by the ACME account Private Key to this Certification Center to ensure the legitimacy and non-repudiation of the request source. Upon receiving the request, this Certification Center will immediately verify the digital signature using the ACME account Public Key. If the authorization is verified, the system will immediately execute the certificate revocation operation. |

### 4.9.4 Revocation request grace period

The BR and the EVG make no stipulation as to the period within which a Subscriber must submit a revocation request. After becoming aware of a revocation circumstance set out in [Section 4.9.1.1](#4911-reasons-for-revoking-a-subscriber-certificate), the Subscriber shall immediately submit a certificate revocation request.

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

CRLs covering Subscriber Certificates are issued by each Subordinate CA on a schedule twice a day, with the `nextUpdate` field no more than 10 days after the `thisUpdate` field; the value currently configured for that schedule is 4 days.

CRLs covering Subordinate CA certificates are issued by the Root CA on a schedule at least once a day, with the `nextUpdate` field no more than 12 months after the `thisUpdate` field; the value currently configured for that schedule is 1 day.

This Certification Center may adjust the configured schedule values stated in the two preceding paragraphs as operationally required, provided that they remain within the `nextUpdate` limits stated above; in any case, CRLs covering Subscriber Certificates are updated and published at least every 4 days, CRLs covering Subordinate CA certificates are updated and published at least every 12 months, and a CRL is updated and published within 24 hours after any certificate it covers is recorded as revoked.

The CRL issuance system of this Certification Center also provides a forced-issuance function. For the circumstances set out in [Section 4.9.1](#491-circumstances-for-revocation) that require revocation within 24 hours (for example, Key Compromise), this Certification Center triggers that function manually once the revocation has been recorded, and issues and publishes an updated CRL immediately rather than waiting for the scheduled run.

This Certification Center continues issuing CRLs until all Subordinate CA Certificates containing the same Subject Public Key have expired or been revoked, or the corresponding Subordinate CA Private Key has been destroyed.

### 4.9.8 Maximum latency for CRLs (if applicable)

No stipulation.

### 4.9.9 On-line revocation/status checking availability

This Certification Center provides OCSP services, supporting OCSP queries via HTTP GET or POST methods. The response messages comply with the specifications of [RFC 6960](https://datatracker.ietf.org/doc/html/rfc6960) and include a digital signature on the message.

For queries regarding unassigned (or unissued) certificate serial numbers (Unassigned Serial Numbers), this Certification Center's OCSP responder MUST NOT return a "good" status; it MUST return "revoked" or "unknown".

An authoritative OCSP response (that is, a response other than "unknown") is available no more than 15 minutes after a Subscriber Certificate or its corresponding Precertificate is first published or otherwise made available.

For OCSP responses issued by this Certification Center covering the status of Subscriber Certificates and CA certificates, the validity interval (`thisUpdate` to `nextUpdate`) is at least 8 hours and no more than 7 days; the value currently configured is 4 days. For a validity interval of 16 hours or more, this Certification Center provides an updated response before one-half of the validity period has elapsed; for a validity interval of less than 16 hours, it provides an updated response at least 8 hours prior to the `nextUpdate`. This validity interval and update timing meet [BR Section 4.9.9](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#499-on-line-revocationstatus-checking-availability). The `nextUpdate` of an OCSP response is no later than the notAfter of the Delegated Responder certificate included in that response. This Certification Center may adjust the configured value as operationally required, provided that the adjusted value continues to meet these requirements.

The OCSP issuance system of this Certification Center also provides a forced-issuance function. For the circumstances set out in [Section 4.9.1](#491-circumstances-for-revocation) that require revocation within 24 hours (for example, Key Compromise), this Certification Center triggers that function manually once the revocation has been recorded, and issues and publishes an updated OCSP response immediately rather than waiting for the scheduled run.

Where any CA certificate is revoked, this Certification Center updates the OCSP response for that certificate within 24 hours.

For other related details, please refer to [Section 7.3](#73-ocsp-profile).

### 4.9.10 On-line revocation checking requirements

Relying Parties must check the certificate status before deciding to rely on a certificate issued by this Certification Center. If the Relying Party does not use a CRL issued by this Certification Center to check certificate status, the Relying Party must check certificate status through the OCSP service in the manner specified in [Section 4.9.9](#499-on-line-revocationstatus-checking-availability).

For Precertificates that have been uploaded to CT (Certificate Transparency) log servers, if the transaction times out and the certificate is not issued to the Subscriber, this Certification Center shall revoke the Precertificate and add it to the CRL/OCSP. For the update frequency of CRL and OCSP services and other related details, please refer to Sections [4.9.7](#497-crl-issuance-frequency), [4.9.9](#499-on-line-revocationstatus-checking-availability), [7.2](#72-crl-profile), and [7.3](#73-ocsp-profile).

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

The Private Key of this Certification Center is not permitted to be escrowed, and this Certification Center does not provide key escrow services for Subscriber Private Keys.

### 4.12.2 Session key encapsulation and recovery policy and practices

No stipulation.
# 5 MANAGEMENT, OPERATIONAL, AND PHYSICAL CONTROLS

The security controls of this Certification Center, in addition to complying with this Statement, also comply with the "Network and Certificate System Security Requirements" (NCSSR) established by CABF.

This Certification Center defines and maintains an inventory of its CA Infrastructure. The inventory covers the server hosts and database hosts of the certificate systems, the offline Root CA systems, the hardware security modules, and the systems that support the security of the foregoing, namely network communication equipment and network boundary control devices, intrusion detection and prevention devices, logging and monitoring systems, and endpoint protection devices; assets located in the primary machine room, the primary key room, and the standby machine room are all included.

For each asset, the inventory records the machine room in which it is located, its category, host or device designation, asset number, purpose, and IP address; for an asset that operates offline, the IP address field records the offline status instead.

The inventory is jointly maintained by the Company's operations department and information security department, and is updated when an asset is added, replaced, or has its purpose changed. Each asset listed in the inventory is protected against common network and system threats using intrusion detection and prevention controls, as required by the NCSSR.

## 5.1 Physical Security Controls

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

### 5.2.2 Number of Individuals Required per Task

The personnel requirements for each Trusted Role are as follows:

- System Administrator — at least 2 persons.
- Certificate Officer — at least 2 persons.
- Auditor — at least 1 person.
- Operator — at least 2 persons.
- Developer — at least 1 person.

Before completed code is submitted for integration into the production environment, at least two authorized trusted persons must review and confirm it, ensuring the code meets business logic and security requirements before approval for release.

Subscriber Certificate issuance is confirmed by at least 2 persons in Trusted Roles, according to the business process, as follows:

- Manual process: before each Subscriber Certificate is issued, at least 2 persons in Trusted Roles must confirm it before issuance can be executed.
- Self-service process and ACME automated process: the organization validation performed before an account is approved is reviewed by at least 2 persons in Trusted Roles, one of whom verifies the Applicant information while the other approves it; no one person may complete both the verification and the approval alone. After the account is approved, domain validation and certificate issuance are performed automatically by the system; the system issues a certificate only after confirming that the organization validation record remains valid, that domain validation has been completed, and that the pre-issuance checks in [Section 4.3.1](#431-ca-actions-during-certificate-issuance) have been passed. This applies equally to SSL Certificates and EV SSL Certificates.

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

Before any person begins employment with this Certification Center for engagement in the EV Processes, whether as an employee, agent, or independent contractor, this Certification Center additionally performs the following in accordance with [EVG Section 5.3.2](https://cabforum.org/working-groups/server/extended-validation/guidelines/#532-background-check-procedures):

1. Verification of identity: through the personal (physical) presence of the person before trusted persons who perform human resource or security functions, and verification of well-recognized forms of government-issued photo identification (e.g., passports and/or driver's licenses).
2. Verification of trustworthiness: background checks addressing at least confirmation of previous employment, a check of professional references, confirmation of the highest or most-relevant educational qualification obtained, and a search of criminal records (local, state or provincial, and national) where allowed by the jurisdiction in which the person will be employed.

Upon termination of an individual's employment or contracting relationship, this Certification Center disables that individual's access to the CA Infrastructure and to network boundary controls in all forms (including physical access control, system accounts, remote connection privileges, and smart cards) within 24 hours of the termination.

All accounts capable of authenticating to or accessing the CA Infrastructure and network boundary controls (including personnel accounts, service accounts, and privileged accounts) are reviewed by this Certification Center every 3 months to confirm that the account remains necessary and that its privileges remain consistent with the holder's duties, and to remove accounts or privileges that are no longer required. The results of each review are documented.

### 5.3.3 Training Requirements and Procedures

Operational personnel of this Certification Center receive training appropriate to their duties, covering the hardware and software functions required for system operation, operational procedures, certificate issuance review procedures, security control procedures, Disaster Recovery operation specifications, key management operations, this Statement, and other information security-related operational specifications. When there are changes to the certificate system or new systems are added, appropriate training is also provided.

Specifically, this Certification Center enforces strict training and qualification testing for "Validation Specialists" responsible for identity and domain verification tasks. Before allowing a Validation Specialist to perform any verification task, this Certification Center requires the specialist to pass an examination provided by this Certification Center on the information verification requirements outlined in the BR; for Validation Specialists vetting EV SSL Certificates, the examination also covers the EV Certificate validation criteria outlined in the EVG. The CA documents and maintains records proving that each Validation Specialist possesses the skills required for the assigned task before permitting execution. Training for Validation Specialists covers basic Public Key Infrastructure knowledge, authentication and vetting policies and procedures (including this Statement), common threats to the information verification process (including phishing and other social engineering tactics), and the requirements of the [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) and the [EVG](https://cabforum.org/working-groups/server/extended-validation/guidelines/) (per [BR Section 5.3.3](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#533-training-requirements-and-procedures) and [EVG Section 5.3.3](https://cabforum.org/working-groups/server/extended-validation/guidelines/#533-training-requirements)).

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

### 5.3.7 Independent Contractor Controls

If this Certification Center engages outsourced personnel to serve as Operators due to insufficient human resources, this Certification Center must conduct background checks in accordance with the procedures specified in [Section 5.3.2](#532-background-check-procedures), followed by training on job-related knowledge and skills as specified in [Section 5.3.3](#533-training-requirements-and-procedures). In addition to signing confidentiality agreements related to the scope of work, such outsourced personnel must comply with relevant operational regulations and legal requirements. The rights and obligations of such outsourced personnel are the same as those of the internal Operators of this Certification Center.

### 5.3.8 Documentation supplied to personnel

To ensure the normal operation of the certificate management system, this Certification Center must provide relevant operational personnel with the following operational documents for system operation, including at minimum:

- Operating documents for hardware, software operating platforms, network systems and website-related operations, and cryptographic system operations.
- Operating documents related to the certificate management system of this Certification Center.
- This Statement and related operational specification documents.
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
- Records of all verification activities, including at a minimum the information being validated (e.g., the organization name or the applied-for FQDN) and the validation method used (e.g., the BR or EVG section number) (per [BR Section 5.4.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#541-types-of-events-recorded)); for domain validation, the Authorization Domain Name is also recorded under [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control).
- Multi-Perspective Issuance Corroboration (MPIC): for each attempt from each Network Perspective, at least an identifier that uniquely identifies the Network Perspective used, the attempted domain name or IP address, and the result of the attempt (e.g., domain validation pass/fail, CAA permission/prohibition); and, for each domain name or IP address in a certificate request, the corroboration quorum result (e.g., "3/4", meaning three of four attempted Network Perspectives corroborated the determinations made by the Primary Network Perspective).

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

#### 5.7.1.1 Incident Response and Disaster Recovery Plans

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

This Certification Center has established incident response handling procedures and a Disaster Recovery plan, documenting business continuity plans and Disaster Recovery procedures in writing. The content includes notification procedures for Application Software Suppliers, Subscribers, and Relying Parties when disasters, security compromises, and operational interruption events occur. These procedures are tested, reviewed, and updated at least annually by this Certification Center.

This Certification Center defines an "Incident" as: any non-compliance with or violation of this CP/CPS, the CA/Browser Forum Baseline Requirements (such as TLS BR), or Root Store Policies (including the Apple Root Program Policy). Once this Certification Center becomes aware of any incident, it follows the reporting procedures of the CCADB Incident Reporting Guidelines: within 72 hours of becoming aware of the event, this Certification Center discloses a Preliminary or Full Incident Report in CCADB (including Bugzilla), or responds to a Preliminary Incident Report previously created for the incident by a third party reporter; a Full Incident Report is posted within 14 days of the incident’s initial disclosure. Thereafter, the report is updated on or before the "Next update" date recorded in the bug’s "Whiteboard" field; where no such date is recorded, at least every 7 days; and within 3 days of an Action Item being changed, completed, or delayed. For reports whose "Whiteboard" field contains "revocation-delay", updates are provided no less frequently than every 7 days. Comments and questions are answered within 7 days. These activities continue until the incident is closed.

#### 5.7.1.2 Mass Revocation Plans

This Certification Center has established a mass certificate revocation plan that details the procedures for handling mass certificate revocation events. The content includes "Source Confirmation," "Impact Scope Confirmation," "Internal Notification and Incident Response Team Organization," "Response Actions and Procedures," "Plan Training, Testing, and Continuous Improvement," and "Third-Party Assessment." Annual simulation exercises are conducted, and experiences gained from exercises or actual incidents are incorporated into the plan for continuous improvement and enhancement of response capabilities.

### 5.7.2 Recovery Procedures if Computing resources, software, and/or data are corrupted

This Certification Center has established recovery procedures for computer resources, software, and data that have been damaged, and conducts exercises annually.

If the computer equipment of this Certification Center is damaged or inoperable but the signing key has not been compromised, priority is given to restoring the repository, followed by rebuilding certificate issuance, revocation, and management capabilities; each service is restored within the Recovery Time Objective (RTO) set out in the Company's Business Continuity Plan (BCP).

### 5.7.3 Recovery Procedures after Key Compromise

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

**Certification Center Key Pair:**

- This Certification Center develops a key generation script and generates the Key Pair in accordance with the script.
- In accordance with [Section 6.2.1](#621-cryptographic-module-standards-and-controls), this Certification Center uses a Hardware Security Module (HSM) validated as meeting at least FIPS 140-2 Level 3, FIPS 140-3 Level 3, or an appropriate Common Criteria Protection Profile or Security Target at EAL 4 or higher to generate the Key Pair. The Private Key is generated within the HSM and remains stored therein without being disclosed.
- The Key Pair generation process is witnessed by a Qualified Auditor, and the entire process is recorded on video. After generation, the Qualified Auditor issues a report opining that this Certification Center followed its key ceremony (Key Generation Script) during its key and certificate generation process and the controls used to ensure the integrity and confidentiality of the Key Pair.

**Subscriber Key Pair:**

- The Key Pair is generated securely by the Subscriber; this Certification Center does not generate Key Pairs on behalf of Subscribers and does not accept a certificate request using a Key Pair previously generated by this Certification Center.
- This Certification Center uses zlint and pkilint to check that the encoding and parameters of the Public Key carried in the certificate request conform to the applicable requirements, and queries the badkeys database (https://badkeys.info/ ) to determine whether it is a known weak key (including Debian weak keys, keys affected by the ROCA vulnerability, and RSA keys that can be factored using Fermat's factorization method); if the key fails the checks, a certificate will not be issued.
- If the Applicant's Private Key has previously been reported to this Certification Center as compromised through the procedures in [Section 4.9.3](#493-procedure-for-revocation-request) and [Section 4.9.12](#4912-special-requirements-re-key-compromise), this Certification Center rejects the certificate request.
- If there is clear evidence that the specific method used to generate the Private Key was flawed, or this Certification Center is aware of a demonstrated or proven method that exposes the Applicant's Private Key to compromise, this Certification Center rejects the certificate request.

### 6.1.2 Private key delivery to subscriber

The Private Key is generated and securely maintained by the Subscriber; therefore, delivery is not required. Parties other than the Subscriber do not archive the Subscriber's Private Key without the Subscriber's authorization. If this Certification Center or its Registration Authority becomes aware that a Subscriber's Private Key has been communicated to a person or organization not authorized by the Subscriber, this Certification Center revokes all certificates that include the Public Key corresponding to the communicated Private Key.

### 6.1.3 Public key delivery to certificate issuer

The Subscriber's Public Key is transmitted to this Certification Center via a PKCS#10 certificate request file. The transmission method shall use a securely protected channel. Verification of possession of the Private Key is completed in the manner described in [Section 3.2.1](#321-method-to-prove-possession-of-private-key).

### 6.1.4 CA public key delivery to relying parties

This Certification Center shall publish the certificates it issues to the repository for Subscribers and Relying Parties to query and download.

### 6.1.5 Key sizes

The key lengths and algorithms used and accepted by this Certification Center are as follows:

**Certificates of this Certification Center**

Root Certification Authority (RCA) key pairs are RSA with a modulus length of at least 4096 bits; Subordinate CA key pairs are RSA with a modulus length of at least 2048 bits.

**Subscriber Certificates**

For key pairs generated by Subscribers, this Certification Center accepts either of the following:

- RSA key pairs: modulus length of 2048, 3072, or 4096 bits.
- ECDSA key pairs: the key represents a valid point on the NIST P-256 or NIST P-384 elliptic curve.

Before issuance, this Certification Center verifies that the Public Key in the CSR meets the above conditions; where it does not, the certificate is not issued. This Certification Center does not accept algorithms or key lengths other than those stated above.
### 6.1.6 Public key parameters generation and quality checking

RSA: The CA SHALL confirm that the value of the public exponent is an odd number equal to 3 or more. Additionally, the public exponent SHOULD be in the range between 2^16 + 1 and 2^256 - 1. The modulus SHOULD also have the following characteristics: an odd number, not the power of a prime, and have no factors smaller than 752.

ECDSA: The CA SHOULD confirm the validity of all keys using either the ECC Full Public Key Validation Routine or the ECC Partial Public Key Validation Routine.

This Certification Center performs weak key checks (e.g., Debian Weak Key) on keys generated by itself or by Subscribers. If the key fails the check, it is not permitted for use as a certificate key.
### 6.1.7 Key usage purposes (as per X.509 v3 key usage field)

For certificates issued by this Certification Center, key usage purposes refer to the Key Usage and Extended Key Usage extensions described in [Section 7.1.2](#712-certificate-content-and-extensions).

### 6.1.8 Subscriber Key Generation Equipment

The Key Pair generation device for Subscribers is typically the built-in key generation device of the web server or network equipment.

## 6.2 Private Key Protection and Cryptographic Module Engineering Controls

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

### 6.2.8 Activating Private Keys

The Private Key stored in the Cryptographic Module must be activated by 2 or more authorized Certificate Officers after identity authentication. Activation is performed through Smart Card-based authentication of Certificate Officer identity, and the activation procedure controls must comply with the provisions of [Section 5.2](#52-procedural-controls).

### 6.2.9 Deactivating Private Keys

After the Private Key is activated, it is deactivated by either manually shutting down the Cryptographic Module after identity authentication or by automatic logout by the system after 15 minutes of inactivity, to prevent unauthorized use of the Private Key.

### 6.2.10 Destroying Private Keys

When the Private Key usage period of this Certification Center expires, the key is destroyed in the following year in the presence of a Qualified Auditor. The memory locations storing the old Private Key in the Hardware Security Module (HSM) are zeroized to destroy the old Private Key in the HSM.

In addition to destroying the old Private Key in the HSM, backup copies of the old Private Key (three generations retained) are also physically destroyed when the backup expires. However, if the key backup copies must be used for restoration and the restored keys include expired keys, those expired keys are immediately deleted.

### 6.2.11 Cryptographic Module Rating

The Hardware Security Module (HSM) used by this Certification Center must be validated as meeting at least FIPS 140-2 Level 3, FIPS 140-3 Level 3, or an appropriate Common Criteria Protection Profile or Security Target at EAL 4 or higher. CNS 15135 or ISO/IEC 19790 may be used only as an additional standard, at security level 3, and not in place of the validation above. Any such Common Criteria Protection Profile or Security Target shall include requirements to protect the Private Key and other assets against known threats.

## 6.3 Other aspects of key pair management

### 6.3.1 Public key archival

When certificates issued by this Certification Center reach the end of their lifecycle, the certificates are archived and the Public Keys are archived simultaneously.

### 6.3.2 Certificate operational periods and key pair usage periods

The validity periods of Public Keys and Private Keys listed below are identical.

- The Key Pair validity period for the Root Certification Authority (RCA) has a maximum of 9132 days (approximately 25 years, per [TLS BR Section 7.1.2.1.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#71211-root-ca-validity)), including where the RCA's Public Key is also certified in a Cross Certificate. A Root CA newly created on or after July 1, 2026 is valid for no more than 10 years from the date of its submission to a Root Store Program.
- The Subscriber Key Pair validity period equals the Subscriber Certificate validity period, whose maximum is set out in the table below. Per [BR Section 6.3.2](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#632-certificate-operational-periods-and-key-pair-usage-periods), the maximum Subscriber Certificate validity period will be progressively shortened as follows:

| Certificate Not Before >= | Certificate Not Before < | Maximum Subscriber Certificate Validity |
|---|---|---|
| - | March 15, 2026 | 398 days |
| March 15, 2026 | March 15, 2027 | 200 days |
| March 15, 2027 | March 15, 2029 | 100 days |
| March 15, 2029 | - | 47 days |

## 6.4 Activation data

### 6.4.1 Activation data generation and installation

The activation data for the signing Private Key is generated individually by multiple Smart Cards, using a Multi-person (m-of-n) Control duty separation mechanism. The activation data in the Smart Cards is accessed by a card reader, and the Personal Identification Number (hereinafter referred to as PIN) of the Smart Card is used for identity authentication to access the activation data.

### 6.4.2 Activation data protection

The activation data is protected by the controlling Smart Card set. The PIN of the Smart Card is maintained by the custodian and shall not be recorded on any media. If the number of failed login attempts exceeds 3, the Smart Card is locked. When a Smart Card is transferred, the new custodian must reset the PIN.

### 6.4.3 Other aspects of activation data

No stipulation.

## 6.5 Computer security controls

### 6.5.1 Specific computer security technical requirements

This Certification Center and related auxiliary systems provide the following security control functions through the operating system, or through a combination of operating system, software, and physical protection measures:

- Identity authentication and multi-factor login.
- Discretionary access control.
- Security audit capabilities.
- Access control restrictions for various certificate services and Trusted Roles.
- Identification and authentication of Trusted Roles and identities.
- Ensuring the security of communications and databases.
- Secure and trusted channels for Trusted Roles and related identity identification.
- Process integrity and security control protection.

This Certification Center implements information security control measures in accordance with the NCSSR.


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

To prevent network intrusion and sabotage, the hosts of this Certification Center are installed and configured with firewalls, intrusion prevention systems, and antivirus systems to enhance network security. System vulnerability scans are performed at least once every 3 months, penetration testing is performed in accordance with [Section 5.4.8](#548-vulnerability-assessments), and system patch updates are completed within the timeframes specified in the following table, to strengthen protection. This Certification Center classifies identified vulnerabilities using CVSS scoring together with a product context impact assessment, and ensures that review, response, and remediation are completed within the timeframes specified in the following table:

| Severity | Reference criteria | Review deadline | Response deadline | Remediation / mitigation deadline |
|---|---|---|---|---|
| Critical | CVSS >= 9.0, or capable of immediately affecting core trust services, certificate issuance, or a large number of customers | Within 1 working day | Within 7 working days | Within 7 calendar days (or immediate temporary mitigation) |
| High | CVSS 7.0-8.9, capable of causing significant service disruption or data disclosure | Within 1 working day | Within 7 working days | Within 30 calendar days |
| Medium | CVSS 4.0-6.9, limited impact or requiring specific conditions to exploit | Within 1 working day | Within 7 working days | Within 90 calendar days |

Other vulnerabilities that do not reach the severity levels above are addressed in routine patching or version updates. Where a vulnerability is confirmed to be exploited in the wild, its severity is raised to at least "High" even if originally assessed as Medium or Low, and the accelerated handling process is initiated.

The hosts and internal databases of this Certification Center are connected only to the internal network and isolated by firewalls. Only internal host connections are permitted, and identity authentication is required to confirm that the person or system accessing the resources is authorized.

Every remote connection that enables Privileged Access to the CA Infrastructure of this Certification Center satisfies all of the following conditions:

- **Originating workstation**: the connection originates from a laptop computer issued and controlled by the Company and dedicated to this purpose. That computer is subject to the Company's information security monitoring, its operating system patches and antivirus signatures are kept up to date, and file uploads and downloads must use an individually assigned USB device; that computer is also bound, by its registered network interface, to the remote access account, and no other computer may be used to connect.
- **Connection channel**: the connection is made through an encrypted Virtual Private Network (VPN) channel. The channel is temporary and non-persistent, and is torn down when the computer is shut down.
- **Authentication**: authentication uses multi-factor authentication consisting of a smart card and a password.
- **Network boundary control**: the connection is made to the Company's VPN gateway. That gateway is a Network Boundary Control asset located within the Company's network, secured in accordance with the NCSSR, and mediates the remote connection to the production network segment in which the certificate systems reside.

Remote access does not, of itself, confer any operational privileges. The authorization and authentication requirements set out earlier in this Section apply equally to management operations performed remotely and to those performed on site. The Root Certification Authority (RCA) certificate system remains offline and is not reachable by any remote connection.

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

The certificates of this Certification Center and the certificates issued to Subscribers are X.509 v3, with the following fields (field definitions comply with the [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) standard):

| Field | Description |
|-------|-------------|
| Version | Fixed as v3 |
| Serial Number | Certificate serial number |
| Signature Algorithm | The signature algorithm used for issuing certificates. This Certification Center supports: sha256WithRSAEncryption, sha384WithRSAEncryption |
| Signature Value | Signature value generated by the issuer's signing |
| Issuer | Subject information of the CA corresponding to this certificate |
| Validity Not Before | Certificate start date. For Subscriber Certificates, this value is within 48 hours of the time of the certificate signing operation |
| Validity Not After | Certificate end date |
| Subject | Certificate subject information; see Sections [7.1.4.2](#7142-subject-information-subscriber-certificates) and [7.1.4.3](#7143-subject-information-root-certificates-and-subordinate-ca-certificates) |
| Public Key | Public Key corresponding to the certificate |
| Extensions | See [Section 7.1.2](#712-certificate-content-and-extensions) |

Fields not listed in the table above are not used by this Certification Center; the certificates it issues contain neither `issuerUniqueID` nor `subjectUniqueID`.

### 7.1.2 Certificate Content and Extensions

The Extensions used by this Certification Center comply with the [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) standard and the requirements of [BR Section 7.1.2](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#712-certificate-content-and-extensions).

#### 7.1.2.1 Root CA certificates

The Root CA (RCA) certificates of this Certification Center are self-signed. RCA certificates newly issued on or after the effective date of this Statement conform to the extension requirements in the table below; RCA certificates issued before these profile requirements took effect and still within their validity period retain their original content.

| Certificate Extension | Criticality | Description |
|-----------------------|-------------|-------------|
| basicConstraints | Critical | The `cA` field is set to true; `pathLenConstraint` is not set. |
| keyUsage | Critical | The `keyCertSign` and `cRLSign` bits are set; the RCA Private Key of this Certification Center is not used to sign OCSP responses, so `digitalSignature` is not set. |
| subjectKeyIdentifier | Non-critical | Its value is the `keyIdentifier` carried in the authorityKeyIdentifier extension of the certificates issued by that RCA. |
| authorityKeyIdentifier | Non-critical | Contains only the `keyIdentifier` field, whose value is identical to the subjectKeyIdentifier of the same certificate; it contains neither `authorityCertIssuer` nor `authorityCertSerialNumber`. |

Extensions other than those listed above are not used by this Certification Center.

#### 7.1.2.2 Subordinate CA Certificates

For Subordinate CA certificates issued by this Certification Center, their extension fields must comply with the table below:

| Certificate Extension | Criticality | Description |
|-----------------------|-------------|-------------|
| certificatePolicies | Non-critical | Includes policyIdentifiers in accordance with [Section 7.1.6.3](#7163-subordinate-ca-certificates). The policyInformation for the Company's certificate policy object identifier may contain a CPS policy qualifier (id-qt-cps) whose value is an HTTP or HTTPS URL. |
| cRLDistributionPoints | Non-critical | Its value is the HTTP URL of this Certification Center's CRL service. |
| authorityInformationAccess | Non-critical | Contains the HTTP URL of the Issuing CA certificate (accessMethod = id-ad-caIssuers), and may contain the HTTP URL of the Issuing CA OCSP responder (accessMethod = id-ad-ocsp). |
| basicConstraints | Critical | The cA field is set to true and pathLenConstraint is set to 0. For Cross Certificates, pathLenConstraint is not set. |
| keyUsage | Critical | Bit positions for keyCertSign and cRLSign SHALL be set. If the Subordinate CA Private Key is used for signing OCSP responses, then the digitalSignature bit SHALL be set. |
| extKeyUsage | Non-critical | Does not assert `anyExtendedKeyUsage` (OID: 2.5.29.37.0), nor `id-kp-codeSigning`, `id-kp-emailProtection`, `id-kp-timeStamping`, or `id-kp-OCSPSigning`. The EKU combination depends on when the certificate is disclosed to the CCADB: for certificates disclosed before June 15, 2026, the EKU asserts only `id-kp-serverAuth` (OID: 1.3.6.1.5.5.7.3.1), or only `id-kp-serverAuth` and `id-kp-clientAuth` (OID: 1.3.6.1.5.5.7.3.2); for certificates disclosed on or after June 15, 2026, the EKU asserts only `id-kp-serverAuth`. |
| authorityKeyIdentifier | Non-critical | Contains only the keyIdentifier field, and does not contain the authorityCertIssuer or authorityCertSerialNumber fields. |
| subjectKeyIdentifier | Non-critical | Its value is the keyIdentifier carried in the authorityKeyIdentifier (AKI) extension of the certificates issued by that Subordinate CA. |

Extensions other than those listed above are not used by this Certification Center.

The following two Cross Certificates listed in Section 7.1.4.3.2 were issued before BR version 2.0.0 took effect on September 15, 2023 (the certificate issued by TWCA Root Certification Authority to TWCA Global Root CA on October 28, 2014, and the certificate issued by TWCA Global Root CA to TWCA CYBER Root CA on December 9, 2022) and retain their original content: their basicConstraints extension sets cA to true and does not set pathLenConstraint; they contain no extKeyUsage extension; their certificatePolicies extension contains only anyPolicy with an id-qt-cps qualifier; and their authorityInformationAccess extension contains only the id-ad-ocsp access method. Cross Certificates issued on or after September 15, 2023, including the Cross Certificate issued by TWCA Global Root CA to TWCA CYBER Root CA G3, the Cross Certificate issued by TWCA CYBER Root CA to TWCA CYBER Root CA G3, and the Cross Certificate issued by TWCA Global Root CA to TWCA CYBER Root CA on October 31, 2026, conform to this section.

The Subordinate CA certificate "TWCA Global EVSSL Certification Authority" listed in Section 7.1.4.3.1 was issued by TWCA Global Root CA on August 23, 2012 and retains its original content: it contains no extKeyUsage extension; its certificatePolicies extension contains only anyPolicy with an id-qt-cps qualifier; and its authorityInformationAccess extension contains only the id-ad-ocsp access method.

#### 7.1.2.3 Subscriber Certificates

The Extension settings for Subscriber Certificates issued by the Subordinate CA are as follows. The table below lists only the extensions actually used by this Certification Center; extensions not listed are not used:

| Certificate Extension | Criticality | Description |
|-----------------------|-------------|-------------|
| authorityKeyIdentifier | Non-critical | Uses the SHA-1 algorithm. |
| subjectKeyIdentifier | Non-critical | Uses the SHA-1 or SHA-256 algorithm. |
| cRLDistributionPoints | Non-critical | Contains the CRL download location. |
| subjectAltName | Non-critical | Contains at least one subject information entry (see [Section 7.1.4.2.1](#71421-subject-alternative-name-san)). |
| authorityInformationAccess | Non-critical | Contains CA Issuers (accessMethod=1.3.6.1.5.5.7.48.2) (required), Online Certificate Status Protocol (accessMethod=1.3.6.1.5.5.7.48.1) (optional). |
| certificatePolicies | Non-critical | Contains certificatePolicies:policyIdentifier, certificatePolicies:policyQualifiers:policyQualifierId, certificatePolicies:policyQualifiers:qualifier:cPSuri. |
| basicConstraints | Critical | cA=false; pathLenConstraint is not set. |
| keyUsage | Critical | Set according to the algorithm of the key submitted by the Subscriber:<br>1. RSA keys: digitalSignature (required), keyEncipherment (optional).<br>2. ECC keys: only digitalSignature is set; keyEncipherment and keyAgreement are not used. |
| extKeyUsage | Non-critical | serverAuth (1.3.6.1.5.5.7.3.1) (required). Certificates issued before March 1, 2027 may also include clientAuth (1.3.6.1.5.5.7.3.2) (optional); certificates issued on or after March 1, 2027 include only serverAuth (see [Section 1.4.1](#141-appropriate-certificate-uses)). |
| signedCertificateTimestampList | Non-critical | Signed Certificate Timestamps, in the number specified in [Section 4.3.1](#431-ca-actions-during-certificate-issuance). |

#### 7.1.2.4 All Certificates

All other Extensions must comply with the [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) standard and the requirements of [BR Section 7.1.2.11](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#71211-common-certificate-fields).

#### 7.1.2.5 Application of RFC 5280

A Precertificate is not considered a certificate only for the serial number uniqueness requirement of [RFC 5280 Section 4.1.2.2](https://datatracker.ietf.org/doc/html/rfc5280#section-4.1.2.2), and therefore carries the same serial number as the corresponding Subscriber Certificate.

### 7.1.3 Algorithm object identifiers

#### 7.1.3.1 SubjectPublicKeyInfo

The key identifiers used by this Certification Center when issuing certificates are as follows:

| Key Algorithm | Object Identifier (OID) |
|---------------|------------------------|
| rsaEncryption | {iso(1) member-body(2) us(840) rsadsi(113549) pkcs(1) pkcs-1(1) rsaEncryption(1)} (1.2.840.113549.1.1.1) |
| ecPublicKey | {iso(1) member-body(2) us(840) ansi-X9-62(10045) keyType(2) ecPublicKey(1)} (1.2.840.10045.2.1) |

#### 7.1.3.2 Signature AlgorithmIdentifier

The signature algorithm object identifiers used by this Certification Center when issuing certificates are as follows:

| Signature Algorithm | Object Identifier (OID) |
|---------------------|------------------------|
| sha256WithRSAEncryption | {iso(1) member-body(2) us(840) rsadsi(113549) pkcs(1) pkcs-1(1) sha256WithRSAEncryption(11)} (1.2.840.113549.1.1.11) |
| sha384WithRSAEncryption | {iso(1) member-body(2) us(840) rsadsi(113549) pkcs(1) pkcs-1(1) sha384WithRSAEncryption(12)} (1.2.840.113549.1.1.12) |

All Certification Authority keys of this Certification Center are RSA keys; this Certification Center therefore signs certificates, CRLs, and OCSP responses only with the RSA signature algorithms listed above. Subscribers may request certificates for RSA or ECDSA keys; the public key algorithms are listed in [Section 7.1.3.1](#7131-subjectpublickeyinfo).

### 7.1.4 Name Forms

#### 7.1.4.1 Name Encoding

The certificate Subject Distinguished Name and Issuer Distinguished Name of this Certification Center and Subscribers comply with the X.500 Distinguished Name (DN) naming convention. The attribute types of these names comply with the relevant provisions of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280).

For all certificates issued by this Certification Center, the Issuer Distinguished Name (Issuer DN) MUST be byte-for-byte identical to the Subject Distinguished Name (Subject DN) of the Issuing CA's certificate. A self-signed Root CA certificate has no superior issuer certificate; its Issuer DN MUST be byte-for-byte identical to its own Subject DN. All CA certificates that have the same Subject DN according to the [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280) DN comparison algorithm MUST be encoded identically.

#### 7.1.4.2 Subject information: subscriber certificates

For Subscriber Certificates issued by this Certification Center, the verification procedures for subject information are conducted in accordance with the requirements of [Section 3.2.2](#322-authentication-of-organization-and-domain-identity) of this Statement, ensuring that all verification procedures are correct prior to issuance.

For Subscriber Certificates issued by this Certification Center, each attribute in the subject shall not use incomplete, inapplicable, or default values. Except for the CN attribute in the subject information, no other attributes may contain domain names or IP addresses.

##### 7.1.4.2.1 Subject Alternative Name (SAN)

Subscriber Certificates issued by this Certification Center must contain a Subject Alternative Name (SAN) Extension. Its value must be in dNSName or iPAddress form, and shall not use Internal Names or Reserved IP Addresses, and must contain at least one value matching the subject information CN. Per the requirements of [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280), the dNSName content shall not contain underscores ("_").

##### 7.1.4.2.2 Subject Distinguished Name Fields

The Distinguished Name (DN) attributes of Subscriber Certificates issued by this Certification Center are shown in the table below. It should also be noted that the SAN of certificates issued by this Certification Center must contain a value matching the subject information CN; the content of that value is described in [Section 7.1.4.2.1](#71421-subject-alternative-name-san).

| Subject Name Attribute | SSL Certificate | EV SSL Certificate |
|---|---|---|
| Common Name (CN) | ○ | ○ |
| Organization (O) | ○ | ○ |
| Street Address | X | △ |
| Locality (L) | ○ | ○ |
| State or Province (ST) | △ | ○ |
| Postal Code | X | △ |
| Country (C) | ○ | ○ |
| Business Category | X | ○ |
| Jurisdiction of Incorporation Country Name | X | ○ |
| Serial Number | X | ○ |

Note: ○ = used; △ = may be used; X = not used.

The Jurisdiction of Incorporation fields are populated in accordance with [EVG Section 7.1.4.2.4](https://cabforum.org/working-groups/server/extended-validation/guidelines/#71424-subject-jurisdiction-of-incorporation-or-registration-field), which prohibits the inclusion of information that is not relevant to the level of the Incorporating or Registration Agency: where that Agency operates at the country level, the country information must be included and state or province and locality information must not be included; where it operates at the state or province level, the country and state or province information must be included and locality information must not be included; where it operates at the locality level, the country, state or province (where the state or province regulates locality-level registrations) and locality information must be included.

This Certification Center issues EV SSL Certificates only to Private Organizations, and their Incorporating or Registration Agencies are all nationwide agencies of the Republic of China (Taiwan) operating at the country level. Accordingly, EV SSL Certificates include only the Jurisdiction of Incorporation Country Name, with the value "TW"; the Jurisdiction of Incorporation State or Province Name and the Jurisdiction of Incorporation Locality Name are not included. The acceptable values for these fields are disclosed in the list of organization registration agencies published by this Certification Center; see [Section 3.2.2.7](#3227-data-source-accuracy).

#### 7.1.4.3 Subject information: root certificates and subordinate CA certificates

The self-signed certificates issued by the Root Certification Authority (RCA) and the certificates of the Subordinate CA are issued in accordance with the certificate policy, ensuring that all subject information is correct prior to issuance.

##### 7.1.4.3.1 Subject Distinguished Name Fields

The organizationName in the subject of this Certification Center's CA certificates is "TAIWAN-CA", which is the Company's legal English name "TAIWAN-CA INC." with the company-type suffix "INC." omitted.

The Distinguished Names of the Subordinate CA certificates are:

**SSL Subordinate CA**

| Distinguished Name (DN) |
|-------------------------|
| C=TW, O=TAIWAN-CA, OU=Global SSL Sub-CA, CN=TWCA Global SSL Certification Authority |
| C=TW, O=TAIWAN-CA, OU=Secure SSL Sub-CA, CN=TWCA Secure SSL Certification Authority |
| C=TW, O=TAIWAN-CA, OU=SSL Sub-CA, CN=TWCA SSL Certification Authority |
| C=TW, O=TAIWAN-CA, CN=TWCA Secure SSL Certification Authority |
| C=TW, O=TAIWAN-CA, CN=TWCA SSL Certification Authority |

**EV SSL Subordinate CA**

| Distinguished Name (DN) |
|-------------------------|
| C=TW, O=TAIWAN-CA, OU=Global EVSSL Sub-CA, CN=TWCA Global EVSSL Certification Authority |
| C=TW, O=TAIWAN-CA, OU=EVSSL Sub-CA, CN=TWCA EVSSL Certification Authority |
| C=TW, O=TAIWAN-CA, CN=TWCA EVSSL Certification Authority |

The Distinguished Names of the Root Certification Authority (RCA) certificates are:

| Distinguished Name (DN) |
|-------------------------|
| C=TW, O=TAIWAN-CA, OU=Root CA, CN=TWCA Root Certification Authority |
| C=TW, O=TAIWAN-CA, OU=Root CA, CN=TWCA Global Root CA |
| C=TW, O=TAIWAN-CA, OU=Root CA, CN=TWCA CYBER Root CA |
| C=TW, O=TAIWAN-CA, CN=TWCA CYBER Root CA G3 |

##### 7.1.4.3.2 Certificate hierarchy mapping

The trust paths and scope of applicability of the certificate hierarchy governed by this Statement are as follows:

**Current issuance hierarchy**

| Tier | Certificate Common Name (CN) | Description |
|---|---|---|
| Root Certification Authority (RCA) | TWCA CYBER Root CA | Self-signed certificate; the trust anchor dedicated to the TLS Trust Purposes governed by this Statement. |
| Root Certification Authority (RCA) | TWCA CYBER Root CA G3 | Self-signed certificate; the trust anchor dedicated to the TLS Trust Purposes governed by this Statement. |
| Subordinate CA | TWCA SSL Certification Authority | Issues SSL Certificates (OV level). |
| Subordinate CA | TWCA EVSSL Certification Authority | Issues EV SSL Certificates. |
| Subscriber Certificate (EE) | — | Profiles are set out in [Section 7.1.2.3](#7123-subscriber-certificates) and [Section 7.1.4.2](#7142-subject-information-subscriber-certificates). |

**Cross Certificates**

To extend the compatibility of the trust path, this Certification Center also issues the following Cross Certificates:

| Subject of the Cross Certificate | Issuer of the Cross Certificate | Date of Issuance |
|---|---|---|
| TWCA CYBER Root CA | TWCA Global Root CA | December 9, 2022 |
| TWCA CYBER Root CA | TWCA Global Root CA | October 31, 2026 |
| TWCA CYBER Root CA G3 | TWCA Global Root CA | October 30, 2026 |
| TWCA CYBER Root CA G3 | TWCA CYBER Root CA | October 31, 2026 |
| TWCA Global Root CA | TWCA Root Certification Authority | October 28, 2014 |

**Scope of applicability**

All operational practices, validation procedures, and certificate and CRL profiles set out in this Statement apply to each Root CA certificate and each Subordinate CA certificate listed in [Section 7.1.4.3.1](#71431-subject-distinguished-name-fields) (including the Cross Certificates listed above), and to all Subscriber Certificates issued by them. Every certificate containing the `id-kp-serverAuth` Extended Key Usage is issued and managed in accordance with this Statement. This Statement does not cover any CA certificate outside the foregoing lists.

The remaining Subordinate CA certificates listed in [Section 7.1.4.3.1](#71431-subject-distinguished-name-fields) were issued by the Root CA certificates identified in this Section; those that have not expired continue to be subject to this Statement for certificate revocation, CRL, and OCSP services.

##### 7.1.4.3.3 Transition of multi-Trust-Purpose Root CA certificates to single-purpose operation

"TWCA CYBER Root CA" and "TWCA CYBER Root CA G3", the trust anchors governed by this Statement, are dedicated to a single Trust Purpose and issue only the TLS Subordinate CA certificates covered by this Statement (including the Cross Certificate issued by "TWCA CYBER Root CA" to "TWCA CYBER Root CA G3" listed in Section 7.1.4.3.2) and the OCSP Delegated Responder certificates of each such Root CA.

"TWCA Global Root CA" is the issuer of the Cross Certificates for "TWCA CYBER Root CA" and "TWCA CYBER Root CA G3", and "TWCA Root Certification Authority" is the issuer of the Cross Certificate for "TWCA Global Root CA". In addition to the TLS Trust Purposes covered by this Statement, those two Root CA certificates are the starting point of the trust path for other hierarchies operated by the Company, whose operational practices are set out in the Certificate Policy and Certification Practice Statement that the Company publishes separately for each such Trust Purpose.

This Certification Center transitions those two Root CA certificates to single-purpose operation as follows:

1. Newly issued TLS Subordinate CA certificates are issued exclusively from "TWCA CYBER Root CA" or "TWCA CYBER Root CA G3". Effective June 15, 2026, the trust path for TLS certificates uses "TWCA CYBER Root CA" as the trust anchor; "TWCA Global Root CA" and "TWCA Root Certification Authority" no longer issue certificates for TLS purposes, except that "TWCA Global Root CA" issues the Cross Certificate for "TWCA CYBER Root CA G3" listed in Section 7.1.4.3.2, as required for root CA succession by Section 1.3.1.1 of the Chrome Root Program Policy, and on October 31, 2026 re-issued the Cross Certificate for "TWCA CYBER Root CA" listed in that Section. Those Cross Certificates conform to Section 7.1.2.2 and assert only the `id-kp-serverAuth` Extended Key Usage.
2. Trust paths are progressively migrated to the dedicated hierarchies referred to in item 1, and, by December 31, 2028, one of the trust bits of "TWCA Root Certification Authority" and "TWCA Global Root CA" is removed, or those root certificates are sunset; the related requests are submitted to the CCADB early enough for this to be completed by that date.
3. Progress of the transition is disclosed in Bugzilla, and this Statement is revised in accordance with [Section 9.12](#912-amendments).

### 7.1.5 Name constraints

The certificates of this Certification Center and the certificates it issues do not use the "Name Constraints" extension.

### 7.1.6 Certificate policy object identifier

For certificates issued by this Certification Center, the "Certificate Policies" extension within the certificate uses the Certificate Policy Object Identifier defined by the certificate policy.

#### 7.1.6.1 Reserved Certificate Policy Identifiers

The following are Certificate Policy Object Identifiers reserved by CABF BR:

| Object Identifier | Usage |
|-------------------|-------|
| {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) baseline-requirements(2) domain-validated(1)} (2.23.140.1.2.1) | Not used (this Certification Center does not issue DV certificates) |
| {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) baseline-requirements(2) organization-validated(2)} (2.23.140.1.2.2) | Used for SSL CA certificates and SSL Certificates |
| {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) baseline-requirements(2) individual-validated(3)} (2.23.140.1.2.3) | Not used (this Certification Center does not issue IV certificates) |
| {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) ev-guidelines(1)} (2.23.140.1.1) | Used for EV SSL CA certificates and EV SSL Certificates |

#### 7.1.6.2 Root Certification Authority Certificates

The certificates of the Root Certification Authority (RCA) do not contain the Certificate Policies extension.

#### 7.1.6.3 Subordinate CA Certificates

Subordinate CA certificates contain the Certificate Policies extension. Except for Cross Certificates and the certificates described in [Section 7.1.2.2](#7122-subordinate-ca-certificates) as retaining their original content, they use the following Certificate Policy Object Identifiers:

| Certificate Type | Object Identifier |
|-----------------|-------------------|
| SSL CA Certificate | {ISO(1) identified-organization(3) dod(6) internet(1) private(4) enterprise(1) TWCA(40869) certificates(1) policies(1) SSL(21)} (1.3.6.1.4.1.40869.1.1.21); {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) baseline-requirements(2) organization-validated(2)} (2.23.140.1.2.2) |
| EV SSL CA Certificate | {ISO(1) identified-organization(3) dod(6) internet(1) private(4) enterprise(1) TWCA(40869) certificates(1) policies(1) EV(22) class3(3)} (1.3.6.1.4.1.40869.1.1.22.3); {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) ev-guidelines(1)} (2.23.140.1.1) |

Cross Certificates issued on or after September 15, 2023 contain policy identifiers in accordance with [BR Section 7.1.2.2.6](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#71226-cross-certified-subordinate-ca-certificate-certificate-policies). The Cross Certificates issued before that date are described in [Section 7.1.2.2](#7122-subordinate-ca-certificates).

#### 7.1.6.4 Subscriber Certificates

Subscriber Certificates issued by the Subordinate CA contain the Certificate Policies extension and use the following Certificate Policy Object Identifiers:

| Certificate Type | Object Identifier |
|-----------------|-------------------|
| SSL Certificate | {ISO(1) identified-organization(3) dod(6) internet(1) private(4) enterprise(1) TWCA(40869) certificates(1) policies(1) SSL(21)} (1.3.6.1.4.1.40869.1.1.21); {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) baseline-requirements(2) organization-validated(2)} (2.23.140.1.2.2) |
| EV SSL Certificate | {ISO(1) identified-organization(3) dod(6) internet(1) private(4) enterprise(1) TWCA(40869) certificates(1) policies(1) EV(22) class3(3)} (1.3.6.1.4.1.40869.1.1.22.3); {joint-iso-itu-t(2) international-organizations(23) ca-browser-forum(140) certificate-policies(1) ev-guidelines(1)} (2.23.140.1.1) |

### 7.1.7 Usage of Policy Constraints extension

Certificates issued by this Certification Center do not use the "Policy Constraints" (policyConstraints) extension.

### 7.1.8 Policy qualifiers syntax and semantics

The Subscriber Certificates issued by this Certification Center contain, in the policyInformation for the Company's certificate policy object identifier, a CPS policy qualifier (id-qt-cps); Subordinate CA certificates may contain this policy qualifier. For the certificates described in [Section 7.1.2.2](#7122-subordinate-ca-certificates) as retaining their original content, the CPS policy qualifier is included in the policyInformation for anyPolicy. No other policy qualifiers are included in these certificates.

### 7.1.9 Processing semantics for the critical Certificate Policies extension

No stipulation.

## 7.2 CRL profile

The service URL can be obtained from the CRL Distribution Points (cRLDistributionPoints) extension of Subscriber Certificates. The frequency at which this Certification Center issues CRLs is specified in [Section 4.9.7](#497-crl-issuance-frequency).

For each Certification Authority, this Certification Center issues a single CRL whose scope covers all certificates issued by that Certification Authority, signed with that Certification Authority's Private Key; this Certification Center does not issue partitioned CRLs. None of these CRLs contains an Issuing Distribution Point extension. Before a Certification Authority issues its first certificate, this Certification Center publishes that Certification Authority's first CRL and makes its OCSP service operational.

### 7.2.1 Version number(s)

This Certification Center issues CRLs in X.509 v2 format, compliant with [RFC 5280](https://datatracker.ietf.org/doc/html/rfc5280), with the following fields:

| Field | Description |
|-------|-------------|
| Version Number | Fixed as v2 |
| Issuer | Subject DN of the Issuing CA. Its encoding is byte-for-byte identical to the encoding of the `subject` field of the CA certificate that issued this CRL |
| This Update | CRL issuance time (`thisUpdate`) |
| Next Update | The date by which the next CRL will be issued (`nextUpdate`). For CRLs covering Subscriber Certificates, no more than 10 days after `thisUpdate`; for CRLs covering Subordinate CA certificates, no more than 12 months after `thisUpdate`. The values currently configured for those schedules are 4 days and 1 day respectively. This Certification Center may adjust these configured values as operationally required, provided that the adjusted values remain within the limits stated above |
| Signature Algorithm | The signature algorithm used for issuing the CRL. This Certification Center supports: sha256WithRSAEncryption, sha384WithRSAEncryption. Its encoded value is byte-for-byte identical to `tbsCertList.signature` |
| Revoked Certificates List | List of revoked certificates, including certificate serial number and revocation time; for CRL entry extensions, see [Section 7.2.2](#722-crl-and-crl-entry-extensions) |
| Extensions | CRL extensions; see [Section 7.2.2](#722-crl-and-crl-entry-extensions) |
| Signature Value | Signature value generated by the issuer's signing |

Fields not listed in the table above are not used by this Certification Center.

### 7.2.2 CRL and CRL entry extensions

The CRLs issued by this Certification Center contain the following Extensions; of these, Reason Code is an extension of the individual CRL entry (CRL entry extension):

| Extension | Criticality | Description |
|-----------|--------|-------------|
| CRL Number | Non-critical | The CRL Number (crlNumber) extension. This extension MUST contain an INTEGER greater than or equal to zero (0) and less than 2^159, conveying a strictly increasing sequence. |
| Authority Key Identifier | Non-critical | Identifies the Issuing CA |
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
| Superseded (4) | The Subscriber requests certificate revocation for this reason. The CA revokes the certificate due to domain validation or compliance issues, and the issue is unrelated to Key Compromise or privilege withdrawal. |
| Cessation of Operation (5) | The Applicant no longer owns or is no longer authorized to use all domain names in the certificate. The website using the certificate is no longer in operation. The CA is made aware that the domain name or IP in the certificate can no longer be legally used, such as by court order. |
| Privilege Withdrawn (9) | The CA obtains evidence that the certificate has been misused. The CA is made aware that the Subscriber has violated the Subscriber agreement or Terms of Use. The CA is made aware that a Wildcard Certificate has been used for a misleading or fraudulent subdomain. The CA is made aware that information in the certificate has changed. The CA determines or is made aware that information in the certificate is incorrect. The CA is made aware that the certificate application was not authorized. |

This Certification Center's certificate revocation request page informs Subscribers of the revocation reason options available to them and explains when to choose each option: no reason specified (the default; no reasonCode extension is provided in the CRL), keyCompromise (1), affiliationChanged (3), superseded (4), and cessationOfOperation (5). The revocation tools that this Certification Center provides to Subscribers (including the self-service issuance platform and ACME) use "no reason specified" as the default; privilegeWithdrawn (9) is used as determined by this Certification Center and is not offered to Subscribers as an option (per [BR Section 7.2.2](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#722-crl-and-crl-entry-extensions)).

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
| Signer Certificate | The certificate of the OCSP responder that signed this response, carried in the `certs` field of the response so that Relying Parties can verify the signature. It is issued by the CA that issued the certificate being queried and its Extended Key Usage contains only `id-kp-OCSPSigning`; it is therefore a Delegated Responder certificate (OCSP Responder certificate, see BR Section 7.1.2.8). See [Section 7.3](#73-ocsp-profile) |

### 7.3.2 OCSP extensions

The Extensions used in the Online Certificate Status Protocol (OCSP) of this Certification Center comply with the [RFC 6960](https://datatracker.ietf.org/doc/html/rfc6960) specification; the singleExtensions of an OCSP response do not contain the reasonCode (OID: 2.5.29.21) extension.

# 8 COMPLIANCE AUDIT AND OTHER ASSESSMENTS

## 8.1 Frequency or circumstances of assessment

This Certification Center conducts external audits at least once per year and internal audits at least once per quarter. This Certification Center MUST upload the annual external audit reports to CCADB within 3 months of the end of the audit period.

Any key lifecycle events (including key generation, backup, storage, recovery, transport, and destruction) for Root CAs and Subordinate CAs MUST be covered by annual external audits. If a key lifecycle event is not included in the annual audit, this Certification Center MUST report the event with an audit/witness report to major Root Store Programs (Application Software Suppliers, or CCADB) within 90 days of the event.

## 8.2 Identity/qualifications of assessor

The audit personnel conducting internal and external audits for this Certification Center must possess at least knowledge of certification authority and information system security auditing, have more than 2 years of audit-related experience or certificate operations experience, and must be familiar with the operational specifications of this Statement, as well as have knowledge and experience in application systems and computer hardware/software systems. If the competent authority has relevant regulations regarding the qualification of audit personnel, those regulations shall prevail.

When conducting external audits, the commissioned audit firm must comply with the requirements of [BR Section 8.2](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#82-identityqualifications-of-assessor) and [CCADB Policy Section 5.3](https://www.ccadb.org/policy#53-audit-firm-and-audit-team-qualifications) and possess nationally recognized formal audit qualifications or internationally recognized audit credentials to provide fair and objective audit services. When conducting audits, this Certification Center will first verify the qualifications of the audit personnel, and after the audit is completed, the audit report will also list the audit credentials and certifications held by the audit personnel.

## 8.3 Assessor's relationship to assessed entity

The internal audit personnel conducting audits for this Certification Center have independent and separate responsibilities from the audited units, with no conflicts of interest that could affect the objectivity of the audit, and they perform assessments with an independent, fair, and objective attitude.

External audits of this Certification Center are conducted by commissioned audit firms to audit the operations of this Certification Center.

## 8.4 Topics covered by assessment

The audit covers the following items:

- Whether a Certification Practice Statement and related operational specifications have been established and published, including operational specifications established in accordance with the Certification Practice Statement.
- Whether certificate management and related operations are performed in accordance with the Certification Practice Statement and related operational specifications, to meet the integrity requirements of certificate services and the security controls of this Certification Center's environment.
- Whether this Statement complies with the requirements of the BR, the EVG, and the Root Store Programs.

This Certification Center's audit standards comply with the following:

- WebTrust Principles and Criteria for Certification Authorities -- Version 2.2.2 or later.
- WebTrust Principles and Criteria for Certification Authorities -- Extended Validation TLS -- Version 2.0.1 or later.
- WebTrust Principles and Criteria for Certification Authorities -- TLS Baseline -- Version 2.10 or later.
- WebTrust Principles and Criteria for Certification Authorities -- Network Security -- Version 2.0.5 or later.

## 8.5 Actions taken as a result of deficiency

Upon completion of a full audit and assessment of this Certification Center's operations, if any non-compliance with the Certification Practice Statement is identified, the auditor shall list each deficiency according to its severity and notify this Certification Center. Upon receipt of the details, this Certification Center will handle them in accordance with its incident response procedures.

Every audit finding (including any qualification, qualified opinion, other matter, or non-conformity identified during an audit), and any other non-compliance that violates this CP/CPS, relevant baseline requirements (such as TLS BR), or Root Store Policies, is treated as an "Incident". This Certification Center commits to reporting and managing it in accordance with the CCADB Incident Reporting Guidelines and timelines: disclosing a Preliminary or Full Incident Report in CCADB (including Bugzilla) within 72 hours of becoming aware, posting a Full Incident Report within 14 days of the initial disclosure, and thereafter updating the report on or before the "Next update" date recorded in the bug’s "Whiteboard" field, or where no such date is recorded at least every 7 days, and within 3 days of an Action Item being changed, completed, or delayed, until the deficiency is fully corrected and the incident is closed. This Certification Center must propose corrective and preventive measures for the deficiencies and track subsequent improvement progress.

## 8.6 Communication of results

This Certification Center will publish historical WebTrust audit reports in the Repository. This Certification Center also displays international certification marks on the Company's official website, and clicking on the mark icon allows viewing of the WebTrust audit report.

## 8.7 Self-Audits

This Certification Center monitors its own adherence to this Statement, the BR, and the EVG and controls its service quality by performing self-audits on at least a quarterly basis. SSL Certificates and EV SSL Certificates are sampled separately; in accordance with [BR Section 8.7](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#87-self-audits) and [EVG Section 8.1.1](https://cabforum.org/working-groups/server/extended-validation/guidelines/#811-self-audits), each randomly selected sample includes at least the greater of one (1) certificate or three percent (3%) of the certificates of that type issued during the period commencing immediately after the previous self-audit sample was taken.

This Certification Center uses a Linting process to verify the technical accuracy of the certificates within the selected sample set, independently of any previous linting performed on the same certificates.

## 8.8 Review of Delegated Parties

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
- If operational personnel of this Certification Center intentionally or negligently fail to follow this Statement and related operational specifications in performing registration, certificate issuance and revocation operations, or violate relevant legal regulations resulting in damage to Subscribers, this Certification Center shall compensate the Subscriber for damages in accordance with regulations, with the maximum compensation limited as specified in [Section 9.8](#98-limitations-of-liability) on limitation of liability.
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

This Statement, certificates issued by this Certification Center, CRLs issued by this Certification Center, and external audit results are all publicly available information.

### 9.3.3 Responsibility to protect confidential information

Unless one of the following conditions is met, the Subscriber's basic registration data and identity verification-related data shall never be disclosed to management authorities or any other person:

- As required by laws and regulations and authorized by the management authority through legal procedures.
- When a court or arbitration institution with lawful jurisdiction processes disputes or arbitration arising from certificates and requests through legal procedures.
- As otherwise provided in this Statement (e.g., the transfer of operations under [Section 5.8](#58-ca-or-ra-termination)).
- When provided to a Qualified Auditor for audit purposes.

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
- This Certification Center represents and warrants to the Certificate Beneficiaries that, during the period when the Certificate is valid, it has complied with the relevant Baseline Requirements and this Certificate Policy and/or Certification Practice Statement in issuing and managing the Certificate.
- The Root CA (RCA) SHALL be responsible for the performance and warranties of the Subordinate CA, for the Subordinate CA's compliance with this Statement, and for all liabilities and indemnification obligations of the Subordinate CA under this Statement, as if the Root CA were the Subordinate CA issuing the Certificates.
- This Certification Center must fulfill its responsibility to properly safeguard Subscriber registration data, certificate data, and related certificate operation information, and to prevent Confidential Information from being leaked, misused, tampered with, or used without authorization.
- This Certification Center shall accept Subscriber Certificate applications, certificate re-keys, and certificate revocation requests in accordance with this Statement, verify the correctness and completeness of relevant information sent by Subscribers to this Certification Center, perform certificate issuance and certificate revocation operations, and deliver relevant response messages to Subscribers.
- When issuing Subscriber Certificates, this Certification Center must verify the correctness and legality of application documents and Subscriber identity.
- When there are security concerns regarding the Private Key of the Subordinate CA, the Subordinate CA must notify Subscribers and the Root Certification Authority (RCA). When there are security concerns regarding the Private Key of the RCA, the RCA must notify all Subordinate CAs.
- When issuing certificates, this Certification Center shall securely deliver the issued certificates to the Repository in accordance with this Statement.
- When revoking Subscriber Certificates, this Certification Center shall generate CRLs in accordance with this Statement and securely deliver them to the Repository.
- This Certification Center shall provide certificate application procedures and a Subscriber agreement prior to the Subscriber's certificate application, detailing the operational specifications for certificate application, re-key, revocation, and usage, as well as the relevant rights and obligations.
- The Private Keys used by this Certification Center for issuing certificates and CRLs must be used independently and shall not be shared with other functions. If there are other requirements for message signing and encryption, different Private Keys must be used.
- The Certificate Warranties specifically include, but are not limited to, the following. For items 1 to 4, this Certification Center warrants that, at the time of issuance, it implemented the relevant verification procedure, followed that procedure when issuing the Certificate, and accurately described that procedure in this Statement:
  1. Right to Use Domain Name or IP Address: verifying that the Applicant either had the right to use, or had control of, the Domain Name(s) and IP address(es) listed in the Certificate's `subject` field and `subjectAltName` extension (or, only in the case of Domain Names, was delegated such right or control by someone who had such right to use or control); see [Section 3.2.2.4](#3224-validation-of-domain-authorization-or-control) and [Section 3.2.2.5](#3225-authentication-for-an-ip-address).
  2. Authorization for Certificate: verifying that the Subject authorized the issuance of the Certificate and that the Applicant Representative is authorized to request the Certificate on behalf of the Subject; see [Section 3.2.5](#325-validation-of-authority).
  3. Accuracy of Information: verifying the accuracy of all of the information contained in the Certificate; see [Section 3.2.2](#322-authentication-of-organization-and-domain-identity).
  4. Identity of Applicant: where the Certificate contains Subject Identity Information, verifying the identity of the Applicant in accordance with [Section 3.2](#32-initial-identity-validation); see [Section 3.2.2](#322-authentication-of-organization-and-domain-identity).
  5. Subscriber Agreement: where this Certification Center and the Subscriber are not Affiliated, the Subscriber and this Certification Center are parties to a legally valid and enforceable Subscriber Agreement that satisfies the BR; where they are the same entity or are Affiliated, the Applicant Representative acknowledged the Terms of Use.
  6. Status: this Certification Center maintains a 24 x 7 publicly-accessible Repository with current information regarding the status (valid or revoked) of all unexpired Certificates.
  7. Revocation: this Certification Center will revoke the Certificate for any of the reasons specified in the BR.
- When issuing an EV SSL Certificate, this Certification Center and its Root CA represent and warrant to the Certificate Beneficiaries that, during the period when the EV SSL Certificate is valid, this Certification Center has followed the EVG and this Statement in issuing and managing the EV SSL Certificate and in verifying the accuracy of the information contained in it. The EV Certificate Warranties specifically include, but are not limited to, the following:
  1. Legal Existence: this Certification Center has confirmed with the Incorporating or Registration Agency in the Subject's Jurisdiction of Incorporation or Registration that, as of the date the EV SSL Certificate was issued, the Subject named in the EV SSL Certificate legally exists as a valid organization or entity in that jurisdiction.
  2. Identity: this Certification Center has confirmed that, as of the date the EV SSL Certificate was issued, the legal name of the Subject matches the name on the official government records of that Incorporating or Registration Agency.
  3. Right to Use Domain Name: this Certification Center has taken all steps reasonably necessary to verify that, as of the date the EV SSL Certificate was issued, the Subject has the right to use all the Domain Name(s) listed in the EV SSL Certificate.
  4. Authorization for EV Certificate: this Certification Center has taken all steps reasonably necessary to verify that the Subject has authorized the issuance of the EV SSL Certificate.
  5. Accuracy of Information: this Certification Center has taken all steps reasonably necessary to verify that all of the other information in the EV SSL Certificate is accurate, as of the date the EV SSL Certificate was issued.
  6. Subscriber Agreement: the Subject has entered into a legally valid and enforceable Subscriber Agreement with this Certification Center that satisfies the EVG or, if they are affiliated, the Applicant Representative has acknowledged and accepted the Terms of Use.
  7. Status: this Certification Center will follow the EVG and maintain a 24 x 7 online-accessible Repository with current information regarding the status of the EV SSL Certificate as valid or revoked.
  8. Revocation: this Certification Center will follow the EVG and revoke the EV SSL Certificate for any of the revocation reasons specified in the EVG.

### 9.6.2 RA representations and warranties

As specified in [Section 9.6.1](#961-ca-representations-and-warranties).

### 9.6.3 Subscriber representations and warranties

Subscribers of this Certification Center are Legal Entities or organizations. Before issuing a Certificate, this Certification Center obtains the Applicant's agreement to the Subscriber Agreement, for the express benefit of this Certification Center and the Certificate Beneficiaries. The Subscriber Agreement applies to the Certificate to be issued pursuant to the certificate request, and this Certification Center has implemented a process to ensure that each Subscriber Agreement is legally enforceable against the Applicant. The Subscriber Agreement imposes the following obligations and warranties on the Applicant:

1. Accuracy of Information: to provide accurate and complete information at all times to this Certification Center, both in the certificate request and as otherwise requested by this Certification Center in connection with the issuance of the Certificate.
2. Protection of Private Key: to take all reasonable measures to assure control of, keep confidential, and properly protect at all times the Private Key that corresponds to the Public Key included in the Certificate (and any associated activation data or device, such as a password or token).
3. Acceptance of Certificate: to review and verify the Certificate contents for accuracy, and to confirm that the Public Key and Private Key are a matching key pair.
4. Use of Certificate: to install the Certificate only on servers that are accessible at the `subjectAltName`(s) listed in the Certificate, and to use the Certificate solely in compliance with all applicable laws and solely in accordance with the Subscriber Agreement.
5. Reporting and Revocation: to immediately request revocation of the Certificate, and cease using it and its associated Private Key, if there is any actual or suspected misuse or compromise of the Private Key associated with the Public Key included in the Certificate; and to immediately request revocation of the Certificate, and cease using it, if any information in the Certificate is or becomes incorrect or inaccurate.
6. Termination of Use of Certificate: to immediately cease all use of the Private Key corresponding to the Public Key included in the Certificate upon revocation of that Certificate for reasons of Key Compromise.
7. Responsiveness: to respond to this Certification Center's instructions concerning Key Compromise or Certificate misuse within 24 hours.
8. Acknowledgment and Acceptance: to acknowledge and accept that this Certification Center is entitled to revoke the Certificate immediately if the Applicant violates the terms of the Subscriber Agreement or if revocation is required by this Statement, the BR, or the EVG.

The same obligations and warranties apply to Applicants for EV SSL Certificates. Where an EV SSL Certificate request does not contain all necessary information about the Applicant, this Certification Center additionally confirms that information with the Certificate Approver or Contract Signer, rather than the Certificate Requester, in accordance with [Section 4.2.1](#421-performing-identification-and-authentication-functions).

Subscribers shall also observe the following:

- When applying for a certificate from this Certification Center, the Subscriber must fully understand and agree to the rights and obligations in the application form and agreement, as well as the content of this Statement and related specifications.
- The Subscriber shall bear the risk and liability arising from the use of the certificate before the revocation status has been published.
- If this Certification Center is unable to operate normally due to unforeseen circumstances, the Subscriber shall promptly seek other means to complete legal acts with others, and shall not use the inability of this Certification Center to operate normally as a defense against others.
- Technical personnel or contracted entities installing Subscriber site certificates shall have the capability to replace certificates within 24 hours or 5 days to avoid site operation disruption due to certificate revocation.
- In accordance with [Section 4.9.1](#491-circumstances-for-revocation), when circumstances meeting the grounds for certificate revocation occur, this Certification Center completes the revocation, depending on the revocation reason classification, within 24 hours (e.g., Key Compromise) or 5 days (e.g., incorrect certificate content) of becoming aware of them. Subscribers shall not request an extension of the revocation deadline, and shall cooperate to complete certificate replacement within that deadline. This Certification Center will proactively revoke the certificate when the revocation deadline expires without further notice.

### 9.6.4 Relying party representations and warranties

- Relying Parties shall obtain the Subordinate CA and the Root Certification Authority (RCA) self-signed certificates in accordance with this Statement.
- Relying Parties shall use the Subordinate CA certificate and the RCA self-signed certificate to establish and verify the certificate chain, to determine whether to trust Subscriber Certificates.
- When verifying certificates, Relying Parties shall use the RCA self-signed certificate to verify whether the digital signature of the Subordinate CA certificate was signed by the RCA's Private Key, and verify through the CRL whether the certificate has been revoked.
- When verifying Subscriber Certificates, Relying Parties shall use the Subordinate CA certificate to verify whether the digital signature of the Subscriber Certificate was signed by the Subordinate CA's Private Key, and verify through the CRL or OCSP service whether the certificate has been revoked.
- When using CRLs issued by this Certification Center, the Relying Party shall first verify the digital signature and check the Next Update time recorded in the CRL. If the Next Update time has passed, the latest CRL should be obtained. When using the OCSP service, the digital signature of the OCSP response should first be verified.
- Relying Parties shall select a secure computing environment and trustworthy applications. If the Relying Party's rights are compromised due to factors inherent in the computing environment or applications, the Relying Party shall bear the responsibility.
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

For EV SSL Certificates, this Certification Center does not limit its liability to Subscribers or Relying Parties for legally recognized and provable claims to a monetary amount less than US$2,000 per Subscriber or Relying Party per EV SSL Certificate (per [EVG Section 9.8](https://cabforum.org/working-groups/server/extended-validation/guidelines/#98-limitations-of-liability)); otherwise, liability is as provided by applicable law and contract.

## 9.9 Indemnities

Notwithstanding the limitations it places on its liability to Subscribers and Relying Parties, this Certification Center understands and acknowledges that the Application Software Suppliers that have a Root Certificate distribution agreement in place with the Root CA do not assume any obligation or potential liability of this Certification Center under the [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/), or that otherwise might exist because of the issuance or maintenance of certificates or reliance thereon by Relying Parties or others.

Accordingly, this Certification Center shall defend, indemnify, and hold harmless each Application Software Supplier for any and all claims, damages, and losses suffered by such Application Software Supplier related to a certificate issued by this Certification Center, regardless of the cause of action or legal theory involved. This Certification Center is not a government entity and does not invoke the exception provided in the [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) for government entities.

The foregoing obligation does not apply where, and only to the extent that, the claim, damage, or loss was directly caused by such Application Software Supplier's software:

- displaying as not trustworthy a certificate that is still valid;
- displaying as trustworthy a certificate that has expired; or
- displaying as trustworthy a certificate that has been revoked, but only in cases where the revocation status was at the time available online from this Certification Center, and the application software either failed to check such status or ignored an indication of revoked status.

The limitations of liability, disclaimers, and exclusions set out in [Section 9.2.3](#923-insurance-or-warranty-coverage-for-end-entities), [Section 9.7](#97-disclaimers-of-warranties), [Section 9.8](#98-limitations-of-liability), and [Section 9.16.5](#9165-force-majeure) govern the liability of this Certification Center to Subscribers and Relying Parties, and do not limit, condition, or diminish the obligations set out in this Section.

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
- If the object identifier is changed, this Statement will be revised accordingly.
- If changes are required due to changes in legal regulations, updates to international standards (e.g., [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/)), or other factors, this Statement will also be revised accordingly.
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
- If the disputing parties are unable to agree on the mediator's negotiation and ruling within 60 days, both parties agree that the Taiwan Taipei District Court shall be the court of first instance jurisdiction.
- The allocation of costs incurred during dispute negotiation and litigation proceedings shall be handled in accordance with the negotiation or relevant legal regulations.
- If a cross-border or cross-regional dispute cannot be resolved by the above methods, it must be handled in accordance with the relevant cross-border or cross-regional dispute arbitration regulations.

## 9.14 Governing law

The content of this Statement and the execution and interpretation of the related business of this Certification Center shall comply with the relevant laws and regulations of the competent authority and the relevant laws of this country.

## 9.15 Compliance with applicable law

- This Statement and this Certification Center shall comply with the Electronic Signatures Act of this country, its enforcement rules, and other applicable laws and regulations.
- This Certification Center complies with the latest version of the [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) and the [EVG](https://cabforum.org/working-groups/server/extended-validation/guidelines/). If there is any inconsistency between this Statement and the BR or the EVG, the BR or the EVG shall prevail; where the BR or the EVG conflicts with domestic law, the matter is handled in accordance with [Section 9.16.3](#9163-severability).
- In addition to the BR and the EVG, this Certification Center is bound by the latest version of the [CCADB Policy](https://www.ccadb.org/policy), by its own policy documents as disclosed in the CCADB, and by the policy of each Root Store Program listed in [Section 1.1](#11-overview). Where a new version of the CCADB Policy is published without a future effective date, this Certification Center complies with it within 14 calendar days of its publication.
- Where those requirements apply at the same time, they rank as follows: first, domestic law; second, whichever requirement is the stricter on the matter concerned; and last, this Statement. This Statement may not be relied upon to do anything that a stricter requirement prohibits. Where domestic law conflicts with those requirements, the matter is handled in accordance with [Section 9.16.3](#9163-severability).
- Where this Certification Center is uncertain which requirement applies to a particular practice, it seeks clarification from the Root Store Program concerned before taking the action in question, by a case comment in the CCADB or by the contact address that Program has designated for CA Owners, and retains the enquiry and the reply received. Where the requirements of two or more Root Store Programs cannot both be met, this Certification Center resolves the matter with the Programs concerned before proceeding. Any resulting amendment to this Statement is handled in accordance with [Section 9.12](#912-amendments).

## 9.16 Miscellaneous provisions

### 9.16.1 Entire agreement

No stipulation.

### 9.16.2 Assignment

No stipulation.

### 9.16.3 Severability

If certain provisions of this Statement are inapplicable and must be revised, the remaining provisions shall remain effective and unaffected by the inapplicable provision, until a new version of this Statement is updated and published.

In the event of a conflict between the [BR](https://cabforum.org/working-groups/server/baseline-requirements/requirements/) or the [EVG](https://cabforum.org/working-groups/server/extended-validation/guidelines/) and a law, regulation or government order (hereinafter "Law") of any jurisdiction in which this Certification Center operates or issues certificates, this Certification Center may modify the conflicting requirement only to the minimum extent necessary to make the requirement valid and legal in that jurisdiction, and only for operations or certificate issuances that are subject to that Law. Before issuing any certificate under the modified requirement, this Certification Center shall:

1. immediately include in this section a detailed reference to the Law requiring the modification of the BR or the EVG and the specific modification implemented by this Certification Center; and
2. notify the CA/Browser Forum of the information newly added to this Statement under item 1 by sending a message to questions@cabforum.org and receive confirmation that it has been posted to the Public Mailing List and is indexed in the Public Mail Archives available at https://cabforum.org/pipermail/public/ (or such other email addresses and links as the CA/Browser Forum may designate).

Any such modification shall be discontinued if and when the Law no longer applies, or the BR or the EVG is modified to make it possible to comply with both the BR or the EVG and the Law simultaneously; the corresponding change in practice, amendment of this Statement, and notice to the CA/Browser Forum as described above shall be made within 90 days. Where domestic law conflicts with the policy of a Root Store Program listed in [Section 1.1](#11-overview), this Certification Center also notifies that Root Store Program. A conflict of requirements that does not involve domestic law is handled in accordance with [Section 9.15](#915-compliance-with-applicable-law).

Updates to this Statement shall be handled in accordance with [Section 9.12](#912-amendments).

### 9.16.4 Enforcement (attorneys' fees and waiver of rights)

No stipulation.

### 9.16.5 Force Majeure

This Certification Center shall not be liable for damages due to force majeure events (e.g., earthquakes) or other causes not attributable to this Certification Center (e.g., war).

## 9.17 Other provisions

No stipulation.

# Appendix I: Glossary

Terms not defined in this Statement have the meanings given in [BR Section 1.6.1](https://cabforum.org/working-groups/server/baseline-requirements/requirements/#161-definitions) and [EVG Section 1.6.1](https://cabforum.org/working-groups/server/extended-validation/guidelines/#161-definitions).

**Internet**
Many different computer networks interconnected through standard communication protocols, enabling the exchange of information with each other.

**(Electronic) Message**
Refers to text, sound, images, symbols, or other data produced in electronic, magnetic, or other forms that cannot be directly perceived by human senses, sufficient to represent the intended meaning, for the purpose of electronic processing.

**RSA Algorithm**
An asymmetric encryption algorithm proposed by Ron Rivest, Adi Shamir, and Leonard Adleman in 1977. Its security strength is based on the difficulty of factoring large numbers into prime factors.

**Elliptic Curve Cryptography (ECC)**
A public key encryption algorithm based on elliptic curve mathematics, proposed by Neal Koblitz and Victor Miller in 1985. Its security strength is based on the difficulty of solving the elliptic curve discrete logarithm problem.

**ECC P-256 Curve**
An elliptic curve standard defined by NIST in FIPS 186-3, which defines the elliptic curve parameters p, a, b, G, n, h, where the x and y coordinates of the base point G are each 256 bits in length.

**Electronic Signature**
Refers to data messages existing in electronic form, attached to electronic documents that can be used to identify and confirm the identity of the signer of electronic documents, and messages generated by the signer using digital, voice, fingerprint, or other biometric-optical technology characteristics. It is attached to electronic messages and has the same effect as a signature, which can be used to identify and confirm the identity of the signer of electronic documents and to verify the integrity of the signed message.

**Encrypt/Encipher**
Refers to using mathematical algorithms or other methods to scramble electronic documents to ensure the security of data transmission.

**Decrypt/Decipher**
Restoring messages that have been encrypted and rendered unrecognizable to a form that is recognizable and meaningful using relevant mathematical algorithms or other methods.

**Digital Signature**
A type of electronic signature that uses an asymmetric cryptosystem and a hash function to compress a digital message of a certain length and then encrypt it with the signer's Private Key. The corresponding Public Key can verify this encrypted digital message, forming data that can identify the signer's identity and the authenticity of the electronic document.

**Private Key**
Refers to a set of paired digital data used to create and verify digital signatures, held by the signer. In addition to being used for creating digital signatures, this digital data can also be used for decrypting electronic messages.

**Public Key**
In the digital signature of an asymmetric cryptosystem, refers to a set of paired digital data used to create and verify digital signatures that is publicly disclosed. It can be used to verify the correctness of message data signed by the signer. When performing message confidentiality functions, it can encrypt transmitted messages.

**Public Key Certificate or Certificate**
A digitally recorded entry issued by a certification authority using a computer as its medium, containing the Applicant's registered Distinguished Name, Public Key, the validity period of the Public Key, the certification authority's registered Distinguished Name and signature, and other relevant identification information, used to confirm the identity of the signer and prove that they possess a matching pair of Public Key and Private Key.

**Certification Authority (CA)**
An organization that provides digital signature creation and electronic authentication services. It is an entity that, from a fair and objective position, verifies the correctness of the certificate Applicant's identity information and the relevance and legality between the Public Key and Private Key to be verified, and issues Public Key certificates accordingly.

**Certification Practice Statement (CPS)**
The operational specifications and application procedures published by a certification authority to its service recipients regarding certificate issuance, revocation, and inquiry management, including the Public Key architecture and security mechanisms for certificate operations, operational specifications and procedures, security mechanisms implemented in the certification authority's hardware and software, authority management, and related specifications.

**Asymmetric Cryptosystem**
A mathematical algorithm using a computer as its medium that can generate and use a pair of mathematically related security keys. The Private Key is used to sign messages, and the corresponding Public Key is used to verify the signed messages. The Public Key can also be used to encrypt messages, and the corresponding Private Key is used to decrypt the encrypted messages.

**Hash Function**
A mathematical algorithm that can convert a long string of bit messages into a fixed-length bit message. The same message input processed through the hash function will always produce the same output, and it is impossible to deduce the input message from the output result.

**Automated Certificate Management Environment (ACME)**
A communication protocol used to automate certificate-related management operations (e.g., certificate applications) between a Certification Authority (CA) and its client web servers, allowing users to automatically deploy public key infrastructure at extremely low cost. The protocol primarily transmits formatted JSON messages over HTTPS. The relevant standard is defined in [RFC 8555](https://datatracker.ietf.org/doc/html/rfc8555).

**Certificate Signing Request (CSR)**
An encoded file that allows certificate applicants to transmit Public Keys and certificate-related information (e.g., domain names) to a certification authority for certificate issuance through a standardized method. The file can concretely prove that the Applicant is the owner of the Private Key.

**Issue a Certificate**
Refers to the certification authority, in accordance with the Certification Practice Statement, verifying the identity qualifications and related documents of the Public Key certificate Applicant, verifying the pairing relationship between the Public Key and Private Key, and then issuing a Public Key certificate or other certificates.

**Public Suffix List (PSL)**
A public resource created by Mozilla, located at https://publicsuffix.org/. The list consists of two parts: one is the TLD (Top Level Domain) list provided by ICANN, and the other is the PRIVATE list provided by individuals or organizations.

**Punycode**
A way of representing Unicode and ASCII with a limited character set. For example, the Chinese characters for "Taiwan" would be encoded as "xn--kpry57d". The purpose of Punycode is to enable multilingual domain names to be encoded as ASCII within the framework of internationalized domain name labels.

**Bugzilla**
A web-based bug tracking management application maintained by Mozilla. When a CA has a significant deficiency, it must be reported here. Located at https://bugzilla.mozilla.org/.

**Internal Name**
A string of characters (not an IP address) in a Common Name or Subject Alternative Name field of a Certificate that cannot be verified as globally unique within the public DNS at the time of certificate issuance because it does not end with a Top-Level Domain registered in IANA's Root Zone Database.

**Reserved IP Address**
In the Internet addressing structure, IP addresses reserved for special purposes by the IETF (Internet Engineering Task Force) and IANA (Internet Assigned Numbers Authority). They can be queried at the following URLs:
https://www.iana.org/assignments/iana-ipv4-special-registry/iana-ipv4-special-registry.xhtml
https://www.iana.org/assignments/iana-ipv6-special-registry/iana-ipv6-special-registry.xhtml

**Certificate Transparency (CT)**
Defined in [RFC 6962](https://datatracker.ietf.org/doc/html/rfc6962), the purpose is to monitor certificates issued by CAs. By having CAs upload certificates to public servers (Log servers), Certificate Transparency allows website users and domain owners to identify improperly or maliciously issued certificates, and also to monitor improper CA operational behavior.

**Precertificate**
Defined in [RFC 6962](https://datatracker.ietf.org/doc/html/rfc6962), a special type of certificate in CT, used for auditing and verifying CA issuance records. This certificate must be issued in advance before the actual certificate is issued to the Subscriber, and uploaded to the CT log server to obtain SCTs (Signed Certificate Timestamps). The actual certificate issued to the Subscriber will contain these SCTs to prove that it has been successfully uploaded to the CT log server.

**Certification Authority Authorization (CAA)**
A DNS resource record that allows website owners to specify which CAs are authorized to issue TLS certificates for their domain. By setting CAA records, website administrators can restrict certificate issuance authority, effectively preventing unauthorized CAs from accidentally or maliciously issuing certificates for their domain, thereby enhancing domain certificate security.

**Multi-Perspective Issuance Corroboration (MPIC)**
Multi-perspective issuance corroboration requires CAs, before issuing certificates, to cross-verify DNS records and domain validation results from multiple geographically distributed verification nodes to reduce the risk of erroneous validation caused by BGP hijacking, DNS poisoning, or regional network attacks. In the MPIC architecture, the verification process includes two types of perspectives:

- **Primary Network Perspective**: Executed by the CA's primary verification node, responsible for obtaining basic verification data such as DNS, CAA, or HTTP-01, serving as a baseline for subsequent comparison. The Primary Network Perspective is mainly used to confirm whether the Applicant has basic and normally observable verification configurations.
- **Remote Network Perspective**: Executed by nodes distributed in geographic regions different from the Primary Network Perspective, with different network paths. These nodes must be able to obtain verification information consistent with the Primary Network Perspective to confirm that the domain configuration is consistent globally, and to rule out routing or DNS spoofing that only occurs near the CA's Primary Network Perspective.

The CA may consider the validation valid and issue a certificate only when the number of remote Network Perspectives whose results are inconsistent with the Primary Network Perspective does not exceed the allowed number set out in [Section 3.2.2.9](#3229-multi-perspective-issuance-corroboration); otherwise the validation is deemed to have failed.

**Common CA Database (CCADB)**
A common CA database jointly maintained by major browser vendors such as Google, Apple, Microsoft, and Mozilla, used to centrally manage and track global CA audit reports, policy documents, and root certificate information. It is a key management platform for ensuring that certificates can be trusted by major systems.

**Qualified Government Information Source (QGIS)**
A regularly-updated, current and publicly available database maintained by a Government Entity, designed for the purpose of accurately providing the information for which it is consulted and generally recognized as a dependable source of such information, where the reporting of data is required by law and false or misleading reporting is punishable with criminal or civil penalties; where a third-party vendor provides the information, that vendor obtains it directly from the Government Entity.

**Qualified Government Tax Information Source (QTIS)**
A QGIS that specifically contains tax information relating to Private Organizations, Business Entities, or Individuals; by definition a QTIS also meets all of the requirements for a QGIS.

**Qualified Independent Information Source (QIIS)**
A regularly-updated and current, publicly available database designed for the purpose of accurately providing the information for which it is consulted, and generally recognized as a dependable source of such information. The process for checking its accuracy is set out in [Section 3.2.2.7](#3227-data-source-accuracy).

# Appendix II: Acronyms and Abbreviations

| Acronym | Full Name |
|---------|-----------|
| ACME | Automated Certificate Management Environment |
| BR | Baseline Requirements for the Issuance and Management of Publicly-Trusted TLS Server Certificates |
| CA | Certification Authority |
| CAA | Certification Authority Authorization |
| CABF | CA/Browser Forum |
| CC | Common Criteria |
| CCADB | Common CA Database |
| CN | Common Name |
| CP | Certificate Policy |
| CPS | Certification Practice Statement |
| CRL | Certificate Revocation List |
| CSR | Certificate Signing Request |
| DN | Distinguished Name |
| DNSSEC | Domain Name System Security Extensions |
| ECC | Elliptic Curve Cryptography |
| EKU | Extended Key Usage |
| DCR | Detailed Controls Report |
| EVG | Guidelines for the Issuance and Management of Extended Validation Certificates |
| EVSSL | Extended Validation SSL |
| FIPS | Federal Information Processing Standard |
| IDNs | Internationalized Domain Names |
| ISO/IEC | The International Organization for Standardization/The International Electrotechnical Commission |
| ITSEC | Information Technology Security Evaluation Criteria |
| LDAP | Lightweight Directory Access Protocol |
| MPIC | Multi-Perspective Issuance Corroboration |
| MRSP | Mozilla Root Store Policy |
| OCSP | Online Certificate Status Protocol |
| OID | Object Identifier |
| PMA | Policy Management Authority |
| PIN | Personal Identification Number |
| PKCS | Public Key Cryptography Standard |
| PKI | Public Key Infrastructure |
| QGIS | Qualified Government Information Source |
| QIIS | Qualified Independent Information Source |
| QTIS | Qualified Government Tax Information Source |
| RA | Registration Authority |
| RCA | Root Certification Authority |
| RIR | Regional Internet Registry |
| RSA | Rivest, Shamir, Adleman (Encryption Algorithm) |
| SAN | Subject Alternative Name |
| SSL | Secure Sockets Layer |
| TCSEC | Trusted Computer System Evaluation Criteria |
| URL | Uniform Resource Locator |

---
