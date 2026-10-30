# TAIWAN-CA INC. GLOBAL Certification Authority Certification Practice Statement (TWCA GLOBAL CA CPS)

**(Version 3.3)**

Effective Date: 2026/07/20

---

## Document History

| Version | Effective Date | Issued By | Remarks |
|---------|---------------|-----------|---------|
| 1.0 | 2013/01/22 | TWCA PMA | Initial release |
| 1.1 | 2014/07/02 | TWCA PMA | Added device certificates |
| 1.2 | 2016/08/23 | TWCA PMA | Removed two distinguished names from the SSL Server UCA's own certificate |
| 1.3 | 2017/09/26 | TWCA PMA | Added identity verification procedures for legal entities |
| 1.5 | 2020/01/30 | TWCA PMA | Revised to comply with CABF Baseline Requirement; added CA/Browser Forum policy identifiers; added AATL Certificates |
| 1.6 | 2021/12/21 | TWCA PMA | Section 1.2: Modified TLS/SSL server certificate OID. Sections 1.4.1, 3.2.2: Updated TLS/SSL server certificate and device certificate identity verification methods. Sections 3.2.2, 4.2.1: Updated CAA reference document (RFC 8659). Section 3.2.2: Added BR-compliant domain and IP verification methods and marked deprecated verification methods. Sections 3.3.1, 6.3.2: Updated TLS/SSL certificate maximum validity to 398 days. Section 4.9.12: Added acceptable methods for proving key compromise. Added TSA certificate. Section 3.1.1: Adjusted AATL certificate naming. Section 3.2.2: Modified content to satisfy CABF Baseline Requirement 1.7.5 requirements. Section 3.2.2: All domain validations must undergo Public Suffix check. |
| 1.7 | 2022/12/02 | TWCA PMA | Device certificates merged into TLS/SSL certificates. Sections 2.2, 3.2.2, 9.15: Adjusted applicable certificate types for BR. Section 3.2.2: Appended content to satisfy BR 1.7.8 requirements. Sections 3.1.1, 7.1.4: Appended content to satisfy BR 1.7.9 requirements. Section 8.4: Updated audit version. TLS/SSL certificate naming aligned with CP specification. Layout adjustments. |
| 1.8 | 2023/06/30 | TWCA PMA | Removed TLS/SSL certificate-related content and Business Security EC certificate-related content. Removed device authentication-related content. InfoSec UCA certificate renamed to InfoSec Certificate. Added AATL and S/MIME related content. Adjusted OCSP-related content. Added Sections 1.6, 5.6.1, 5.6.2, 8.7. Revised Sections 1.4, 3.1.1, 3.2, 4.3.1, 5.2.4, 5.4.2, 5.4.5, 6.1.5, 6.1.6, 6.3.2, 6.5.2, 6.8, 7.1.3, 8.2, 8.6, 9.2.1, 9.2.2. |
| 1.9 | 2024/02/29 | TWCA PMA | Added definitions for S/MIME certificates and adjusted related content. Renamed SSL BR to TLS BR. |
| 2.0 | 2024/06/28 | TWCA PMA | Added internal audit 3% inspection: adjusted Section 8.7. Added CAA-related descriptions: adjusted Section 3.2. Added S/MIME personal certificate distinguished name descriptions: adjusted Section 3.1.1. |
| 3.0 | 2025/04/09 | TWCA PMA | Revised in accordance with the "Required Items for Digital Signature Certification Practice Statements" promulgated under the new Electronic Signatures Act. |
| 3.1 | 2025/12/15 | TWCA PMA | Added verification record validity period description. Added MPIC requirements. Added DNSSEC requirements. |
| 3.2 | 2026/07/20 | TWCA PMA | Added developer role. Added vulnerability response and remediation timelines. |
| 3.3 | 2026/08/10 | TWCA PMA | Removed S/MIME certificate-related content, which is now governed by the separately issued TAIWAN-CA INC. S/MIME Certificate Policy and Certification Practice Statement. Removed Section 3.2.3 (Email Mailbox Control Validation) and its subsections, Section 4.2.2.1 (CAA Records Validation), and Section 4.2.2.2 (MPIC); renumbered former Sections 3.2.4 to 3.2.7 as Sections 3.2.3 to 3.2.6. Revised Sections 1.1, 1.2, 1.4.2, 3.1.1, 3.2, 3.2.2, 3.3.1, 4.3.1, 4.9.1.1, 4.9.5, 4.9.13 to 4.9.16, 5.7.1, 6.3.2, 7.1.2, 8.4, 8.5, 8.7, 9.6.1, 9.12.1, 9.15, 9.16.3, and Appendices I and II. Removed Online Certificate Status Protocol (OCSP) provisions, which applied only to S/MIME certificates: Sections 4.9.9 and 7.3 (including 7.3.1 and 7.3.2) now state that OCSP is not provided for the certificate types within the scope of this Statement, and Sections 4.9, 4.9.1.2, 4.9.6, 4.9.10, 4.10.1, 4.10.2 and 9.6.4 were revised to reference the CRL only. Removed from Appendix I the glossary entries for Public Suffix List, Bugzilla, Certification Authority Authorization and Multi-Perspective Issuance Corroboration, and from Appendix II the acronyms CAA, MPIC and TLS BR, all of which became unused. Added to Section 1.1 a declaration of adherence to the CCADB Policy and the root program policies, together with a statement that the scope of this Statement covers InfoSec, AATL and Time-Stamping Certificates. |

---

## Summary

The key items of the TAIWAN-CA INC. GLOBAL Certification Authority Certification Practice Statement are described as follows:

### 1. Competent Authority Approval

This Certification Practice Statement is compiled in accordance with the "Required Items for Digital Signature Certification Practice Statements" promulgated by the competent authority, the Ministry of Digital Affairs. The approval reference number after review is:

2025/12/15 Ministry of Digital Affairs Letter No. Shu-Shou-Chan-Jing-Zi 1140011315

### 2. Issued Certificates

The types, Assurance Levels, and applicable scopes of Global Certificates issued by this Certification Center in accordance with this Statement are listed as follows:

| No. | Certificate Type | Assurance Level | Applicable Scope |
|-----|-----------------|-----------------|------------------|
| 1 | InfoSec Certificate | Class 3 | Financial transactions, securities trading, e-commerce applications, online identity verification, online tax filing, electronic invoices, electronic communication voting, online patent and trademark applications, short-term bill issuance and trading applications, code signing. |
| | | Class 2 | E-commerce applications, online identity verification. |
| | | Class 1 | E-commerce applications, online identity verification. |
| | | Test Level | For testing purposes. |
| 2 | AATL Certificate | Class 3 | E-commerce applications, online identity verification, PDF document signing. |
| | | Class 2 | E-commerce applications, online identity verification, PDF document signing. |
| 3 | Time-Stamping Certificate | Class 3 | Time proof for digital signatures on electronic documents or messages. |

[Note 1]: Certificate Assurance Levels and usage scope are detailed in "1.4 Certificate Usage."

### 3. Important Legal Liability Matters

If a Subscriber encounters grounds for certificate revocation (such as Private Key data leakage or loss), the Subscriber must immediately notify this Certification Center and carry out the certificate revocation procedures. However, the Subscriber shall still bear the risks and responsibilities arising from the use of that certificate before the certificate revocation status has been published.

This Certification Center shall not be liable for damages in processing Subscriber registration data and certificate issuance operations, unless it has failed to follow the provisions of this Statement, violated relevant laws and regulations, or is at fault due to the intentional act or negligence attributable to this Certification Center.

This Certification Center shall not be liable for damages to Subscribers caused by force majeure events (such as earthquakes) or other causes not attributable to this Certification Center (such as war).

If this Certification Center fails to properly safeguard Subscriber registration and certificate-related data, resulting in leakage, misuse, tampering, or unauthorized use of such information that causes damage to third parties, this Certification Center shall be liable for damages.

After receiving a certificate revocation request, this Certification Center shall complete the certificate revocation operation within the time limit specified in Section 4.9.5, and after completion, shall issue the Certificate Revocation List (CRL) and publish it in the Repository at the frequency specified in Section 4.9.7. Before the CRL is published, the Subscriber shall take appropriate actions to minimize the impact on Relying Parties and shall bear all liabilities arising from the use of that certificate. For revocation operation specifications, please refer to Section 4.9.

In the event of a damage compensation dispute between this Certification Center and a Subscriber arising from certificate issuance or use, the liability of both parties shall be limited to the scope defined by relevant laws and regulations and the contract.

By accepting and using a certificate issued by this Certification Center, a Relying Party acknowledges and agrees to the legal liability terms of this Certification Center and relies on that certificate within the scope specified in this Statement.

### 4. Other Important Matters

When there are concerns about a Subscriber's Private Key being lost or compromised, or when Subscriber-related information has changed, the Subscriber must report to this Certification Center in accordance with the relevant operational provisions.

Subscribers shall properly generate, safeguard, and use their Private Keys and comply with usage restrictions on keys and certificates.

When applying for a certificate, a Subscriber must provide truthful and accurate information. When accepting a certificate issued by this Certification Center, the Subscriber must verify the accuracy of the certificate contents and confirm that the Public Key and Private Key are a matching key pair.

When verifying a certificate, a Relying Party shall use the self-signed certificate of the Root Certification Authority (RCA) to verify the digital signature of the User Certification Authority (UCA) certificate, and use the UCA certificate to verify whether the digital signature of the Subscriber certificate was signed by the UCA's Private Key, and verify through the Certificate Revocation List (CRL) whether the certificate has been revoked.

When using a CRL issued by this Certification Center, a Relying Party shall first verify the digital signature to confirm whether the CRL is valid.

This Certification Center obtained the ISO 27001 Information Security Management System certificate in September 2007 and has continuously maintained its validity. In June 2024, a version transition was completed to obtain the ISO 27001:2022 certificate.

This Certification Center obtained the BS 10012 Personal Information Management System certificate in November 2013. In July 2018, a version transition to BS 10012:2017 was completed, and the ISO/IEC 27701 Privacy Information Management System certificate was obtained on July 6, 2020; both have been continuously maintained to the present.

This Certification Center obtained the ISO 20000-1 IT Service Management System certificate in December 2020 and has continuously maintained its validity to the present.

This Certification Center obtained the ISO 22301 Business Continuity Management System certificate in November 2021 and has continuously maintained its validity to the present.

This Certification Center conducts internal audits at least once every six months and engages an accounting firm to conduct at least one external audit per year to ensure that its operations comply with the Certification Practice Statement and Certificate Policy. For detailed audit specifications, please refer to Chapter 8.

---

## 1. Introduction

### 1.1 Overview

TAIWAN-CA INC. (hereinafter referred to as "the Company" or "TWCA") was jointly established with capital contributions from the Taiwan Stock Exchange, Taiwan Depository & Clearing Corporation, Financial Information Service Co., Ltd., and Chunghwa Telecom HiTRUST Inc.

The TAIWAN-CA INC. GLOBAL Certification Authority Certification Practice Statement (TWCA Global Certification Authority Certification Practice Statement; hereinafter referred to as "this Statement") is established in accordance with the TAIWAN-CA INC. Public Key Infrastructure Certificate Policy (hereinafter referred to as the "Certificate Policy") and in compliance with the "Required Items for Digital Signature Certification Practice Statements" promulgated by the competent authority under the Electronic Signatures Act. Its primary purpose is to describe how the TAIWAN-CA INC. GLOBAL Certification Authority (hereinafter referred to as "this Certification Center") complies with the Certificate Policy to carry out certificate issuance and management operations.

In addition to domestic laws and regulations, and in order to ensure the global trustworthiness of the certificates it issues and to maintain the security of Internet communications and user trust, this Certification Center expressly declares its adherence to the latest requirements of the following:

- **CCADB Policy**: Adheres to the requirements of the [Common CA Database (CCADB) Policy](https://www.ccadb.org/policy), co-maintained by multiple browser vendors.
- **Root Program Policies**: Including but not limited to the [Chrome Root Program Policy](https://googlechrome.github.io/chromerootprogram/), the [Microsoft Trusted Root Program Requirements](https://github.com/TrustedRootProgram/Program-Requirements/blob/main/Requirements.md), the [Mozilla Root Store Policy](https://www.mozilla.org/en-US/about/governance/policies/security-group/certs/policy/), and the [Apple Root Program Policy](https://github.com/apple/apple-root-program/blob/main/policy.md).

The scope of this Statement covers the InfoSec Certificates, AATL Certificates, and Time-Stamping Certificates issued by this Certification Center. TLS Certificates are governed by the TAIWAN-CA INC. CYBER Certification Authority Certificate Policy and Certification Practice Statement, and S/MIME Certificates are governed by the TAIWAN-CA INC. S/MIME Certificate Policy and Certification Practice Statement; neither is within the scope of this Statement.

To establish a secure and trustworthy online transaction environment and ensure that information is not easily forged, tampered with, or stolen during network transmission, the Company has specifically planned and built an Internet certification service system with certification-related security mechanisms, using public key cryptography. Its security control mechanisms meet the security standards of the Financial Supervisory Commission's "Operational Standards for Security Controls of Electronic Banking Operations by Financial Institutions," providing non-repudiation of network transaction messages, authentication of Subscriber identity, verification of message integrity, encryption of messages, and other security control mechanisms. It can be used for Internet electronic banking, online trading, as well as online tax filing, insurance, bills and bonds, corporate inquiry and quotation, procurement and payment transactions, and other Internet e-commerce application trading systems.

### 1.2 Document Name and Identification

The name of this Statement is "TAIWAN-CA INC. GLOBAL Certification Authority Certification Practice Statement."

This Statement is established in accordance with the Certificate Policy. The Object Identifiers (OIDs) corresponding to the various certificate classifications detailed herein are described as follows:

| Certificate Type | Object Identifier |
|-----------------|-------------------|
| InfoSec Certificate | 2.16.158.3.1.8.5 |
| | 1.3.6.1.4.1.40869.1.1.23 |
| AATL (Adobe Approved Trust List) Certificate | 1.3.6.1.4.1.40869.1.1.26 |
| Time-Stamping Certificate | 1.3.6.1.4.1.40869.1.1.27 |

### 1.3 Members and Applicable Scope

The "TAIWAN-CA INC. GLOBAL Certification Authority" includes the following members:

- Certification Authority (CA)
- Registration Authority (RA)
- Subscriber
- Relying Party
- Policy Management Authority (PMA)

The Certification Authority is divided by hierarchy and purpose into the "Root Certification Authority" (Root CA, abbreviated as RCA) and the "User Certification Authority" (User CA, abbreviated as UCA), collectively referred to as "this Certification Center." The member relationship diagram is as follows:

This Statement describes in Chapters 3 and 4 how this Certification Center performs Subscriber certificate issuance and management operations, and how Subscribers and Relying Parties apply for and use certificates; Chapter 5 describes the management standards for the Root Certification Authority and User Certification Authority.

#### 1.3.1 Certification Authority

##### 1.3.1.1 Root Certification Authority

The Root Certification Authority (RCA) is the top-level certification management body, serving as the trust anchor of this infrastructure. It is operated and managed by the Company and is primarily responsible for the following tasks:

- Responsible for the issuance and management of User Certification Authority certificates; it shall not issue Subscriber certificates.
- Managing and publishing User Certification Authority certificates and Certificate Revocation Lists (CRL) to the Repository.
- Maintaining the stability and operation of the Repository.
- Established in an independent, security-controlled operating environment. Two or more authorized personnel perform Public Key generation, establishment, and issuance of User Certification Authority certificates. The RCA's certificate is a self-signed certificate. When a certificate is newly generated or renewed, it must be delivered to users or users must be notified to obtain it from the RCA by the fastest means possible.

##### 1.3.1.2 User Certification Authority

The User Certification Authority (UCA) is operated and managed by the Company and is primarily responsible for the following tasks:

- Responsible for the issuance and management of Subscriber certificates.
- Managing and publishing Subscriber certificates and Subscriber certificate Certificate Revocation Lists (CRL) to the Repository.
- Maintaining the stability and operation of the Repository.

##### 1.3.1.3 Policy Management Authority

The TAIWAN-CA INC. Policy Management Authority (PMA) is an organization established within the Company and is responsible for formulating the following:

- Certificate Policy.
- This Statement.
- Operational standards.

#### 1.3.2 Registration Authority

The Registration Authority (RA) is primarily responsible for verifying the identity of certificate applicants and the relevant information required for certificate issuance, which is provided to this Certification Center for certificate issuance.

#### 1.3.3 Subscriber

A Subscriber is the individual identified in the Certificate Subject name within the certificate, who holds the Private Key corresponding to the Public Key contained in the certificate.

Subscribers of this Certification Center are legal entities and natural persons who apply for certificates.

#### 1.3.4 Relying Party

A Relying Party is an individual who uses the Public Key in a certificate issued by this Certification Center to verify the validity of the digital signature message on a Subscriber certificate issued by this Certification Center.

A Relying Party relies on the identity information recorded in the Subscriber certificate to identify domain hostnames and associated Subscriber information.

A Relying Party shall use the information recorded in a certificate issued by this Certification Center to determine whether to rely on that certificate or whether it may be used for a specific purpose.

#### 1.3.5 Other Participants

No stipulations.

### 1.4 Certificate Usage

#### 1.4.1 Certificate Assurance Levels

This Certification Center differentiates Certificate Assurance Levels based on the strength of the identity verification method used by the Subscriber during the registration phase. The meaning of each Certificate Assurance Level is as follows:

| Assurance Level | Assurance Meaning |
|----------------|-------------------|
| Test Level | This Certification Center and the Registration Authority do not perform any Subscriber identity verification procedures. It is for testing purposes only and shall not be used for any application or business other than testing. |
| Class 1 | The User Certification Authority and Registration Authority only guarantee the uniqueness of the Subscriber's identification information within the Company's database. All Subscriber-related information undergoes only limited verification. |
| Class 2 | The User Certification Authority and Registration Authority guarantee the uniqueness of the Subscriber's identification information within the Company's database. For Subscriber-related information, they only provide assurance of completed verification rather than absolute accuracy. |
| Class 3 | In addition to guaranteeing the uniqueness of the Subscriber's identification information within the Company's database, the User Certification Authority and Registration Authority verify Subscriber-related information through multiple rigorous operational procedures, providing identity verification assurance similar in strength to in-person authentication. |
| Class 4 | In addition to guaranteeing the uniqueness of the Subscriber's identification information within the Company's database, the User Certification Authority and Registration Authority verify Subscriber-related information through multiple rigorous operational procedures, providing identity verification assurance at the strength of in-person authentication. |

The identity verification requirements during the registration phase differ for each Assurance Level. Specific descriptions are provided in Section 3.2.

#### 1.4.2 Usage Scope and Liability

**I. Usage Scope**

The usage scope code for certificates is divided into four segments, in the following format:

First Segment . Second Segment . Third Segment . Fourth Segment

The meaning of each segment is as follows:

| Segment | Description | Values |
|---------|-------------|--------|
| First Segment | Identity Authentication Security Level | Class 1 / Class 2 / Class 3 / Test Certificate |
| Second Segment | Usage Type | Single-purpose / Limited-scope multi-purpose |
| Third Segment | Subscriber Identity | Legal entity / Natural person |
| Fourth Segment | Applicable Business Scope | (1) Financial transactions, e-commerce applications, online tax filing, electronic invoices, electronic communication voting, short-term bill issuance and trading applications; (2) Securities trading, e-commerce applications, online tax filing, electronic invoices, electronic communication voting; (3) E-commerce applications, online identity verification, online tax filing, electronic invoices, electronic communication voting, online patent and trademark applications, email applications, code signing, PDF document signing, Time-Stamp for digital signatures on electronic documents or messages |

**First Segment** -- Identity Authentication Security Level:

Classified as (1) Class 1, (2) Class 2, (3) Class 3, or (0) Test Certificate. The security level is determined by the identity authentication method used during Subscriber registration. Please refer to the specifications in "1.4.1 Certificate Assurance Levels."

**Second Segment** -- Usage Type:

Classified as (1) Single-purpose or (2) Limited-scope multi-purpose (e.g., within a financial holding company group):

- Single-purpose: Designated for a specific purpose or restricted to specific transaction counterparties, such as property declaration only, online trading only, or online banking only. In addition, the certificate's Certificate Policy TerseStatement field will record the certificate's designated purpose and restricted transaction counterparties.
- Limited-scope multi-purpose: If a usage scope code is recorded in the certificate's Certificate Policy TerseStatement field, the limited-scope multi-purpose usage follows that code; if none is recorded, the contract signed with the Company or announcements on the Company's website shall prevail.

**Third Segment** -- Subscriber Identity:

Classified as (1) Legal entity or (2) Natural person.

**Fourth Segment** -- Applicable Business Scope:

Classified as (1) Financial transactions, e-commerce applications, online tax filing, electronic invoices, electronic communication voting, short-term bill issuance and trading applications; (2) Securities trading, e-commerce applications, online tax filing, electronic invoices, electronic communication voting; (3) E-commerce applications, online identity verification, online tax filing, electronic invoices, electronic communication voting, online patent and trademark applications, email applications, code signing, PDF document signing, Time-Stamp for digital signatures on electronic documents or messages. Certificates for financial transactions may also be used for securities trading and e-commerce applications and online identity verification, subject to usage scope restrictions or with the Company's consent.

Example: The current usage scope code for enterprise online banking certificates is 3.1.1.1, interpreted as follows:

(3) Security Class 3 . (1) Single-purpose . (1) Legal entity Subscriber . (1) Financial transactions.

**II. Certificate Transaction Limits and Liability**

Certificate transaction limits and compensation limits are described as follows:

- Transaction limits: Different transaction limits are established based on the security level, usage type, customer identity, and applicable business scope. When Subscribers conduct transactions, the transaction amount shall not exceed the transaction limit corresponding to the usage scope code.
- Compensation limits: Different compensation limits are established based on the security level, usage type, and Subscriber identity. The compensation limit refers to the maximum compensation for a single Subscriber certificate; that is, regardless of the number of transactions, the cumulative compensation amount for a single certificate shall not exceed the compensation limit.
- If the Subscriber has a contract with the Company that separately specifies the certificate usage scope, transaction limits, and compensation limits, those contractual terms shall prevail.
- Limited-scope multi-purpose: The usage scope of Subscriber certificates shall be governed by the contract signed with the Company or the relevant operational management standards established by the Company and published on the Company's website.

The certificate usage scope and liability table is shown below:

**Table 1** (Unit: NTD)

| Usage Scope Code | Security Level | Usage Type | Subscriber Identity | Applicable Business Scope | Transaction Limit | Compensation Limit |
|-----------------|----------------|------------|--------------------|--------------------------|--------------------|-------------------|
| 1.1.1.3 | Class 1 | Single-purpose | Legal entity | E-commerce applications, online identity verification | 3,000 | 3,000 |
| 1.1.2.3 | Class 1 | Single-purpose | Natural person | E-commerce applications, online identity verification | 3,000 | 3,000 |
| 2.1.1.3 | Class 2 | Single-purpose | Legal entity | E-commerce applications, online identity verification, email applications, PDF document signing | 900,000 | 300,000 |
| 2.1.2.3 | Class 2 | Single-purpose | Natural person | E-commerce applications, online identity verification, email applications, PDF document signing | 300,000 | 100,000 |
| 3.1.1.1 | Class 3 | Single-purpose | Legal entity | Financial transactions | Unlimited | 2,000,000 |
| 3.2.1.1 | Class 3 | Limited-scope multi-purpose | Legal entity | Financial transactions, e-commerce applications, online tax filing, electronic invoices, electronic communication voting, short-term bill issuance and trading applications | Unlimited | 2,000,000 |
| 3.1.2.1 | Class 3 | Single-purpose | Natural person | Financial transactions | Unlimited | 300,000 |
| 3.2.2.1 | Class 3 | Limited-scope multi-purpose | Natural person | Financial transactions, e-commerce applications, online tax filing, electronic communication voting, short-term bill issuance and trading applications | Unlimited | 300,000 |
| 3.1.1.2 | Class 3 | Single-purpose | Legal entity | Securities trading | 100,000,000 | 2,000,000 |
| 3.2.1.2 | Class 3 | Limited-scope multi-purpose | Legal entity | Securities trading, e-commerce applications, online tax filing, electronic invoices, electronic communication voting | 100,000,000 | 2,000,000 |
| 3.1.2.2 | Class 3 | Single-purpose | Natural person | Securities trading | 15,000,000 | 300,000 |
| 3.2.2.2 | Class 3 | Limited-scope multi-purpose | Natural person | Securities trading, e-commerce applications, online tax filing, electronic communication voting | 15,000,000 | 300,000 |
| 3.1.1.3 | Class 3 | Single-purpose | Legal entity | E-commerce applications, online identity verification, online patent and trademark applications, code signing, PDF document signing, Time-Stamp for digital signatures on electronic documents or messages, email applications | 20,000,000 | 2,000,000 |
| 3.2.1.3 | Class 3 | Limited-scope multi-purpose | Legal entity | E-commerce applications, online identity verification, online tax filing, electronic invoices, electronic communication voting, PDF document signing, email applications | 20,000,000 | 2,000,000 |
| 3.1.2.3 | Class 3 | Single-purpose | Natural person | E-commerce applications, online identity verification, online patent and trademark applications, code signing, PDF document signing, email applications | 2,000,000 | 300,000 |
| 3.2.2.3 | Class 3 | Limited-scope multi-purpose | Natural person | E-commerce applications, online identity verification, online tax filing, electronic communication voting, PDF document signing, email applications | 2,000,000 | 300,000 |

Note 1: If the usage scope code contained in a certificate is not listed in the table above, that certificate shall not be used for any application or business other than testing, and the Company shall bear no compensation liability for such certificate.

Note 2: The certificate usage scope code is recorded in the certificate's "Certificate Policy TerseStatement" field.

#### 1.4.3 Prohibited Use of Certificates

Certificates issued by this Certification Center, in addition to the usage scope specified above, are prohibited from being used for the following purposes:

- Eavesdropping on or intercepting third-party communications.
- Purposes that cause personal injury, death, or psychological harm.
- Applications or businesses that pose significant harm to social order and the public interest.
- Applications or businesses expressly prohibited or excluded by the Electronic Signatures Act, other relevant laws and regulations, or the competent authorities of the relevant industries.

### 1.5 Policy Management

#### 1.5.1 Management Body

The authority responsible for the formulation, revision, and publication of this Statement is the TAIWAN-CA INC. Policy Management Authority (PMA).

#### 1.5.2 Contact Information

For any questions regarding this Statement, or related security incident reports (such as key loss, leakage concerns, or certificate mis-issuance), please contact us through the following channels with detailed information and contact details:

| Item | Details |
|------|---------|
| Company Name | TAIWAN-CA INC. (TWCA) |
| Contact | Customer Service Center |
| Address | 10th Floor, 85, Yen-Ping South Road, Zhongzheng District (100), Taipei, Taiwan, R.O.C. |
| Phone | 886-2-23708886 |
| Fax | 886-2-23700728 |
| Email | ca@twca.com.tw |

#### 1.5.3 Approval of Certification Practice Statement

The Certification Practice Statement established by this Certification Center shall be approved by the PMA.

#### 1.5.4 Certification Practice Statement Approval Procedure

In accordance with the Electronic Signatures Act, the Certification Practice Statement established by this Certification Center must be approved by the competent authority before it may be publicly published and before certificate issuance services may be provided.

### 1.6 Definitions and Abbreviations

Please refer to Appendix 1 and Appendix 2.

---

## 2. Publication and Repository

### 2.1 Repository

This Certification Center is responsible for managing and maintaining the Repository, publicly disclosing the Certificate Policy (CP), Certification Practice Statement (CPS), certificate-related information, and audit reports in the Repository.

This Certification Center ensures that Repository information is available 7 x 24. The Repository URL is: https://www.twca.com.tw/repository

### 2.2 Publication of Certificate Information

The information published by this Certification Center is as follows:

- Certificate Policy.
- Certification Practice Statement (i.e., this Statement).
- Certification Authority certificate chain.
- Certification Authority certificate-related information, including certificate attribute field values and Certificate Revocation List (CRL) download points.
- Audit reports.

### 2.3 Publication Frequency

- A new version of the Certificate Policy (CP) shall be published in the Repository within 7 business days after it has been revised, approved, and made effective by the Policy Management Authority (PMA).
- A new version of the Certification Practice Statement (CPS), after revision and approval by the Policy Management Authority (PMA), shall be submitted to the competent authority for approval. The Company shall publish it in the Repository within 7 business days of receiving the approval letter.
- Once a certificate is issued by this Certification Center, the certificate chain and certificate-related information shall be published in the Repository within 7 business days for Subscriber or Relying Party inquiries. The CRL issuance frequency follows the provisions in Section 4.9.7.
- This Certification Center publishes audit reports in the Repository at least once per year.

### 2.4 Repository Access Control

The Repository is made available to Subscribers or Relying Parties for public inquiry on a read-only basis. However, to prevent malicious attacks or tampering, access control measures are implemented when updating Repository information or during abnormal traffic conditions.
# 3 Identification and Authentication

## 3.1 Naming

### 3.1.1 Types of Names

This Certification Center issues X.509 certificates with subject names in X.501 naming format.

1. Distinguished names of Subscriber certificates issued by this Certification Center:

**(1) InfoSec Certificate**

| Distinguished Name (DN) | Description | DN Content Example | Required |
|---|---|---|---|
| CountryName (C) | Country of the certificate subject | TW | Required |
| Organization (O) | CA company policy information or certificate applicant organization information | Information | Required |
| OrganizationUnit (OU) | CA (issuing unit) information or certificate applicant organizational unit information (1) | TaiCA Information User CA | Optional |
| OrganizationUnit (OU) | Registration Authority English distinguished name or certificate applicant organizational unit information (2) | 12345678-RA-Trade | Optional |
| OrganizationUnit (OU) | Registration Authority application or service distinguished name or certificate applicant organizational unit information (3) | Trade | Optional |
| CommonName (CN) | Distinguished name of the certificate applicant, e.g., the business unified identification number of the enterprise or other identifiable name | 12345678-01-000 | Required |

**(2) AATL Certificate**

| Distinguished Name (DN) | Description | DN Content Example | Required |
|---|---|---|---|
| CountryName (C) | Country of the certificate subject | TW | Required |
| Organization (O) | CA company policy information or certificate applicant organization information | TAIWAN-CA Inc. | Required |
| OrganizationUnit (OU) | CA (issuing unit) information or certificate applicant organizational unit information (1) | TWCA InfoSec User CA | Optional |
| OrganizationUnit (OU) | Registration Authority English distinguished name or certificate applicant organizational unit information (2) | 70759028-RA-AATL | Optional |
| OrganizationUnit (OU) | Registration Authority application or service distinguished name or certificate applicant organizational unit information (3) | Information Security | Optional |
| CommonName (CN) | Distinguished name of the certificate applicant or other identifiable name or other confirmed information | 70759028-AATL | Required |

**(3) Time-Stamping Certificate**

| Distinguished Name (DN) | Description | DN Content Example | Required |
|---|---|---|---|
| CountryName (C) | Country of the certification authority | TW | Required |
| Organization (O) | General distinguished name of the certification authority | TAIWAN-CA Inc. | Required |
| CommonName (CN) | Dedicated CN for time-stamping certificate | 70759028-01-TSA | Required |

2. Distinguished names of the User Certification Authority (UCA) certificates:

**(1) InfoSec UCA Certificate**

| Distinguished Name (DN) | Description |
|---|---|
| CountryName (C) | C=TW |
| Organization (O) | O=TAIWAN-CA Inc. |
| OrganizationUnit (OU) | OU=User CA |
| CommonName (CN) | CN=TWCA InfoSec User CA |

**(2) Time-Stamping UCA Certificate**

| Distinguished Name (DN) | Description |
|---|---|
| CountryName (C) | C=TW |
| Organization (O) | O=TAIWAN-CA |
| OrganizationUnit (OU) | OU=Timestamping Sub-CA |
| CommonName (CN) | CN=TWCA Timestamping Certification Authority |

3. Distinguished names of Root Certification Authority (RCA) self-signed certificates:

| Distinguished Name (DN) | Description |
|---|---|
| CountryName (C) | C=TW |
| Organization (O) | O=TAIWAN-CA |
| OrganizationUnit (OU) | OU=Root CA |
| CommonName (CN) | CN=TWCA Root Certification Authority |

Or:

| Distinguished Name (DN) | Description |
|---|---|
| CountryName (C) | C=TW |
| Organization (O) | O=TAIWAN-CA |
| OrganizationUnit (OU) | OU=Root CA |
| CommonName (CN) | CN=TWCA Global Root CA |

Or:

| Distinguished Name (DN) | Description |
|---|---|
| CountryName (C) | C=TW |
| Organization (O) | O=TAIWAN-CA |
| OrganizationUnit (OU) | OU=Root CA |
| CommonName (CN) | CN=TWCA Global Root CA G2 |

### 3.1.2 Need for Names to Be Meaningful

The subject distinguished name recorded in the Subscriber certificate shall comply with the naming requirements of relevant laws and regulations, must be sufficient to identify a specific legal entity or natural person, and must be identifiable by Relying Parties. For example: an individual's national identification number is processed according to the regulations established by the Ministry of the Interior; an enterprise's business unified identification number is processed according to the regulations established by the competent authority.

If, due to business needs, a subject distinguished name is not an individual's national identification number or a business unified identification number, the Subscriber and the Relying Party shall agree in advance on the Subscriber's distinguished name prior to using the certificate, and shall confirm the accuracy of the Subscriber's distinguished name when verifying the certificate, in addition to obtaining prior consent from this company.

### 3.1.3 Anonymity or Pseudonymity of Subscribers

This Statement does not allow Subscribers to use anonymous names, pseudonyms, aliases, or pen names.

### 3.1.4 Rules for Interpreting Various Name Forms

The interpretation rules for the name forms recorded in certificates are defined in accordance with ITU-T X.520 name attribute definitions.

### 3.1.5 Uniqueness of Names

This Certification Center shall verify the uniqueness of Subscribers' Chinese and English names and legal entity distinguished names.

When the unique distinguished name used for a Subscriber certificate is identical to another, this Certification Center gives priority to the Subscriber who first applied for registration and passed organization identity and domain validation; if a later applicant completes identity information verification before the earlier applicant, the later applicant shall have priority.

If a dispute arises regarding the use of a distinguished name and a competent authority/institution confirms through legitimate documents that the name belongs to another applicant, this Certification Center shall revoke the registered unique distinguished name usage right and revoke the issued certificate, and the Subscriber shall bear the related legal liability.

### 3.1.6 Recognition, Authentication, and Role of Trademarks

This Certification Center respects the registered trademarks of Subscribers' Chinese and English names. After verification, this Certification Center accepts the Subscriber's use of such Chinese and English names but does not guarantee the approval, verification, or uniqueness of the Subscriber's registered trademark. In the event of a trademark dispute, the Subscriber shall resolve it through legal channels on their own.

## 3.2 Initial Identity Validation

The purpose of initial identity validation is to prevent fraudulent applications and to confirm the authenticity of the identity information provided by the applicant. To this end, the Registration Authority (RA) shall adhere to the following principles when performing identity validation:

- Complete authenticity verification, validation verification, and linkage verification of the collected identity documentation, with the verification strength matching the certificate assurance level.
- If the applicant entrusts an agent to handle the application, a verifiable authorization mechanism must be in place to complete the agent's identity and authorization verification.
- The final recorded identity information must be confirmed by the applicant to ensure that the information to be recorded is consistent with what the applicant submitted and is the applicant's correct information.

### 3.2.1 Method of Proving Possession of Private Key

The Public Key contained in the certificate and the corresponding Private Key shall be generated by the Subscriber. The Subscriber shall provide a PKCS#10 certificate signing request signed with the Private Key and submit it to this Certification Center as proof of possession of the Private Key. This Certification Center shall use the Subscriber's Public Key to verify the Subscriber's signature on the PKCS#10 certificate signing request to confirm that the Subscriber is the owner of the Private Key, that the Public Key and Private Key form a key pair, and the integrity of the Subscriber's identity information.

### 3.2.2 Organization Identity Validation

The method of organization identity validation varies depending on the assurance level of the certificate applied for (defined in Section 1.4.1.1). The specific validation methods are described as follows:

| Assurance Level | Organization Identity Validation Method |
|---|---|
| Class 1 | The applicant submits application identification information (such as company registered name and email address information). The Registration Authority (RA) confirms the uniqueness of the identification information and the objective existence of the legal entity's identity (see Section 3.1.5). The applicant may submit the above identification information digitally or in writing. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. |
| Class 2 | In addition to the Class 1 information checks, the applicant must submit the legal entity's name, business unified identification number, or data sufficient to identify the legal entity's identity. The Registration Authority (RA) shall verify the existence and validity of the legal entity's identity through telephone or other means (such as third-party databases). For the initial registration identity identification and authentication procedure, the applicant must submit one piece of identity data issued by a reliable data source (*Note 1), verified by a trusted third party, and checked by the Registration Authority (RA) according to the credential's verification specifications (*Note 2). The applicant may submit the above identification information digitally or in writing. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. Certificates at this assurance level, when used for digital signature purposes, carry the presumption of being from the Subscriber themselves. |
| Class 3 | **In-person processing:** In addition to the Class 2 information checks, the applicant (legal representative) must submit an application form that includes the legal entity's name, business unified identification number, and other legal entity-related information, and the form must bear the seals of the legal entity and the legal representative. The Registration Authority (RA) shall verify the information. The applicant must also provide identity documentation sufficient to identify the applicant (e.g., a photo ID card or passport). If the applicant entrusts an agent to handle the application, the agent must also attach relevant authorization documents and identity documentation sufficient to identify the agent. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. **Non-in-person processing:** In addition to the Class 2 information checks, the applicant must submit a copy of the application form that includes the legal entity's name, business unified identification number, and other legal entity-related information. For the initial registration identity identification and authentication procedure, the applicant must submit two pieces of identity data issued by a reliable data source (*Note 3), verified by a trusted third party, and checked by the Registration Authority (RA) according to the credential's verification specifications (*Note 4). The applicant may submit the above verification information digitally or in writing. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. Certificates at this assurance level, when used for digital signature purposes, carry the presumption of being from the Subscriber themselves. |
| Class 4 | In addition to the Class 3 information checks, the legal representative or their authorized agent must handle the application in person. If the legal representative does not handle it in person, the agent must present relevant authorization documents and must provide identity documentation sufficient to identify the agent. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. Certificates at this assurance level, when used for digital signature purposes, carry the presumption of being from the Subscriber themselves. |

Note 1. The identity data must be a credential at or above the high assurance level of ISO/IEC 29115.

Note 2. Initial registration identity identification and authentication procedures satisfying Assurance Level 2, such as: business certificate verification, legal entity bank account verification, company change registration application form verification, and similar mechanisms.

Note 3. At least one of the two pieces of identity data must be a credential at or above the high assurance level of ISO/IEC 29115.

Note 4. Initial registration identity identification and authentication procedures satisfying Assurance Level 3, such as: business certificate verification combined with company change registration application form verification, legal entity bank account verification combined with account-bound device verification, verification through an agent authorized by the legal entity using natural person Assurance Level 3 mechanisms, and similar mechanisms.

### 3.2.3 Individual Identity Validation

The method of individual identity validation varies depending on the assurance level of the certificate applied for (defined in Section 1.4.1.1). The specific validation methods are described as follows:

| Assurance Level | Individual Identity Validation Method |
|---|---|
| Class 1 | The applicant submits application identification information. The Registration Authority (RA) confirms the uniqueness of the identification information and the objective existence of the identity (see Section 3.1.5). The applicant may submit the above identification information digitally or in writing. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. |
| Class 2 | Satisfies the requirements of Assurance Level 1. For the initial registration identity identification and authentication procedure, the applicant must submit one piece of identity data issued by a reliable data source (*Note 1), verified by a trusted third party, and checked by the Registration Authority (RA) according to the credential's verification specifications (*Note 2). The applicant may submit the above identification information digitally or in writing. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. Certificates at this assurance level, when used for digital signature purposes, carry the presumption of being from the Subscriber themselves. |
| Class 3 | **In-person processing:** In addition to the Class 2 information checks, the applicant must handle the application in person and provide identity documentation sufficient to identify the applicant (e.g., a photo ID card or passport). If the applicant entrusts an agent to handle the application, the agent must also attach relevant authorization documents and identity documentation sufficient to identify the agent. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. **Non-in-person processing:** Satisfies the requirements of Assurance Level 2. For the initial registration identity identification and authentication procedure, the applicant must submit two pieces of identity data issued by a reliable data source (*Note 3), verified by a trusted third party, and checked by the Registration Authority (RA) according to the credential's verification specifications (*Note 4). The applicant may submit the above verification information digitally or in writing. Once the relevant information is submitted, it indicates that the applicant confirms and agrees to the information provided, and the Registration Authority (RA) will verify the accuracy of the Subscriber's identity documentation accordingly. Certificates at this assurance level, when used for digital signature purposes, carry the presumption of being from the Subscriber themselves. |

Note 1. The identity data must be a credential at or above the high assurance level of ISO/IEC 29115.

Note 2. Initial registration identity identification and authentication procedures satisfying Assurance Level 2, such as: bank account verification, financial institution registered phone number verification, telecommunications number authentication supplemented by identity data verification through other authoritative organizations, and similar mechanisms.

Note 3. At least one of the two pieces of identity data must be a credential at or above the high assurance level of ISO/IEC 29115.

Note 4. Initial registration identity identification and authentication procedures satisfying Assurance Level 3, such as: online banking account and password verification combined with registered phone number verification, telecommunications number authentication combined with bank account verification, natural person certificate verification combined with manual inspection, and similar mechanisms.

Note 5. This Certification Center does not issue Assurance Level 4 individual certificates.

### 3.2.4 Non-Verified Subscriber Information

This Certification Center requires that all Subscriber information be verified.

### 3.2.5 Validation of Authority

The identity documentation of the legal entity's representative, agent, and the legal entity (hereinafter referred to as "such persons") must be official identity documents issued by government authorities (hereinafter referred to as "such documents") or credentials recognized by this Certification Center as sufficiently representative of the original applicant (such as business certificates). The Registration Authority (RA) shall confirm the authenticity of the agent's authorization documents, and such persons shall attest that such documents are authentic.

### 3.2.6 Mutual Communication Methods

No stipulation.

## 3.3 Identification and Authentication for Re-key

### 3.3.1 Routine Certificate Re-key

As the duration of key usage increases, the risk of loss or compromise increases. Subscribers must periodically re-key to ensure key security.

When the lifecycle of a Subscriber's key (i.e., certificate) is set to one year, it must be renewed upon expiration after one year. That is, the validity period of the Subscriber certificate is one year. Within the certificate renewal period before the expiration date (e.g., one month before expiration), the Subscriber must independently generate a new Public Key and Private Key pair and apply to this Certification Center / Registration Authority (RA) for the issuance of a new certificate. This constitutes the re-key of the certificate and Private Key.

Certificate validity period and Private Key validity period limits:

| Certificate Type | Certificate Validity Period | Private Key Validity Period |
|---|---|---|
| InfoSec Certificate | Maximum 39 months | Same as certificate validity period |
| AATL Certificate | Maximum 39 months | Same as certificate validity period |
| Time-Stamping Certificate | Maximum 135 months | Maximum 15 months |

Before the certificate validity period expires, the new Public Key certificate signing request shall be signed with the currently valid Private Key and transmitted to the Registration Authority (RA) to apply for new certificate issuance.

When the Subscriber performs certificate and Private Key re-key after the certificate validity period has expired, the Subscriber must apply for certificate renewal with the Registration Authority (RA) using the identity validation methods specified in Section 3.2. After obtaining the identity authentication identification data for the certificate renewal application from the Registration Authority (RA), the Subscriber shall submit the certificate signing request signed with the new Private Key, together with the Subscriber's identity authentication identification information, to this Certification Center / Registration Authority (RA) according to the Registration Authority's operational procedures to apply for new certificate issuance. Upon receiving the Subscriber's certificate signing request, the Registration Authority (RA) shall verify the legitimacy of Private Key possession and verify the legitimacy and integrity of the Subscriber's certificate signing request.

### 3.3.2 Re-key After Certificate Revocation

After a Subscriber's certificate is revoked, the Subscriber must undergo the initial validation method specified in Section 3.2 or other methods that can effectively confirm the Subscriber's identity, and re-apply for a new certificate.

## 3.4 Revocation Request

When a Subscriber submits a certificate revocation request, the Subscriber may contact this Certification Center via email, telephone, or physical documents. In addition to verifying the Subscriber's identity, this Certification Center or the Registration Authority (RA) shall verify the authenticity of the request data and meet the identity validation requirements corresponding to Section 3.2.2 or Section 3.2.3. If necessary, the original certificate applicant shall be contacted to confirm the specific facts of the intended certificate revocation. If handled through an agent, the requirements of Section 3.2.5 must be satisfied. Detailed revocation procedures are governed by the provisions of Section 4.9.

Competent authorities, courts, litigation arbitration bodies, and other authorized parties shall submit applications to the Registration Authority (RA) in writing.

# 4 Certificate Life-Cycle Management

## 4.1 Certificate Application

### 4.1.1 Who Can Submit a Certificate Application

For a legal entity applying for a certificate, the certificate applicant shall be the representative or their agent.

For a natural person applying for a certificate, the certificate applicant shall be the individual or their agent.

### 4.1.2 Registration Process and Responsibilities

The Subscriber shall apply to the Registration Authority (RA) for certificate issuance. Before applying for a certificate, the Subscriber must complete the Subscriber registration application with the Registration Authority (RA).

The Registration Authority (RA) must explain to the Subscriber in detail the rights and obligations stated in the certificate application form and the contract, the operational procedures of related business operations, and provide user manuals and operational documents, all of which must be agreed to and confirmed by the Subscriber.

The Subscriber must accurately and thoroughly complete the relevant application forms and provide the relevant supporting documents. After the Registration Authority (RA) verifies the Subscriber's identity and supporting documents in accordance with the security-level operational procedures, identity identification codes and protection passwords are set for the Subscriber, completing the Subscriber registration application process.

## 4.2 Certificate Application Processing

### 4.2.1 Identification and Authentication Procedures

The identity authentication procedures for each security level are described in Section 1.4.1. The identification and authentication procedures are described in Section 3.2.

### 4.2.2 Approval or Rejection of Certificate Applications

Upon completion of the identification and authentication procedures specified in Section 4.2.1, the certificate application is considered approved. If the identification and authentication procedures cannot be completed, the certificate application shall be rejected.

### 4.2.3 Time to Process Certificate Applications

Subject to the contract signed between the Subscriber and this company.

## 4.3 Certificate Issuance

### 4.3.1 CA Actions During Certificate Issuance

The certificate issuance procedure is as follows:

1. The Subscriber logs in to the Registration Authority (RA) after at least passing identity identification code and password verification, and transmits the generated certificate signing request signed with the Subscriber's Private Key to the Registration Authority (RA).
2. After the Registration Authority (RA) verifies that the Subscriber's identity identification code and password are correct, it checks the integrity of the Subscriber's certificate signing request. Once verified as correct, the Registration Authority (RA) signs the Subscriber's certificate signing request with the Registration Authority's Private Key, encrypts it for protection, and transmits it to this Certification Center.
3. The reviewing personnel of this Certification Center log in to the certificate management website through two-factor authentication to perform the validation procedures defined in Section 3.2, and another reviewing officer performs a review procedure. Once all data is confirmed to be correct, the certificate is issued and transmitted to the Registration Authority (RA).
4. The Registration Authority (RA) checks the legitimacy and integrity of the Subscriber certificate response message returned by this Certification Center. Once verified as correct, the Subscriber certificate is transmitted to the applicant.

The certificate start date of Subscriber certificates issued by this Certification Center shall not be backdated; that is, the certificate start date shall not be earlier than the time of certificate issuance.

The Registration Authority (RA) or this Certification Center may, for security control considerations, deliver the certificate application and Private Key generation software to the Subscriber in a trusted and secure manner. Such software must undergo appropriate security evaluation and verification by the Registration Authority (RA) or this Certification Center.

### 4.3.2 Notification of Certificate Issuance to Subscriber

For Subscribers who apply for issuance in real-time online, the issuance result is available immediately after this Certification Center completes the certificate issuance process.

For Subscribers who do not apply for issuance in real-time online, this Certification Center shall notify the Subscriber by telephone or email after completing the certificate issuance process.

## 4.4 Certificate Acceptance

### 4.4.1 Certificate Acceptance Procedures

After receiving the certificate issued by this Certification Center, the Subscriber shall perform the following procedures:

1. Confirm that the certificate content is consistent with the information at the time of application and is the Subscriber's correct information.
2. Check whether the Public Key in the certificate is the same as the Public Key information in the PKCS#10 certificate signing request.
3. The Subscriber must verify the certificate chain of the certificate, check the correctness, integrity, and validity of each certificate in the chain, and confirm whether the certificate has been revoked, whether the certificate validity period has expired, and whether it was indeed issued by this Certification Center.
4. If an error is found in the certificate, the Registration Authority (RA) shall be immediately notified to revoke the certificate, and the certificate issuance procedure in Section 4.3 may be re-performed.
5. After receiving the applied certificate, the Subscriber must confirm that they have fully understood and agree to the rights and obligations of using the certificate. If the Subscriber does not agree, it shall be deemed a refusal to accept the certificate, and the Subscriber shall notify the Registration Authority (RA) to revoke the certificate.

This Certification Center only accepts certificate change requests submitted by the Subscriber to this Certification Center within 7 days after certificate issuance.

### 4.4.2 Publication of the Certificate by the CA

After the Subscriber completes the acceptance procedure, this Certification Center shall publish the issued Subscriber certificate in the Repository.

### 4.4.3 Notification of Certificate Issuance by the CA to Other Entities

No stipulation.

## 4.5 Key Pair and Certificate Usage

### 4.5.1 Subscriber Private Key and Certificate Usage

The usage, scope of application, and limitations of the Subscriber certificate are governed by the provisions of Section 1.4.

The Subscriber shall properly protect their Private Key. If there are any concerns about unauthorized use, exposure, or loss, the Subscriber must report to the Registration Authority (RA).

### 4.5.2 Relying Party Public Key and Certificate Usage

Before relying on a Subscriber certificate issued by this Certification Center, the Relying Party shall at a minimum perform the following necessary procedures to determine whether to rely on the certificate:

1. Obtain the self-signed certificate of the Root Certification Authority (RCA) of this Certification Center through an appropriate and secure channel.
2. Check whether the RCA self-signed certificate, the User Certification Authority (UCA) certificate, and the Subscriber certificate have expired.
3. Use the Public Key of the RCA self-signed certificate to verify whether the digital signature of the UCA certificate is valid and has not been revoked.
4. Use the Public Key of the UCA certificate to verify whether the digital signature of the Subscriber certificate is valid.
5. Check that the Subscriber certificate has not been revoked by the UCA.

If the above verifications cannot be passed, it indicates that the Subscriber certificate obtained by the Relying Party was not issued by this Certification Center or the certificate has expired, and the Relying Party shall not rely on the Subscriber certificate.

## 4.6 Certificate Renewal

Certificate renewal refers to the re-issuance of a certificate with the same key, different serial number, and extended validity period under the condition that the Subscriber's identification information remains unchanged.

This Certification Center does not provide certificate renewal services.

## 4.7 Certificate Re-key

Certificate re-key refers to generating a new Public Key and Private Key pair and applying to the certification authority for certificate issuance using the original registration information.

### 4.7.1 Circumstances for Certificate Re-key

As specified in Section 3.3.1.

### 4.7.2 Who May Request Re-key

The Subscriber has the right to re-key the certificate.

### 4.7.3 Certificate Re-key Procedures

The Subscriber's identity shall be verified in accordance with the provisions of Section 3.3.

The certificate shall be issued in accordance with the provisions of Section 4.3.

### 4.7.4 Notification of Re-keyed Certificate Issuance

As specified in Section 4.3.2.

### 4.7.5 Acceptance Procedures for Re-keyed Certificates

As specified in Section 4.4.

### 4.7.6 Publication of Re-keyed Certificates by the CA

As specified in Section 4.4.2.

### 4.7.7 Notification of Re-keyed Certificates to Other Entities

As specified in Section 4.4.3.

## 4.8 Certificate Modification

Certificate modification refers to the re-issuance of a certificate to the Subscriber when the Public Key in the certificate remains unchanged but the recorded Subscriber's name identification information needs to be changed.

This Certification Center does not accept certificate modification by the Subscriber. If the Subscriber's identification information or other information recorded in the certificate needs to be changed, the certificate must first be revoked in accordance with Section 4.9, and then a new certificate issuance shall be applied for in accordance with Sections 4.1, 4.2, 4.3, and 4.4.

## 4.9 Certificate Revocation and Suspension

When a revocation event occurs, the relevant certificate shall be revoked and added to the CRL. Revoked certificates must be included in all subsequently published CRLs until the certificate expires.

### 4.9.1 Circumstances for Revocation

#### 4.9.1.1 Reasons for Revoking a Subscriber Certificate

During the certificate's validity period, certificate revocation must be performed when any of the following circumstances occur:

**Subscriber:**

- The Subscriber wishes to revoke the use of the certificate, for example: when a company employee's position changes or the employee leaves the company, for security control considerations, or when the Subscriber intends to discontinue use of the certificate and revokes it.
- When the certificate content and Subscriber registration-related information change, for example: company merger and consolidation, or renewal of the company's registered name and registration-related data due to special reasons.
- When the Private Key associated with the certificate is damaged, lost, exposed, tampered with, or there is a concern of theft by a third party.

**This Certification Center may revoke a Subscriber certificate on its own:**

- Due to changes in the certificate system's key, inapplicability, or certificate system integration requirements.
- Due to the need to transfer to another certification authority when the certification authority's business ceases operations.
- When the Subscriber uses the certificate and the Registration Authority (this Certification Center) declares that the Subscriber has not fulfilled obligations under the contract or operational procedures (such as fees), or has improperly used the certificate in violation of government laws, regulations, or business usage rules.
- When the Subscriber-related information in the certificate content does not comply with the certificate policy, this Statement, or business usage rules, for example, when the Subscriber certificate content does not match the registration data, or due to negligence in registration data entry, or when the certificate application was not properly authorized.

**Authorized entities:**

- Competent authorities or courts applying through formal and legal operational procedures for business needs.

#### 4.9.1.2 Reasons for Revoking a Subordinate CA Certificate

The Root Certification Authority (RCA) shall revoke the certificate within 7 days when any of the following circumstances occur:

- The subordinate certification authority requests revocation in writing.
- The subordinate certification authority notifies that the original certificate application was not authorized.
- The key used by the subordinate certification authority violates the provisions of Sections 6.1.5 and 6.1.6.
- The subordinate certification authority's certificate has been misused.
- The subordinate certification authority's certificate was not issued in accordance with the procedures specified in the certificate policy or this Statement.
- The information recorded in the certificate is incorrect.
- The Root Certification Authority (RCA) or subordinate certification authority ceases operations and has not arranged for another certification authority to provide certificate revocation services.
- The authority of the Root Certification Authority (RCA) or subordinate certification authority to issue certificates has expired, been revoked, or been suspended; unless other plans have been arranged to continue maintaining CRL services.
- Items required to be revoked by the certificate policy.

### 4.9.2 Who Can Request Revocation

The Registration Authority (RA) or this Certification Center associated with the Subscriber, competent authorities or legally authorized third parties, and the Subscriber all have the right to apply for certificate revocation.

**Subscriber:**

The Subscriber may apply to revoke the Subscriber certificate according to the Registration Authority's operational procedures, based on their needs.

**Registration Authority (this Certification Center):**

When the Registration Authority (this Certification Center) applies to revoke a Subscriber certificate, it must process the revocation in accordance with Section 4.9.3 and must comply with the contract between the Registration Authority and the Subscriber and related operational procedures.

**Authorized third parties:**

- Company authorized personnel may revoke the Subscriber certificate under the company's lawful authorization.
- Upon application by a lawful heir to the Subscriber's assets, the Registration Authority (RA) must verify the Subscriber's death and the lawful heir's identity in accordance with related operational procedures.
- Upon application by the Registration Authority (RA) due to court litigation or arbitration, subject to compliance with this company's related operational procedures.
- Competent authorities, subject to compliance with related laws and regulations.

### 4.9.3 Procedure for Revocation Request

The certificate revocation procedure is as follows:

1. Those authorized to request certificate revocation as defined in Section 4.9.2 shall apply for certificate revocation.
2. If the certificate Subscriber submits a certificate revocation application, authentication shall be performed as defined in Section 3.4. Other certificate revocation applications shall be verified based on the certificate revocation reasons defined in Section 4.9.1.
3. After this Certification Center completes authentication, the revocation shall be completed within the time limit specified in Section 4.9.1.

### 4.9.4 Revocation Request Grace Period

After a certificate revocation event occurs, the Subscriber shall submit a certificate revocation request within a reasonable period consistent with general commercial practice. This Statement does not mandate a specific time limit. If key compromise is suspected or confirmed, or if there are other security matters requiring certificate revocation, the Subscriber shall submit the request within 24 hours.

This Certification Center provides online 24 x 7 acceptance of certificate revocation applications and certificate misuse reports. The post-acceptance processing mechanism is described in Section 4.9.5.

### 4.9.5 Time Within Which CA Must Process the Revocation Request

When the Registration Authority (or this Certification Center) receives a Subscriber certificate revocation request or misuse report, it must be processed immediately during business or working hours, and must be completed within at most 1 business day.


### 4.9.6 Revocation Checking Requirements for Relying Parties

Relying Parties shall determine, based on their own risk, liability, and potential consequences, the frequency with which they verify the status of certificates issued by this Certification Center through the CRL.

If the Relying Party checks the certificate status through CRL issued by this Certification Center, the Relying Party must verify that the CRL was issued by this Certification Center before use, including verifying the correctness and validity of the CRL's digital signature. Other verification considerations must satisfy the relevant requirements of RFC 5280.


### 4.9.7 CRL Issuance Frequency

This Certification Center shall update and issue the CRL at least once every 24 hours.

### 4.9.8 Maximum Latency for CRLs

No stipulation.

### 4.9.9 On-Line Revocation/Status Checking Availability

This Certification Center does not provide Online Certificate Status Protocol (OCSP) services for the certificate types within the scope of this Statement. The status of certificates issued by this Certification Center is made available through the Certificate Revocation List (CRL) published in the Repository, at the issuance frequency specified in Section 4.9.7.

### 4.9.10 On-Line Revocation Checking Requirements

The Relying Party must use the CRL issued by this Certification Center to check the certificate status before deciding to rely on a certificate issued by this Certification Center.


### 4.9.11 Other Forms of Revocation Advertisements Available

No stipulation.

### 4.9.12 Special Requirements Related to Key Compromise

If key compromise is suspected, the reporter may contact the appropriate contact point of this Certification Center through legitimate channels with supporting evidence. This Certification Center accepts the following method to demonstrate suspected key compromise:

- Provide a CSR (in standard PKCS#10 format) signed with the suspected compromised key for verification, where the common name of the CSR must be "Proof of Key Compromise for TWCA", for this Certification Center to verify its authenticity.

When this Certification Center's signing key is compromised, the following procedures shall be performed:

1. Generate a new signing key pair and the corresponding new certificate.
2. Revoke all issued certificates, and issue a CRL signed with the new signing key. The CRL shall include information on all issued unexpired certificates (including revoked certificates issued before the key compromise).
3. Notify the Subscribers.
4. Securely deliver new certificates to the Subscribers.
5. Use the new signing key to issue new certificates to the Subscribers.

If a Subscriber's key is suspected or confirmed to be compromised, the Subscriber shall notify this Certification Center to revoke the certificate within 24 hours of becoming aware of the fact.

### 4.9.13 Circumstances for Suspension

**1. InfoSec Certificate**

The operational procedures for temporary suspension of Subscriber certificates shall comply with the business needs and operational procedures of this Certification Center and the Registration Authority (RA). If the certificate suspension service is provided, the Subscriber may suspend the certificate during the certificate's validity period when any of the following circumstances occur:

**Subscriber:**

- When there are security concerns that the Private Key of the certificate may be lost or leaked, and the Subscriber does not wish to apply for certificate revocation in order to preserve the Subscriber's right to use the certificate, the Subscriber wishes to temporarily suspend the use of the certificate.
- The Subscriber wishes to temporarily stop using the certificate for a period of time.

**Registration Authority / this Certification Center:**

- When the Subscriber uses the certificate and the Registration Authority / this Certification Center declares that the Subscriber has not fulfilled obligations (e.g., fees), or there are concerns about improper use of the certificate that may violate government laws, regulations, this Statement, or business usage rules.

**Authorized entities:**

- Competent authorities or courts applying through operational procedures for business needs.

**2. AATL Certificate and Time-Stamping Certificate**

Certificate suspension services are not provided.

If a key is compromised, the certificate suspension procedure shall not be used; the matter shall be handled in accordance with Section 4.9.12.

### 4.9.14 Who Can Request Suspension

**1. InfoSec Certificate**

The Registration Authority (RA) or this Certification Center associated with the Subscriber, competent authorities or legally authorized third parties, and the Subscriber all have the right to suspend the certificate.

**Subscriber:**

The Subscriber may apply to suspend the Subscriber certificate according to the Registration Authority's operational procedures, based on their needs.

**Registration Authority (this Certification Center):**

When the Registration Authority (this Certification Center) applies to suspend a Subscriber certificate, it must process the suspension in accordance with Section 4.9.15 and must comply with the contract between the Registration Authority and the Subscriber and related operational procedures.

**Authorized third parties:**

- Company personnel may apply to suspend the Subscriber certificate under the company's lawful authorization.
- Upon application by the Registration Authority (RA) due to court litigation or arbitration, subject to compliance with this Certification Center's related operational procedures.
- Competent authorities, subject to compliance with related laws and regulations.

**2. AATL Certificate and Time-Stamping Certificate**

Not applicable.

### 4.9.15 Procedure for Suspension Request

**1. InfoSec Certificate**

**In-person processing:**

The Subscriber submits a certificate suspension request. After this Certification Center verifies the Subscriber's identity, the operational personnel shall execute the certificate suspension.

**Non-in-person processing:**

The Subscriber logs in to the Registration Authority's certificate system webpage. After the Registration Authority (RA) verifies the Subscriber's identity, this Certification Center's certificate system executes the certificate suspension.

When the Registration Authority (RA) receives the Subscriber certificate suspension response message from this Certification Center, it checks the legitimacy and integrity of the response message. Once verified as correct, the response is relayed to the requesting Subscriber.

Competent authorities, courts, litigation arbitration bodies, and other authorized parties shall submit applications to the Registration Authority (RA) in writing.

After the reason for the suspension is resolved, if the certificate Subscriber intends to continue using the certificate and the certificate's validity period has not yet expired, the certificate Subscriber may apply to the Registration Authority (RA) for certificate reinstatement to make the certificate valid and usable.

**2. AATL Certificate and Time-Stamping Certificate**

Not applicable.

### 4.9.16 Limits on Suspension Period

**1. InfoSec Certificate**

After the Subscriber completes the certificate suspension, until the end of the certificate's validity period, if the certificate is not reinstated, the certificate shall remain in the CRL as an unusable certificate.

The certificate suspension period runs from when the Subscriber certificate is placed in the CRL after completing the suspension, until the Subscriber applies for and completes certificate reinstatement, at which time the certificate is transferred from the CRL to an active certificate. If the certificate reinstatement is not performed beyond the certificate's validity period, the certificate becomes an expired certificate (which, like a revoked certificate, is an unusable certificate).

The maximum duration of certificate suspension is the validity period of the Subscriber certificate issued by this Certification Center.

**2. AATL Certificate and Time-Stamping Certificate**

Not applicable.

## 4.10 Certificate Status Services

### 4.10.1 Operational Characteristics

Subscribers may query the certificate status through the CRL provided by this Certification Center.

The download location for the CRL is recorded in the cRLDistributionPoints extension field of the certificate.

The revocation information for revoked certificates is removed from the CRL only after the certificate's validity period has expired.

### 4.10.2 Service Availability

This Certification Center provides an online 24x7 Repository for Relying Parties to query the certificate status of all unexpired certificates.

All Subscriber certificates issued by this Certification Center can have their certificate status queried via CRL.

Under normal network operation conditions, the response time of the CRL service provided by this Certification Center is within 10 seconds.

This Certification Center provides a 24x7 complaint mechanism for responding to significant certificate issues (e.g., certificates fraudulently applied for or erroneously issued). Once a complaint is confirmed, the complained-about certificate shall be revoked, and if there is an illegal incident, it will be referred to law enforcement agencies. The contact point of this Certification Center is described in Section 1.5.2.

### 4.10.3 Optional Features

No stipulation.

## 4.11 End of Subscription

When a certificate issued by this Certification Center expires, is revoked, or this Certification Center ceases operations, the issued certificate becomes invalid.

## 4.12 Key Escrow and Recovery

### 4.12.1 Key Escrow and Recovery Policy and Practices

The Private Key of this Certification Center shall not be escrowed. Escrow of the Subscriber's Private Key is not prohibited.

### 4.12.2 Session Key Encapsulation and Recovery Policy and Practices

No stipulation.
# 5 Facility, Management, and Operational Controls

The security controls of this Certification Center comply with the "NETWORK AND CERTIFICATE SYSTEM SECURITY REQUIREMENTS" published by the CA/Browser Forum.

## 5.1 Physical Controls

### 5.1.1 Site Location and Construction

The server room of this Certification Center is located within the Company's premises, meeting the facility standards for storing highly important and sensitive information. It incorporates physical security mechanisms including access control, security systems, intrusion detection, and surveillance cameras to prevent unauthorized access to the equipment of this Certification Center.

### 5.1.2 Physical Access

The physical access control measures for the server room of this Certification Center are as follows:

Three layers of access control with identity verification (using Smart Cards or fingerprint recognition), of which at least two require simultaneous identity authentication of two or more persons before entry is permitted. The facility is equipped with 24-hour CCTV motion-detection surveillance equipment and infrared intrusion alarm systems to record server room access and prevent unauthorized entry.

Private Key backup data related to the operations of this Certification Center is securely stored in safes protected by surveillance systems. All operational personnel involved in certificate management operations must have at least two persons present to perform certificate management tasks, with all activities monitored by surveillance equipment.

Hardware, software, and Hardware Security Module (HSM) equipment are all placed in environments protected by surveillance systems, and at least two persons must be present to perform key management operations.

### 5.1.3 Power and Air Conditioning

The server room of this Certification Center is equipped with diesel generators and an Uninterruptible Power Supply (UPS). When the normal power supply system experiences anomalies, it automatically switches to diesel generator power, with the UPS providing stable power during the switchover process.

An independent air conditioning system is in place to ensure stable system operation and provide an optimal working environment, with regular maintenance and testing performed.

### 5.1.4 Water Exposures

The server room of this Certification Center is a sealed building structure. Apart from internal access doors, the exterior is entirely constructed of concrete. The floor is fitted with raised flooring, eliminating concerns about water ingress.

### 5.1.5 Fire Prevention

The server room of this Certification Center is constructed with fire-resistant materials and is equipped with fire suppression equipment connected to a central monitoring system, capable of automatically activating fire suppression functions upon fire detection.

### 5.1.6 Media Storage

The media storage environment of this Certification Center can prevent accidental damage to media. It provides equipment and an environment with anti-magnetic and anti-static interference protection for magnetic media. Important backup media is stored in fire-resistant safes, with one copy of the backup information stored at an off-site backup location with security control measures.

### 5.1.7 Waste Disposal

When hardware equipment, disk drives, and cryptographic devices used by this Certification Center are decommissioned, any commercially sensitive and confidential information stored therein must undergo secure erasure and destruction, verified by the audit unit, with verification documents retained.

When documents and media containing commercially sensitive and confidential information are disposed of, they must undergo secure erasure and destruction so that the information cannot be recovered or accessed. This must be verified by the audit unit, with verification documents retained.

### 5.1.8 Off-site Backup

This Certification Center has established a Disaster Recovery Site with backup equipment. When the daily operational equipment cannot function normally due to external factors, the backup equipment can provide continued operational capability for this Certification Center.

Related media information and documents required for the operation of this Certification Center are backed up and stored in a highly secure off-site backup environment equipped with temperature and humidity controls, anti-magnetic and anti-static interference protection, surveillance camera monitoring, and access authorization requirements.

Backup log files of this Certification Center are stored at the highly secured Disaster Recovery Site.

## 5.2 Procedural Controls

### 5.2.1 Trusted Roles

Under the Public Key Infrastructure (PKI) framework, the certificate management operations of this Certification Center must be conducted under rigorous and secure operational processes. To ensure that the separation of duties and responsibilities, as well as role backup, do not compromise the overall system security and operational integrity, the Trusted Roles and their division of duties within this Certification Center are as follows:

- System Administrator: Responsible for system installation, management operations, and environment parameter configuration.
- Certificate Officer: Responsible for certificate issuance and certificate revocation.
- Auditor: Responsible for conducting internal audits, reviewing, and maintaining Audit Logs.
- Operator: Responsible for routine maintenance operations such as backup, restoration, and website data maintenance.
- Developer: Responsible for system design and development.

### 5.2.2 Number of Persons Required Per Task

The personnel requirements for each Trusted Role are as follows:

- System Administrator: At least 2 persons.
- Certificate Officer: At least 2 persons.
- Auditor: At least 1 person.
- Operator: At least 2 persons.
- Developer: At least 1 person.

Before developed code is submitted for deployment to the production environment, it must pass Multi-Party Control procedures. All changes require review and confirmation by at least two authorized trusted persons, ensuring that the code complies with security standards and business logic before release is approved.

### 5.2.3 Identification and Authentication for Each Role

The System Administrators, Certificate Officers, Auditors, and Operators who perform certificate management operations for this Certification Center each have system resource access segregated by business function, using unique identification codes, Smart Cards, and associated identity verification passwords to achieve identification and authentication of Trusted Roles.

Developers of this Certification Center access source code uniformly through a code version control management platform integrated with Active Directory (AD) account permission control mechanisms, with corresponding project access permissions granted based on development tasks.

All operations performed by relevant operational personnel according to their business needs are recorded in detail to ensure the auditability of system resource usage and to enable assessment of system security threats and risks.

### 5.2.4 Roles Requiring Separation of Duties

| Role | Certificate Officer | System Administrator | Auditor | Operator | Developer |
|---|---|---|---|---|---|
| Certificate Officer | ○ | X | X | X | X |
| System Administrator | X | ○ | X | ○ | X |
| Auditor | X | X | ○ | X | X |
| Operator | X | ○ | X | ○ | X |
| Developer | X | X | X | X | ○ |

## 5.3 Personnel Controls

### 5.3.1 Qualifications, Experience, and Clearance Requirements

Operational personnel of this Certification Center must be loyal, trustworthy, and dedicated to their work. They shall have no other concurrent employment that would affect certificate operations, and shall have no records of legal violations or poor credit.

- Certificate Officers shall have at least practical experience in certificate operations, or shall have passed examinations after receiving certificate operations-related training.
- System Administrators shall have at least practical experience in certificate operations and experience in computer system planning and operations management.
- Auditors shall have at least professional knowledge in information security or system auditing, and experience in independently reviewing operational processes.
- Operators shall have at least received training in certificate lifecycle management and system administration.
- Developers shall have at least the ability to write secure code and develop systems.

### 5.3.2 Background Check Procedures

Personnel of this Certification Center must undergo identity background security checks conducted by the human resources management department in accordance with background check regulations, and practical and experience reviews conducted by the relevant operational departments. Employment may commence only after these reviews are passed. Annual reviews of practical experience and qualifications must be conducted according to each operational role's job characteristics, serving as a basis for determining whether the individual is suitable for the relevant work or for making job adjustment decisions.

### 5.3.3 Training Requirements

Operational personnel of this Certification Center shall receive training appropriate to their duties, covering the hardware and software functions required for the operation of this Certification Center's systems, operational procedures, certificate issuance verification procedures, security control procedures, disaster backup operational standards, key management operations, certificate policy and this Statement, and other information security-related operational standards. When there are changes to the certificate system or new systems are added, appropriate training shall also be provided.

For hardware, software, application systems, and security management systems related to the certificate management system, this Certification Center has established comprehensive training standards. Training on relevant skills is conducted when new personnel are hired or when there are changes to this Certification Center's systems. Detailed performance records are maintained after training completion, serving as a reference for delegating work to relevant operational personnel.

### 5.3.4 Retraining Frequency and Requirements

For personnel involved in the operation of the certificate management system, this Certification Center shall review their relevant knowledge and skills for operating the certificate management system at least once a year and provide appropriate training. Training shall also be provided to all system operation-related personnel when there are updates to the certificate management system functions, addition of new systems, or advances and updates in PKI-related knowledge and technology.

### 5.3.5 Job Rotation Frequency and Sequence

To meet system operational needs and personnel suitability, the Company will select suitable candidates for rotation to appropriate positions. However, appropriate knowledge and skill training must be provided before the transfer.

- A System Administrator must have left the original position for at least 1 year before being eligible to transfer to a Certificate Officer or Auditor role.
- A Certificate Officer must have left the original position for at least 1 year before being eligible to transfer to a System Administrator or Auditor role.
- An Auditor must have left the original position for at least 1 year before being eligible to transfer to a System Administrator or Certificate Officer role.
- An Operator must have served for at least 2 years and have received and passed relevant training before being eligible to transfer to a System Administrator, Certificate Officer, or Auditor role.
- A Developer must have left the original position for at least 1 year before being eligible to transfer to a System Administrator, Certificate Officer, or Auditor role.

### 5.3.6 Sanctions for Unauthorized Actions

When operational personnel involved in the operation of this Certification Center's certificate management system intentionally or negligently perform operations outside their own duties, regardless of whether it causes security issues with the certificate management system, the incident must be immediately reported to the supervisory manager and handled in accordance with relevant operational standards.

### 5.3.7 Independent Contractor Requirements

If this Certification Center outsources Operator duties to external contractor personnel due to insufficient human resources, this Certification Center must conduct the background check procedures described in Section 5.3.2, followed by the job-related knowledge and skill training described in Section 5.3.3. In addition to signing confidentiality agreements related to their work content, such contractor personnel must comply with relevant operational standards and legal regulations. The rights and obligations of such contractor personnel are the same as those of internal Operators of this Certification Center.

### 5.3.8 Documentation Supplied to Personnel

To ensure normal operation of the certificate management system, this Certification Center must provide relevant operational personnel with the following operational documents for system operation, including at least:

- Hardware and software platform operating documents, network system and website-related operating documents, and cryptographic system operating documents.
- Operating documents related to the certificate management system of this Certification Center.
- This Statement, certificate policy, and related operational standard documents.
- Internal operational documents for the certificate management system of this Certification Center, such as: system backup and recovery operational documents, off-site disaster backup and recovery operational documents, and routine work operational documents.

## 5.4 Audit Logging Procedures

### 5.4.1 Types of Events Recorded

Each Audit Log entry of this Certification Center, whether recorded automatically or manually, includes the following items:

- Event type.
- Date and time of the event.
- Result of event success or failure.
- Entity or person that triggered the event.
- Description of event content.

The following are the types of audit events recorded by this Certification Center:

**Security Audit**

- Any changes to important audit parameters, such as audit event types, old and new parameter contents, etc.
- Any attempts to delete or modify Audit Log files.

**Personnel and Trusted Role Management, Identification and Authentication**

- Success or failure of new role establishment.
- Changes to the maximum tolerance for authentication attempts.
- Maximum number of failed authentication attempts when users log into the system.
- Administrator unlocking of locked accounts.
- Administrator changes to the system's authentication mechanism, e.g., from password to biometrics.

**Key Operation Procedures**

- Key generation.
- Key destruction.

**Private Key Loading and Storage**

- Loading Private Keys into system components.

**Addition, Deletion, and Storage of Trusted Public Keys**

- Changes to trusted Public Keys, including addition, deletion, and storage.

**Private Key Export**

- Export of Private Keys (excluding keys intended for single use or one-time use only).

**Certificate Registration/Issuance**

- Certificate registration application process.
- Certificate issuance.

**Certificate Revocation**

- Certificate revocation application process.
- CRL generation records.

**Approval of Certificate Status Changes**

- Approval or rejection of certificate status change requests.

**Configuration Settings**

- Changes to security configuration settings.

**Account Management**

- Addition or deletion of roles and users.
- Modification of user account or role access permissions.

**Certificate Profile Management**

- Changes to certificate profiles.

**CRL Profile Management**

- Changes to CRL profiles.

**System Installation and Critical Operational Events**

- Operating system installation.
- Certificate management system installation.
- HSM installation.
- HSM removal.
- HSM destruction.
- System startup.
- Attempts to log into the certificate management system.
- Receipt of hardware and software.
- Attempts to set passwords.
- Attempts to change passwords.
- Internal data backup of this Certification Center.
- Internal data restoration of this Certification Center.
- File operations (e.g., creation, renaming, moving, etc.).
- Transmission of any information to the repository.
- Access to the internal database of this Certification Center.
- Key Compromise.
- Key renewal of this Certification Center.

**Changes to This Certification Center's Server Configuration**

- Hardware.
- Software.
- Operating system.
- Patches.
- Security profiles.

**Physical Access and Site Security**

- Personnel entry and exit from this Certification Center's server room.
- Access to this Certification Center's servers.
- Known or suspected violations of physical security regulations.

**Anomalous Events**

- Software errors.
- Software integrity check failures.
- Receipt of incorrectly formatted messages.
- Messages routed through non-standard paths.
- Network attacks (suspected or confirmed).
- Equipment failure.
- Power irregularities.
- UPS failure.
- Apparent and significant network service or access failures.
- Violations of this Statement.
- System clock resets.

### 5.4.2 Frequency of Processing Log

This Certification Center reviews Audit Logs at least once per month to investigate events that have occurred. The review includes verifying that Audit Logs have not been tampered with, examining all log entries, and inspecting any alerts or anomalies, followed by interpretation and proposal of preventive measures to avoid recurrence.

### 5.4.3 Retention Period for Audit Log

Audit Log reports and media data of this Certification Center shall be retained for at least 7 years and no earlier than 2 years after the destruction of related keys or the expiration or revocation of related certificates.

### 5.4.4 Protection of Audit Log

- Only authorized personnel may read Audit Logs, and only authorized personnel may back up Audit Logs.
- Signature or encryption technology is used to preserve current and archived electronic Audit Logs, which are stored on write-once optical discs or other media that prevent alteration of Audit Logs.
- Keys used to protect event logs shall not be used for any other purpose.
- Paper and physical Audit Logs are stored in secure locations.

### 5.4.5 Audit Log Backup Procedures

Electronic Audit Logs are backed up at least once per month and stored outside of this Certification Center, at a backup location selected in accordance with ISO or related standards.

### 5.4.6 Audit Collection System

The audit system is built into the certificate management system of this Certification Center. The audit process is activated when the certificate management system starts and is only stopped when the certificate management system is shut down.

If the automated audit system cannot function normally and the security mechanisms protecting system data integrity and confidentiality are in a high-risk state, this Certification Center will suspend certificate issuance services until the problem is resolved before resuming services.

### 5.4.7 Notification to Event-Causing Subject

When an event is recorded by the audit system, the audit system is not required to notify the entity that caused the event that their action has been recorded by the system.

### 5.4.8 Vulnerability Assessments

The following Vulnerability Assessments are conducted at least once per year:

1. Identify foreseeable internal and external threats that could result in unauthorized access, information disclosure, information misuse, data tampering, or destruction of any certificate data or certificate management processes.
2. Assess the likelihood of threats occurring and the potential damage to certificate data and certificate management processes if they occur.
3. Assess whether the currently applicable information security policies, management procedures, information technology, and other protective measures of this Certification Center are sufficient to defend against threats.

## 5.5 Records Archival

### 5.5.1 Types of Records Archived

The Archive Records of this Certification Center include the following types:

- Accreditation data.
- Certification Practice Statement.
- Subscriber agreements.
- System and equipment configuration settings.
- Contents of system or configuration setting modifications and updates.
- Certificate application data.
- Revocation application data.
- Certificate acceptance confirmation documents.
- Issued or published certificates.
- Records of own key renewal.
- Issued or published Certificate Revocation Lists.
- Audit Logs.
- Other explanatory materials or applications used to verify and corroborate archived content.
- Documents requested by independent auditors.
- Subscriber identity verification data.

### 5.5.2 Retention Period for Archive

Archive data of this Certification Center shall be retained for at least 7 years and no earlier than 2 years after the destruction of related keys or the expiration or revocation of related certificates.

### 5.5.3 Protection of Archive

Archived data shall not be written to, modified, or deleted. Individual archived data belonging to a Subscriber may be released to that Subscriber or to other organizations permitted by law.

Archive data must have one copy stored at an off-site backup location outside of this Certification Center's premises, with security control measures and damage prevention measures for storage media.

### 5.5.4 Archive Backup Procedures

Key, certificate, transaction data, and other related data are organized, archived, and backed up on a daily, weekly, and monthly basis in accordance with backup and disaster recovery procedures. One copy is stored in a secure environment within the Company, and another copy is stored at a secure off-site backup environment. When the certificate system is abnormal and cannot be started, the system backup and recovery operational manual is followed to perform certificate system recovery using the preserved backup data.

### 5.5.5 Requirements for Time-Stamping of Records

Archived electronic records (such as certificates, Certificate Revocation Lists, and Audit Logs) include date and time information, and these records are protected by appropriate digital signatures or cryptographic algorithms to detect whether the date and time information in the records has been tampered with. However, the date and time information in these electronic records is not electronic timestamp data provided by an impartial third party, but rather the date and time from the computer operating system.

All computer systems of this Certification Center undergo periodic time synchronization to ensure the accuracy and reliability of date and time information in electronic records.

Archived paper records shall also include date information and, when necessary, time information. The date and time records on paper documents shall not be arbitrarily altered; if alterations are required, they must be confirmed with the signature of an Auditor.

### 5.5.6 Archive Collection System

Archive record information related to the operations of this Certification Center is generated by internal operational personnel under resource responsibility independence and secure control measures. Audit Log collection and preservation information is also generated by internal control systems. Archive records of certificate management system operation-related documents are collected and managed by personnel with relevant business responsibilities.

### 5.5.7 Procedures to Obtain and Verify Archive Information

Access to archived data may only be obtained after formal authorization is granted through a written application. Archived data is verified by Auditors; paper documents must be verified for the authenticity of the document issuer and date, while electronic files are verified through digital signature or cryptographic methods on the archived data.

## 5.6 Key Changeover

To reduce the risk of Key Compromise for the signing keys of this Certification Center, signing keys must be renewed periodically.

When the User Certification Authority (UCA) performs key changeover, a new key pair is generated and submitted to the Root Certification Authority (RCA) for certificate issuance, then made available for relying parties to query and download in accordance with Section 6.1.4.

The key validity period for Subscribers must consider key length, protection methods, control methods, and other various factors, and must not violate the provisions of Section 6.1.5.

### 5.6.1 User Certification Authority Key Changeover

The key used by the User Certification Authority (UCA) to issue Subscriber certificates has a validity period equal to the lifecycle of the corresponding certificate, not exceeding 10 years.

When the UCA performs key changeover, a new key pair is generated and submitted to the Root Certification Authority (RCA) for certificate issuance, then made available for relying parties to query and download in accordance with Section 6.1.4.

Before the expiration of the UCA key's validity period, a new key pair may be generated to apply to the RCA for issuance of a new certificate, and the Registration Authority shall be immediately notified. After completion, Subscriber certificates are issued with the new Private Key, while the old key continues to sign CRLs until the lifecycle of that old key ends. Related operations shall follow the provisions of Section 3.3.1.

When there are security concerns about the UCA's old key and its validity period has not yet expired, the old certificate must first be revoked with the RCA before a new key pair can be generated and a new certificate issued. After completion, Subscriber certificates and CRLs are issued with the new Private Key, and Subscribers and the Registration Authority shall be immediately notified. All Subscriber certificates and CRLs previously issued using the UCA's old Private Key become invalid, and Subscribers must generate new key pairs to apply to the UCA for issuance of new certificates. Certificate revocation operations shall follow the provisions of Section 4.9.

### 5.6.2 Root Certification Authority Key Changeover

The key used by the Root Certification Authority (RCA) to issue subordinate certificates has a validity period equal to the lifecycle of the corresponding certificate, not exceeding 25 years.

Before the expiration of the RCA key's validity period, the RCA generates a new key pair and self-signed certificate, immediately publishes this new self-signed certificate, and promptly notifies subordinate Certification Authorities. The original old key continues to sign CRLs until the lifecycle of that old key ends.

When there are security concerns about an RCA key whose certificate validity period has not yet expired, the certificate must first be revoked before a new key pair and self-signed certificate can be generated. Subordinate Certification Authorities shall be immediately notified. At this point, all subordinate Certification Authority certificates become invalid, and they must generate new key pairs to apply to the RCA for issuance of new certificates.

When the RCA's Private Key is compromised, all subordinate Certification Authority certificates must be revoked, and subordinate Certification Authorities must be notified to revoke all Subscriber certificates and notify business application systems to cease using certificates issued by the subordinate Certification Authorities.

## 5.7 Compromise and Disaster Recovery

### 5.7.1 Incident and Compromise Handling Procedures

This Certification Center has established incident handling procedures and a disaster recovery plan, documented in writing as a business continuity plan and disaster recovery procedures. The contents include notification procedures for software vendors (e.g., browser vendors), Subscribers, and relying parties when disasters, security compromises, and operational interruption events occur. These procedures are reviewed or revised by this Certification Center on a regular annual basis.


### 5.7.2 Computing Resources, Software, and/or Data Are Corrupted

This Certification Center has established recovery procedures for computing resources, software, and data that have been corrupted, and conducts exercises annually.

If the computing equipment of this Certification Center is damaged or cannot operate, but the signing keys have not been damaged, the priority is to restore repository operations and rapidly rebuild certificate issuance, revocation, and management capabilities.

### 5.7.3 Entity Private Key Compromise Procedures

If the UCA key is compromised or lost (even if it has not yet been confirmed whether compromise is possible), the following procedures must be carried out:

1. All Subscribers and the RCA must be notified as soon as possible via secure email or written correspondence.
2. A new key pair shall be generated in accordance with Section 6.1 and submitted to the RCA for issuance of a new certificate.
3. All issued certificates shall be revoked. A Certificate Revocation List shall be issued using the new signing key, which includes information on all issued unexpired certificates (including previously revoked certificates issued before the Key Compromise).
4. New certificates shall be issued to each Subscriber in accordance with the procedures in Section 4.3.
5. Incident information shall be reported and disclosed to relying parties and each Root CA trust list maintenance organization.

If the RCA key is compromised or lost, the following procedures must be carried out:

1. All subordinate Certification Authorities must be notified as soon as possible via secure email or written correspondence to revoke all Subscriber certificates.
2. All issued certificates shall be revoked.
3. A new key pair and self-signed certificate shall be generated in accordance with Section 6.1.
4. New certificates shall be issued to subordinate Certification Authorities.
5. Incident information shall be reported and disclosed to relying parties and each Root CA trust list maintenance organization.

This Certification Center must investigate and report to the PMA the cause of the Key Compromise or loss, and what measures have been taken to prevent the same situation from occurring again.

If a Subscriber's key is suspected of being compromised, the procedures in Section 4.9.3 shall be followed.

### 5.7.4 Business Continuity Capabilities After a Disaster

In the event of a natural disaster or other catastrophe that prevents the restoration of certificate status services within 24 hours, the facilities at the Disaster Recovery Site shall be activated, and certificate status services shall be restored within 24 hours of activation.

## 5.8 CA Termination

When this Certification Center terminates its services, it shall comply with the relevant provisions of the Electronic Signatures Act.

When this Certification Center ceases its system operations for any reason, the impact on system operations must be minimized, and the related certificate services shall be securely transferred to another Certification Authority for continued operation.

In the case of normal business termination, contract termination, or corporate reorganization with no security concerns:

- The competent authority shall be notified 30 days prior to the date of service termination.
- The fact of service termination and the assumption of related services by another Certification Authority shall be communicated to Subscribers and published in the repository 3 months prior to the date of service termination.
- The Private Keys and certificates of the terminating Certification Center shall be transferred to the assuming Certification Authority in a secure operating environment.
- The certificate policy, Certification Practice Statement, Certification Authority related operational manuals, Subscriber agreements and registration data, Audit Logs, Archive Records, certificate status data, and other documents necessary for business assumption shall be transferred to the assuming Certification Authority.
- All Private Keys of this Certification Center shall be completely destroyed, and Subscribers shall be formally notified that certificate services have been transferred to the assuming Certification Authority for continued operation.

In the case of abnormal business termination (court-declared bankruptcy or illegality), this Certification Center must notify Subscribers of the facts as soon as possible and must carry out the normal business termination procedures to minimize the impact.

When this Certification Center ceases operations, related rights and obligations shall also be handled in accordance with the Subscriber agreement.

# 6 Technical Security Controls

## 6.1 Key Pair Generation and Installation

### 6.1.1 Key Pair Generation

Generation of key pairs for this Certification Center itself:

- A key generation script is established and followed.
- This Certification Center generates key pairs using Hardware Security Modules (HSMs) that comply with at least CNS 15135, ISO 19790, FIPS 140-2 Level 3, or FIPS 140-3 Level 3 in accordance with Section 6.2.1. After the Private Key is generated within the HSM, it remains stored therein and is not disclosed.
- The key generation process is conducted in the presence of a third-party impartial witness. The entire key generation procedure is recorded on video. After key generation, the impartial witness signs a key generation witness document to ensure public trust.

Generation of key pairs by Subscribers:

- Subscriber key pairs are generated at the direction of the Subscriber.
- If a Subscriber applies for an AATL certificate, the key storage carrier must be a hardware device, and the hardware specifications must satisfy the "Adobe Approved Trust List Technical Requirements."

### 6.1.2 Private Key Delivery to Subscriber

Subscriber Private Keys are generated by the Subscribers themselves; therefore, there is no delivery requirement.

### 6.1.3 Public Key Delivery to Certificate Issuer

The Public Key is transmitted to this Certification Center via a PKCS#10 certificate request file. The transmission method must use a securely protected channel. Proof of Private Key possession shall be verified in the manner described in Section 3.2.1.

### 6.1.4 CA Public Key Delivery to Relying Parties

This Certification Center shall publish the certificates it issues to the repository for Subscribers and relying parties to query and download.

### 6.1.5 Key Sizes

The RSA Public Key length of this Certification Center is at least 2048 bits, and the bit length must be divisible by 8. The ECC Public Key uses a curve with a security strength of at least P-256.

The RSA Public Key length for Subscribers is at least 2048 bits, and the bit length must be divisible by 8. The ECC Public Key uses a curve with a security strength of at least P-256.

### 6.1.6 Public Key Parameters Generation and Quality Checking

RSA: This Certification Center adopts the RSA algorithm. The prime number generator uses the ANSI X9.31 algorithm to generate the prime numbers required by the RSA algorithm, which ensures that the primes are strong primes. The exponent must have the following properties: an odd number greater than or equal to 3 and between 2^16+1 and 2^256-1. The modulus must have the following properties: an odd number, not a prime power, and having no factors smaller than 752.

ECC: This Certification Center uses the ECC Full Public Key Validation Routine or the ECC Partial Public Key Validation Routine to ensure the validity of all keys.

### 6.1.7 Key Usage Purposes

The certificates issued by this Certification Center to Subscribers for use in signing, encryption, or other purposes have their security control usage types specified. Subscribers must use them in accordance with this Statement and business application system specifications, as defined in the key usage field (keyUsage) of the standard extension fields of X.509 v3 certificates. Subscribers must use the certificates for their designated purposes within the relevant business systems.

In addition to signing and encryption certificate requirements, if Subscribers have certificate requirements for other purposes, this Certification Center may issue certificates with the corresponding key usage to Subscribers.

## 6.2 Private Key Protection and Cryptographic Module Engineering Controls

### 6.2.1 Cryptographic Module Standards and Controls

This Certification Center uses Hardware Security Modules (HSMs) that comply with at least CNS 15135, ISO 19790, FIPS 140-2 Level 3, or FIPS 140-3 Level 3 as protective equipment for Private Keys, with multi-person control capabilities.

In accordance with the "Adobe Approved Trust List Technical Requirements," AATL certificate Subscriber Private Keys must be generated and stored in Hardware Security Modules (HSMs) that comply with at least FIPS 140-2 Level 2, FIPS 140-3 Level 2, or an equivalent security level.

### 6.2.2 Private Key (m-of-n) Multi-person Control

The Private Key activation data of this Certification Center is managed through m-out-of-n Multi-person (m-of-n) Control, which is a Perfect Secret method of Secret Sharing that can serve as a secure Private Key activation, backup, and recovery method.

The Smart Cards and personal passwords that protect Private Key-related information are managed by different management personnel with independent duties and stored in environments with security control measures.

### 6.2.3 Private Key Escrow

The Private Keys of this Certification Center are not permitted to be escrowed, nor does it provide Private Key escrow services for Subscribers.

### 6.2.4 Private Key Backup

The Private Keys of this Certification Center are stored within HSMs. In accordance with Section 6.2.2, the Private Keys are encrypted using the Multi-person (m-of-n) Control method for backup, with the encryption key share information stored in highly secure Smart Cards.

The Smart Cards storing the encryption key share information are kept in a dual-controlled secure environment, sealed and maintained by security control personnel.

At least 2 copies of the encryption key share information shall be retained: one stored at a secure location within this Certification Center, and another stored at a secure off-site backup location.

### 6.2.5 Private Key Archival

The Private Keys of this Certification Center are not archived.

### 6.2.6 Private Key Transfer into or from a Cryptographic Module

The Private Keys of this Certification Center are generated and stored within HSMs. The Private Key may only be imported into another HSM during key backup recovery. Export from the Cryptographic Module shall be handled in accordance with Section 6.2.4.

### 6.2.7 Private Key Storage on Cryptographic Module

The Private Keys of this Certification Center are stored in encrypted form within the Cryptographic Module.

### 6.2.8 Method of Activating Private Key

The Private Key stored within the Cryptographic Module must be activated by two or more authorized Certificate Officers after identity authentication. Activation is performed by authenticating the Certificate Officers' identities through Smart Cards, and the activation procedural control measures must comply with the provisions of Section 5.2.

### 6.2.9 Method of Deactivating Private Key

After the Private Key is activated, it is deactivated by manually shutting down the Cryptographic Module after identity authentication, or by automatic logout after a specified period of inactivity, to prevent unauthorized use of the Private Key.

### 6.2.10 Method of Destroying Private Key

After the Private Key validity period expires, this Certification Center will zeroize the memory locations in the HSM where the old Private Key is stored to destroy the old Private Key within the HSM.

In addition to destroying the old Private Key within the HSM, backup copies of that old Private Key (retaining three generations) will also be physically destroyed when the backups expire. However, when it is necessary to restore from key backup copies and the restored keys include expired keys, those expired keys shall be deleted immediately.

### 6.2.11 Cryptographic Module Rating

The HSMs used by this Certification Center must comply with at least CNS 15135, ISO 19790, FIPS 140-2 Level 3, or FIPS 140-3 Level 3.

## 6.3 Other Aspects of Key Pair Management

### 6.3.1 Public Key Archival

When certificates issued by this Certification Center reach the end of their lifecycle, the certificates will be archived, and the Public Keys will be archived simultaneously.

### 6.3.2 Certificate Operational Periods and Key Pair Usage Periods

The Public Key and Private Key validity periods of this Certification Center are the same.

- The maximum key pair validity period for the Root Certification Authority (RCA) is 25 years.
- The maximum key pair validity period for the User Certification Authority (UCA) is 10 years.
- The maximum key pair validity period for Information Security Certificate and AATL Certificate Subscribers is 39 months.
- For Timestamp Certificate Subscriber key pairs, the Private Key validity period is a maximum of 15 months, and the Public Key validity period is the same as the certificate validity period, with a maximum of 135 months.

## 6.4 Activation Data

### 6.4.1 Activation Data Generation and Installation

The activation data for the signing Private Key is individually generated by multiple Smart Cards, using a Multi-person Control duty separation mechanism. The activation data in the Smart Cards is accessed by card readers, and the Smart Card's Personal Identification Number (hereinafter referred to as PIN) is used for identity authentication when accessing the activation data.

### 6.4.2 Activation Data Protection

Activation data is protected by the controlling Smart Card set. The Smart Card PIN is kept by the custodian and shall not be recorded on any media. If the number of failed login attempts exceeds 3, the Smart Card shall be locked. When a Smart Card is transferred, the new custodian must set a new PIN.

### 6.4.3 Other Aspects of Activation Data

No stipulation.

## 6.5 Computer Security Controls

### 6.5.1 Specific Computer Security Technical Requirements

This Certification Center and related auxiliary systems provide the following security control functions through the operating system, or through a combination of operating system, software, and physical protective measures:

- Identity authentication and multi-factor login capability.
- Customizable access control.
- Security audit capability.
- Access control restrictions for various certificate services and Trusted Roles.
- Identification and authentication of Trusted Roles and identities.
- Communication and database security.
- Secure and trusted channels for Trusted Roles and related identity identification.
- Process integrity and security control protection.

### 6.5.2 Computer Security Rating

The computer operating systems used by this Certification Center shall have a security rating that has passed Common Criteria (CC, ISO/IEC 15408) GPOSPP (General Purpose Operating Systems Protection Profile) certification or EAL4+ certification, or has been approved for use through internal security assessment.

## 6.6 Life Cycle Technical Controls

### 6.6.1 System Development Controls

System development for this Certification Center follows ISO 27001 standards.

The hardware and software of this Certification Center may only use components that comply with the security policy. Hardware devices, network connections, or software components unrelated to operations shall not be installed, and checks for malicious code are performed at each use.

### 6.6.2 Security Management Controls

This Certification Center operates in compliance with ISO 27001 and WebTrust for CA (AICPA/CICA) standards.

The software of this Certification Center will be verified as the correct version provided by the Developer and unmodified at the time of initial installation. After system installation, software integrity is verified at each startup.

This Certification Center shall record and control system configuration and functional changes.

### 6.6.3 Life Cycle Security Controls

This Certification Center annually reviews whether current algorithms or keys are at risk of being compromised.

## 6.7 Network Security Controls

The Root Certification Authority (RCA) certificate system is an off-line, standalone operations management system that can only be operated manually by authorized business-related operational personnel.

The certificate management system of this Certification Center may only be managed by authorized business-related operational personnel. When performing management operations, the certificate management system authenticates the identity of the operational personnel and only permits operations after successful authentication.

To prevent network intrusion and damage, this Certification Center's servers are installed and configured with firewalls, intrusion prevention systems, and antivirus systems to enhance network security. System patch updates and system vulnerability scans are performed regularly to strengthen protection. This Certification Center conducts risk assessments of identified vulnerabilities and ensures response and remediation are completed within the following timeframes:

| Vulnerability Risk Level | Review and Response Deadline | Remediation/Repair Deadline |
|---|---|---|
| High | Within 5 business days | Within 30 calendar days |
| Medium | Within 10 business days | Within 90 calendar days |

The servers and internal databases of this Certification Center are connected only to the internal network and isolated by firewalls. Only internal server connections are permitted and must undergo identity authentication to confirm that only authorized personnel or systems may access them.

The repository is connected to the Internet, providing uninterrupted certificate and CRL query services (except for necessary maintenance or backup situations).

## 6.8 Time-Stamping

This Certification Center periodically synchronizes time through a trusted time source to ensure the accuracy of time values in all operations of this Certification Center, including but not limited to the following time values:

- Certificate issuance time.
- Certificate revocation time.
- CRL issuance time.

The timestamp certificates issued by this Certification Center are provided to the Company's Time-Stamping Authority (TSA) for signing document timestamps. The timestamp protocol used by the Company's TSA satisfies the requirements of RFC 3161. The Company also prepares a Timestamp Practice Statement in accordance with RFC 3628 and publishes it in the repository.
# 7. Certificate, Certificate Revocation List, and Online Certificate Status Protocol Profiles

## 7.1 Certificate Profile

### 7.1.1 Version

The certificates of this Certification Center and the certificates issued to Subscribers are X.509 v3.

### 7.1.2 Certificate Extensions

The use of Extensions complies with the RFC 5280 standard. For detailed contents of each certificate field, please refer to the Certificate and Certificate Revocation List (CRL) Profile document of this Certification Center.


### 7.1.3 Algorithm Object Identifiers

The algorithm object identifiers used by this Certification Center when issuing certificates are as follows:

| Algorithm Type | Algorithm | Object Identifier (OID) |
|---|---|---|
| Key | rsaEncryption | {iso(1)member-body(2)us{840} rsadsi(113549)pkcs(1)pkcs-1(1)rsaEncryption(1)} |
| Key | ecPublicKey | {iso(1)member-body(2)us(840)ansi-X9-62(10045)keyType(2)ecPublicKey(1)} |
| Signature | sha256WithRSAEncryption | {iso(1)member-body(2)us{840} rsadsi(113549)pkcs(1)pkcs-1(1)sha256WithRSAEncryption(11)} |
| Signature | sha384WithRSAEncryption | {iso(1)member-body(2)us(840)rsadsi(113549)pkcs(1)pkcs-1(1)sha384WithRSAEncryption(12)} |
| Signature | ECDSAWithSHA256 | {iso(1)member-body(2)us(840)ansi-x962(10045)signatures(4)ecdsa-with-SHA2(3)ecdsa-with-SHA256(2)} |
| Signature | ECDSAWithSHA384 | {iso(1)member-body(2)us(840)ansi-x962(10045)signatures(4)ecdsa-with-SHA2(3)ecdsa-with-SHA384(3)} |

### 7.1.4 Name Forms

The certificates of this Certification Center and Subscribers use X.500 Distinguished Name (DN) naming conventions for the certificate subject and issuer names. The attribute types of these names comply with the relevant provisions of RFC 5280.

### 7.1.5 Name Constraints

Certificates issued by this Certification Center do not use the nameConstraints Extension.

### 7.1.6 Certificate Policy Object Identifier

Certificates issued by this Certification Center include the Certificate Policy Object Identifier defined by the Certificate Policy in the certificatePolicies Extension within the certificate.

### 7.1.7 Policy Constraints Extension Usage

Certificates issued by this Certification Center may include the policyConstraints Extension as needed.

### 7.1.8 Policy Qualifiers Syntax and Semantics

Certificates issued by this Certification Center may include policyQualifier syntax as needed.

### 7.1.9 Processing Semantics for the Critical Certificate Policies Extension

No stipulation.

## 7.2 CRL Profile

The service URL can be obtained from the CRL Distribution Points (cRLDistributionPoints) Extension of Subscriber certificates. The frequency at which this Certification Center issues CRLs is as specified in Section 4.9.7.

### 7.2.1 Version

This Certification Center issues Certificate Revocation Lists in X.509 v2 format.

### 7.2.2 CRL and CRL Entry Extensions

For detailed contents of each field, please refer to the Certificate and CRL Profile document of this Certification Center.

## 7.3 OCSP Profile

This Certification Center does not provide Online Certificate Status Protocol (OCSP) services for the certificate types within the scope of this Statement. Certificate status is made available through the Certificate Revocation List (CRL) described in Section 7.2.

### 7.3.1 Version

Not applicable; this Certification Center does not provide OCSP services for the certificate types within the scope of this Statement.

### 7.3.2 OCSP Extensions

Not applicable; this Certification Center does not provide OCSP services for the certificate types within the scope of this Statement.

# 8. Compliance Audit and Other Assessments

## 8.1 Frequency or Circumstances of Assessment

This Certification Center conducts at least 1 external audit per year and at least 1 internal audit every six months.

For Registration Authorities (RAs) under this Certification Center, except for external RAs that are only authorized to issue certificates for specific groups and may conduct self-audits, all other RAs must accept audits conducted by this Certification Center or by an external auditor commissioned by this Certification Center.

## 8.2 Identity and Qualifications of Assessor

Auditors performing internal and external audits for this Certification Center must possess at least the knowledge of certification authority and information system security auditing, have more than 2 years of audit-related experience or certificate operations experience, and must be familiar with the operational standards of this Statement, as well as possess knowledge and experience related to application systems operations and computer hardware/software systems. If the competent authority has relevant regulations regarding the qualification requirements for auditors, those regulations shall prevail.

When conducting external audits, the commissioned audit firm must comply with the requirements of MRSP (Mozilla Root Store Policy) and possess nationally recognized formal auditor qualifications or internationally recognized audit credentials to provide impartial and objective audit services. When this Certification Center conducts audits, it will first verify the qualifications of auditors. Upon completion of the audit, the audit report will also list the auditors' audit experience and certifications held.

## 8.3 Assessor's Relationship to Assessed Entity

Internal auditors performing audits for this Certification Center have independent roles and responsibilities separate from the audited units, with no conflicts of interest that could affect the objectivity of the audit, and they carry out assessments with an independent, impartial, and objective attitude.

External audits of this Certification Center will be conducted by a commissioned audit firm to audit the operations of this Certification Center.

## 8.4 Topics Covered by Assessment

The audit covers the following items:

- Whether the Certification Practice Statement and related operational standards have been established and published, including operational standards established in accordance with the Certification Practice Statement.
- Whether certificate management and related operations are performed in accordance with the Certification Practice Statement and related operational standards, to meet the integrity of certification services and the security control requirements of this Certification Center's environment.
- Whether the Certification Practice Statement complies with the provisions of the Certificate Policy.

The audit standards followed by this Certification Center are:

- WebTrust Principles and Criteria for Certification Authorities -- Version 2.2.2 or later.
- WebTrust Principles and Criteria for Certification Authorities -- Network Security -- Version 1.7 or later.

## 8.5 Actions Taken as a Result of Deficiency

After detailed audit and assessment of this Certification Center's operations, if any non-compliance with the Certification Practice Statement is found, the auditor shall list the deficiencies in detail according to severity level and notify this Certification Center of the audit results. This Certification Center must propose corrective and preventive measures for the deficiencies and track subsequent improvements.


## 8.6 Communication of Results

This Certification Center will publish previous WebTrust audit reports in the Repository. Additionally, the Company displays the international seals obtained on its official website; clicking the seal icon also allows viewing of the WebTrust audit reports.

## 8.7 Self-Audits

This Certification Center monitors its own compliance with the Certificate Policy and Certification Practice Statement, conducting internal audits at least once every six months to strictly control service quality.

# 9. Other Business and Legal Matters

## 9.1 Fees

### 9.1.1 Certificate Issuance or Renewal Fees

This Certification Center issues certificates to Subscribers and collects certificate fees from the Subscribers. Certificate fees are specified in the certificate application forms or published on this Certification Center's website.

### 9.1.2 Certificate Access Fees

No fee is charged.

### 9.1.3 Revocation or Status Information Access Fees

No fee is charged.

### 9.1.4 Fees for Other Services

No stipulation.

### 9.1.5 Refund Policy

If a Subscriber applies for a refund after completing the certificate application but before the certificate has been issued, a processing fee of NT$3,000 shall be deducted and the remainder shall be refunded to the Subscriber without interest. If the Subscriber applies for a refund after the certificate has been issued, the fees for the months of usage shall be deducted proportionally, and then a processing fee of NT$3,000 shall be deducted, with the remainder refunded without interest.

## 9.2 Financial Responsibility

### 9.2.1 Insurance Coverage

Regarding risk management related to certificate management operations, in addition to earthquake and fire insurance already held for buildings and hardware facilities, to diversify operational business risks, a US$2 million general liability insurance policy and a US$5 million professional liability insurance policy have been obtained.

### 9.2.2 Other Assets

This Certification Center commissions an impartial and objective third-party institution to perform annual financial operations audits related to the execution of certificate business operations.

### 9.2.3 Insurance or Warranty Coverage for End-Entities

The certification service operation items and contents provided by the Company are all specified in Section 1.4.2 of this Statement. Matters not specified in this Statement are excluded from liability for damages.

This Certification Center handles Subscriber registration data and certificate issuance operations. Unless the loss to the Subscriber is caused by failure to follow the provisions of this Statement, the Certificate Policy, and related operational standards, and is attributable to the negligence of this Certification Center, this Certification Center shall not be liable for damages.

This Certification Center shall not be liable for damages to Subscribers caused by force majeure natural disasters (such as earthquakes) or other causes not attributable to this Certification Center (such as war).

If operational personnel of this Certification Center intentionally or negligently fail to follow the provisions of this Statement, the Certificate Policy, and related operational standards in performing registration, certificate issuance and revocation operations, or violate relevant laws and regulations, causing damage to Subscribers, this Certification Center shall compensate Subscribers for damages in accordance with regulations, subject to the liability limits specified in Section 9.8.

During the period from when this Certification Center or other authorized parties submit a request to revoke a Subscriber's certificate until this Certification Center actually publishes the revocation of that Subscriber's certificate (recorded in the CRL), if legal disputes arise from the use of that Subscriber's certificate, this Certification Center shall not be liable for damages if it has processed the matter in accordance with this Statement and related operational standards.

This Certification Center shall not be liable for damages caused by the use of illegally forged or erroneous certificates by Subscribers.

The statute of limitations for a Subscriber's claim for damages shall be handled in accordance with relevant laws. The liability for damages to be borne by both parties shall be limited to the scope specified by relevant laws and regulations and the contract.

## 9.3 Confidential Information

### 9.3.1 Scope of Confidential Information

Confidential Information includes:

1. Private Keys and passwords used in the operations of this Certification Center.
2. Key share data controlling the Private Keys of this Certification Center.
3. Personal data of the representatives and agents of certificate applicants when Subscribers apply for certificates.
4. Auditable and traceable records generated or maintained by this Certification Center.
5. Audit records and documents generated by auditors during the audit process.
6. Operational documents classified as confidential.

### 9.3.2 Information Not Within the Scope of Confidential Information

The Certificate Policy, this Statement, certificates issued by this Certification Center, Certificate Revocation Lists issued by this Certification Center, and external audit results are all publicly available information.

### 9.3.3 Responsibility to Protect Confidential Information

Unless one of the following conditions is met, the basic registration data and identity verification data of Subscribers shall never be disclosed to authorized management units or any other person:

- As required by laws and regulations and authorized by the authorized management unit through legal procedures.
- When a court or arbitration institution with lawful jurisdiction is handling disputes or arbitration arising from certificates and requests are made through legal procedures.

## 9.4 Privacy of Personal Information

### 9.4.1 Privacy Plan

The Company protects Subscriber information in accordance with the "Personal Data Protection Act" and related regulations of other government agencies, and complies with the OECD privacy protection guidelines for personal data (OECD; Organization for Economic Co-operation and Development, Guidelines on the Protection of Privacy and Transborder Flows of Personal Data).

When the Certification Center or Registration Authority uses and accesses Subscriber information for certificate management operations, it must be in accordance with business needs and with strict and rigorous security controls, performed by operational personnel authorized to access the information.

When the Certification Center or Registration Authority manages and uses Subscriber information, the basic registration data and identity verification data of Subscribers shall never be publicly disclosed, sold, or leased without the Subscriber's consent.

The Company obtained the BS 10012 Personal Information Management System certificate in November 2013. In July 2018, the transition to BS 10012:2017 was completed, and the ISO/IEC 27701 Privacy Information Management System certificate was obtained on July 6, 2020; both have been maintained as valid to the present.

### 9.4.2 Information Treated as Private

- Basic registration data and identity verification data of Subscribers.
- Subscriber information used for identity verification in registration or certificate application related operations.
- Transaction-related privacy information when Subscribers register, apply for, renew, suspend, or revoke certificates.
- Subscriber information filled in on registration-related application forms and contracts, and privacy information on identification documents (or copies thereof) at the time of Subscriber registration.

### 9.4.3 Information Not Deemed Private

Subscriber certificate information published in the Repository, certificate status (when certificate validity status query functionality is provided), and Subscriber Certification Center certificate information, Certificate Revocation Lists, Certificate Policy, and Certification Practice Statement are publicly available non-confidential information.

### 9.4.4 Responsibility to Protect Private Information

Handled in accordance with relevant laws and regulations.

### 9.4.5 Notice and Consent to Use Private Information

Handled in accordance with relevant laws and regulations.

### 9.4.6 Disclosure Pursuant to Judicial or Administrative Process

In accordance with the provisions of Section 9.3.3.

### 9.4.7 Other Information Disclosure Circumstances

In accordance with the provisions of Section 9.3.3.

## 9.5 Intellectual Property Rights

The key pairs and key shares produced by this Certification Center are the Intellectual Property of the Company.

The certificates and Certificate Revocation Lists issued by this Certification Center are the Intellectual Property of the Company.

The key pairs of Subscribers are the Intellectual Property of the Subscribers; however, when the Public Key is issued as a certificate by this Certification Center, that certificate is the Intellectual Property of the Company.

This Certification Center shall ensure the accuracy of Subscriber names but does not guarantee the ownership of Intellectual Property Rights for the subject distinguished names recorded in Subscriber certificates.

The Intellectual Property Rights of related documents prepared by this Certification Center in the course of performing certificate management operations are owned by the Company.

The Intellectual Property Rights of this Statement are owned by the Company.

This Statement may be freely downloaded from the Repository of this Certification Center, or may be used reasonably in accordance with the Copyright Act after authorization by the Company.

Those who make fair use of this Statement shall not charge fees to others.

This Certification Center assumes no legal liability for any consequences arising from the improper use of this Statement.

## 9.6 Representations and Warranties

### 9.6.1 CA Representations and Warranties

- Establish, publish, and manage the Certification Practice Statement and Certificate Policy within the scope of certificate business, as well as related operational standards for certificate operations.
- Confirm the authority and responsibility relationship between this Certification Center and Registration Authorities, and ensure that Registration Authority operations must comply with this Statement, the Certificate Policy, and related standards.
- Confirm that the selection of certificate system operational personnel (including contracted outsourced personnel) and system operations comply with the Certification Practice Statement.
- Operational personnel must fulfill the responsibility of safeguarding Subscriber registration and certificate data and related information, and prevent the leakage, misuse, tampering, or unauthorized use of related information.
- In accordance with the Certification Practice Statement, accept Subscriber (Registration Authority) certificate applications, renewals, suspensions, revocations, queries, and related registration application information; confirm the accuracy and completeness of related transaction messages sent from Registration Authorities and Subscribers to this Certification Center; and perform certificate issuance operations and correctly and securely deliver related response messages to Subscribers.
- Correctly and securely deliver Subscriber and Company certificates and Certificate Revocation Lists to the Repository in accordance with certificate operational standards.
- Contracts with Subscribers or related operational documents must provide detailed descriptions of the operational standards for certificate application, renewal, suspension, revocation, registration, and use, as well as related rights and obligations.
- The Private signing key of this Certification Center shall only be used for issuing Subscriber certificates and Certificate Revocation Lists. If there is a need for message encryption or other signatures, a different and independent Private Key must be used.
- This Certification Center reviews and warrants the following:
  - Authorization for certificate application: refer to Section 3.2.2.
  - Accuracy of information: refer to Section 3.2.2.
  - No misleading information: refer to Section 3.2.2.
  - Identity of the applicant: refer to Section 3.2.2.

### 9.6.2 RA Representations and Warranties

- In accordance with this Statement, the Certificate Policy, and Registration Authority operational standards, confirm the authority and responsibility relationship between the Registration Authority and Subscribers, and verify the legality and completeness of application information when performing Subscriber registration identity verification and certificate application, renewal, suspension, and revocation related operations.
- Confirm that the selection of Registration Authority certificate system operational personnel (including contracted outsourced personnel) and system operations comply with the Certification Practice Statement and Registration Authority operational standards.
- The Registration Authority must confirm that Subscribers, at the time of registration application, fully understand and agree to the rights and obligations stated in the application form and contract, as well as the contents of the operational standards for business-related operations, and have the Subscriber sign for confirmation under personal handling (or under the personal handling of a legally authorized agent for juridical person accounts), or have the Subscriber sign for confirmation in accordance with the operational standards for the security level of identity verification at the time of Subscriber registration.
- Accept Subscriber registration, certificate application, renewal, suspension, query, and certificate revocation application operations.
- At the time of Subscriber registration, verify the legality and accuracy of the Subscriber's identity. At the time of certificate application, verify the legality and accuracy of the Subscriber's identity; upon completion, notify this Certification Center to issue the certificate to the Subscriber, and securely deliver the correct response message returned by this Certification Center to the Subscriber.
- The Registration Authority and its operational personnel must fulfill the responsibility of safeguarding Subscriber registration data and related information, and prevent the leakage, misuse, tampering, or unauthorized use of related information.
- Contracts between the Registration Authority and Subscribers or related operational documents must provide detailed descriptions of the operational standards for certificate application, renewal, suspension, revocation, query, registration, and use, as well as related rights and obligations.
- When there are concerns about the misuse, exposure, or loss of Private Keys corresponding to the Registration Authority's certificates, or when information related to the Registration Authority within the certificate has changed, the Registration Authority must immediately report and process the matter with this Certification Center that issued the certificate in accordance with relevant operational provisions.
- The Registration Authority is responsible for the rights and obligations related to Subscriber registration management operations. This Certification Center is responsible for the rights and obligations related to the certificate issuance management operations entrusted by the Registration Authority. The Registration Authority must provide information about the aforementioned authority and responsibility relationship to Subscribers and Relying Parties.

### 9.6.3 Subscriber Representations and Warranties

- When applying for registration with the Registration Authority, Subscribers must provide detailed and accurate identification documents and data.
- When applying for registration with the Registration Authority, Subscribers must fully understand and agree to the rights and obligations stated in the application form and contract, as well as the contents of the operational standards for certificate application, renewal, suspension, revocation, registration, and use, and may only sign for confirmation upon acceptance of said standards.
- Subscribers must, in accordance with the provisions of this Statement, properly and securely generate and protect their Private Keys and Private Key protection passwords, ensuring that no one other than themselves or entrusted custodians knows or uses them.
- When accepting certificates issued by the Company, Subscribers must verify the legality of the Subscriber's and this Certification Center's identity, as well as the integrity and validity of certificate information.
- Subscribers must understand and agree to the provisions of the Certification Practice Statement and related operational standards, and lawfully and correctly use Private Keys and certificates in related business systems, without violating any relevant laws or infringing upon the rights of third parties.
- When there are concerns about the misuse, exposure, or loss of Private Keys corresponding to the certificate, or when Subscriber-related information within the certificate has changed, or when the certificate is no longer in use, the Subscriber must immediately report and process the matter with the Registration Authority in accordance with relevant operational provisions.

### 9.6.4 Relying Party Representations and Warranties

- When using certificates, Relying Parties must understand and agree to the Certification Practice Statement, and the provisions regarding rights and obligations in the operational standards of the business systems used, and use the certificates in related business systems in accordance with the business scope specified in the certificate and the provisions of this Statement, without violating any relevant laws or infringing upon the rights of third parties.
- When using certificates, Relying Parties must verify the accuracy and validity of the certificate one by one through the certificate chain in accordance with the Certification Practice Statement, the operational standards of the business system, and the X.509 certificate standard, and verify whether the certificate status has been revoked through the CRL.
- When verifying the validity of transaction messages, in addition to verifying the validity and legality of Subscriber certificates, Relying Parties must verify the transaction limits, compensation limits, scope of business usage, and legal authority relationships in accordance with the Certification Practice Statement and the business system-related standards.

### 9.6.5 Representations and Warranties of Other Participants

No stipulation.

## 9.7 Disclaimers of Warranties

This Certification Center handles Subscriber registration data and certificate issuance operations. Unless the operations are performed in violation of the provisions of this Statement, or in violation of relevant laws and regulations, or are attributable to the negligence of this Certification Center, this Certification Center shall not be liable for damages.

This Certification Center shall not be liable for damages to Subscribers and Relying Parties caused by force majeure natural disasters (such as earthquakes) or other causes not attributable to this Certification Center (such as war).

This Certification Center shall be liable for damages if it fails to properly safeguard the confidential registration and certificate-related data of Subscribers, resulting in the leakage, misuse, tampering, or unauthorized use of related information, thereby causing damage to third parties.

After receiving a certificate revocation application, this Certification Center shall complete the certificate revocation operation within the time limit specified in Section 4.9.5, and upon completion, shall issue a Certificate Revocation List and publish it in the Repository at the frequency specified in Section 4.9.7. Before the Certificate Revocation List is published, Subscribers should take appropriate actions to minimize the impact on Relying Parties and shall bear all liabilities arising from the use of that certificate. For revocation operational standards, please refer to Section 4.9.

## 9.8 Limitations of Liability

When damage compensation events arise from the issuance or use of certificates for Subscribers and Relying Parties, the liability for damages to be borne by this Certification Center shall be in accordance with Section 1.4.2.

## 9.9 Indemnities

In accordance with the provisions of Section 9.2.3.

## 9.10 Term and Termination

### 9.10.1 Term

This Statement shall take effect upon publication in the Repository of this Certification Center after approval by the competent authority in accordance with the Electronic Signatures Act.

### 9.10.2 Termination

Upon approval and publication of a new version of this Statement by the competent authority, the previous version shall be terminated.

### 9.10.3 Effect of Termination and Survival

The effect of this Statement shall be maintained until the last certificate issued in accordance with this Statement expires or is revoked.

## 9.11 Individual Notices and Communications with Participants

This Certification Center shall establish communication channels with Subscribers through appropriate means, including but not limited to: telephone, fax, or Email.

## 9.12 Amendments

### 9.12.1 Procedure for Amendment

The responsible management unit for this Statement is the Policy Management Authority (PMA), which reviews this Statement at least once per year. Revision methods include revision by supplementary documents or direct revision of the contents of this Statement.

If the Certificate Policy is revised or the Object Identifier is changed, this Statement will be revised accordingly.

If changes are required due to changes in legal regulations, updates to international standards, or other factors, this Statement will also be revised accordingly.

After revisions to this Statement have been reviewed and approved by the competent authority, they will be published in the Repository in accordance with Chapter 2.

### 9.12.2 Notification Mechanism and Period

For suggestions on updating this Statement, please mail or Email the detailed suggestion documents to the contact point specified in Section 1.5.2, for review by the PMA.

After revisions to this Statement have been reviewed and approved by the competent authority, they will be published in the Repository of this Certification Center for download.

Unless otherwise specified, this Certification Center shall use the methods specified in Section 9.11 as the notification mechanism for changes with Subscribers.

### 9.12.3 Circumstances Under Which OID Must Be Changed

The Certificate Policy Object Identifier referenced in this Statement will not be changed when the contents of this Statement are modified; only the version identifier of this Statement will be incremented.

## 9.13 Dispute Resolution Provisions

If Subscribers have disputes regarding the services of this Certification Center or the use of certificates issued by it, the following provisions shall apply:

- Both parties to the dispute shall act in good faith and endeavor to resolve the dispute through negotiation by reasonable means.
- If both parties to the dispute are unable to reasonably resolve the dispute through negotiation within 30 days, they must appoint a qualified and impartial third-party mediator to conduct mediation and resolve the dispute, and both parties must agree to the mediator's negotiation and ruling.
- If both parties to the dispute are unable to agree to the mediator's negotiation and ruling within 60 days, both parties agree that the Taipei District Court shall be the court of first instance jurisdiction.
- The allocation of costs incurred during the dispute negotiation and litigation process shall be handled in accordance with the negotiation or relevant legal provisions.
- If cross-border or cross-regional disputes cannot be resolved through the above methods, they must be handled in accordance with relevant cross-border or cross-regional dispute arbitration provisions.

## 9.14 Governing Law

The contents specified in this Statement and the execution and interpretation of the related business of this Certification Center shall all be handled in accordance with the relevant laws and regulations of the competent authority, and shall comply with the relevant laws and regulations of the Republic of China.

## 9.15 Compliance with Applicable Law

This Statement and this Certification Center shall comply with the provisions of the Electronic Signatures Act and its Enforcement Rules of this country, and shall not contravene the laws and regulations of this country.


## 9.16 Miscellaneous Provisions

### 9.16.1 Entire Agreement

No stipulation.

### 9.16.2 Assignment

No stipulation.

### 9.16.3 Severability

If certain provisions of this Statement are found to be inapplicable and require revision, the other provisions shall remain valid and shall not be affected by the inapplicable provisions, until the new version of this Statement is updated and published.


Updates to this Statement shall be handled in accordance with Section 9.12.

### 9.16.4 Enforcement

No stipulation.

### 9.16.5 Force Majeure

This Certification Center shall not be liable for damages caused by force majeure natural disasters (such as earthquakes) or other causes not attributable to this Certification Center (such as war).

## 9.17 Other Provisions

No stipulation.

# Appendix I: Glossary

**(1) Internet**
A large number of different computer networks interconnected through standard communication protocols, enabling the exchange of information among them.

**(2) (Electronic) Message**
Refers to text, sound, images, symbols, or other data produced in electronic, magnetic, or other forms not directly perceivable by human senses, which are sufficient to express their intended meaning and are prepared for electronic processing.

**(3) RSA Algorithm**
An asymmetric encryption algorithm proposed by Ron Rivest, Adi Shamir, and Leonard Adleman in 1977. Its security strength is based on the difficulty of factoring large numbers into their prime factors.

**(4) Elliptic Curve Cryptography (ECC)**
A public key encryption algorithm based on elliptic curve mathematics, proposed by Neal Koblitz and Victor Miller in 1985. Its security strength is based on the difficulty of solving the elliptic curve discrete logarithm problem.

**(5) ECC P-256 Curve**
An elliptic curve standard established by NIST in FIPS 186-3, which defines the elliptic curve parameters p, a, b, G, n, h, where the x and y coordinates of the base point G of the curve are each 256 bits in length.

**(6) Electronic Signature**
Refers to data in electronic form that is attached to an electronic document and can be used to identify and confirm the identity of the signer of the electronic document. The signer produces the message using digital, voice, fingerprint, or other biometric-optical technology characteristics, and the message is attached to the electronic message, having the same effect as a handwritten signature, and can be used to identify and confirm the identity of the signer of the electronic document and to verify the integrity of the signed message.

**(7) Encrypt/Encipher**
Refers to the use of mathematical algorithms or other methods to process electronic documents in scrambled form to ensure the security of data transmission.

**(8) Decrypt/Decipher**
To restore an encrypted message that is unrecognizable by humans to a message whose meaning can be recognized by humans, using related mathematical algorithms or other methods.

**(9) Digital Signature**
A digital signature is a type of electronic signature that uses an Asymmetric Cryptosystem and a Hash Function to compress a digital message of a certain length and then encrypt it with the signer's Private Key. The corresponding Public Key can verify this encrypted digital message, forming a data message that can identify the signer's identity and the authenticity of the electronic document.

**(10) Private Key**
Refers to one of a pair of mathematically related digital data used to create and verify digital signatures, held by the signer. In addition to being used to create digital signatures, this digital data can also be used to decrypt electronic messages.

**(11) Public Key**
In asymmetric cryptographic digital signatures, refers to the publicly disclosed one of a pair of mathematically related digital data used to create and verify digital signatures. It can be used to verify the accuracy of message data signed by the signer. When performing message confidentiality functions, it can be used to encrypt transmitted messages.

**(12) (Public Key) Certificate or Electronic Certificate**
A digitally formatted record signed and issued by a Certification Authority using computers as a medium, containing the applicant's registered distinguished name, Public Key, the validity period of the Public Key, the Certification Authority's registered distinguished name and signature, and other related identification information, used to confirm the identity of the signer and to prove that they possess the matching Public Key and Private Key.

**(13) Certification Authority (CA)**
An organization that provides digital signature creation and electronic certification services, which occupies an impartial and objective position, verifies the accuracy of the identity data of certificate applicants and the relevance and legality between the applicant's Public Key and Private Key to be verified, and issues Public Key certificates accordingly.

**(14) Certification Practice Statement (CPS)**
The operational standards and application procedures published by the Certification Authority to its service targets regarding the management of certificate issuance, revocation, query, and other operations, including the Public Key infrastructure and security mechanisms for certificate operations, operational standards and procedures, security mechanisms implemented by the Certification Authority's hardware and software, authority management, and related standards.

**(15) Asymmetric Cryptosystem**
A computer-based mathematical algorithm that can generate and use a pair of mathematically related security keys. The Private Key is used to sign messages, and the corresponding Public Key is used to verify signed messages. The Public Key can also be used to encrypt messages, while the corresponding Private Key is used to decrypt encrypted messages.

**(16) Hash Function**
A mathematical algorithm that can convert a long string of bit messages into a fixed-length bit message. The same message input will always produce the same output through the compression function. It is computationally infeasible to deduce the input message from the output result.

**(17) Automated Certificate Management Environment (ACME)**
A communication protocol used to automate certificate-related management operations (such as certificate application) between the Certification Authority (CA) and its client web servers, allowing users to automate the deployment of Public Key Infrastructure at minimal cost. The protocol primarily transmits formatted JSON messages via HTTPS, with the relevant standard defined in RFC 8555.

**(18) Certificate Signing Request (CSR)**
An encoded file that allows certificate applicants to transmit the Public Key and certificate-related information (such as domain names) to the Certification Authority for certificate issuance in a standardized manner. The file can concretely prove that the applicant is the owner of the Private Key.

**(19) Issue a Certificate (Electronic Certification)**
Refers to the Certification Authority issuing a Public Key certificate or other certificate after verifying the identity and qualifications of the Public Key certificate applicant, reviewing relevant documents, and verifying the pairing relationship between the applicant's Public Key and Private Key, in accordance with the Certification Practice Statement.

**(20) Mozilla Root Store Policy (MRSP)**
A set of regulations and guidelines defined by the Mozilla organization for its Firefox web browser and other related products. The policy aims to ensure that root Certification Authorities (CAs) trusted by the Mozilla browser follow a set of standards and best practices to safeguard user security and privacy.

# Appendix II: Acronyms and Abbreviations

| Acronym | Full Name |
|---|---|
| ACME | Automated Certificate Management Environment |
| ANSI | American National Standard Institute |
| CA | Certification Authority |
| CABF | CA/Browser Forum |
| CC | Common Criteria |
| CP | Certificate Policy |
| CPS | Certification Practice Statement |
| CRL | Certificate Revocation List |
| CSR | Certificate Signing Request |
| DN | Distinguished Name |
| ECC | Elliptic Curve Cryptography |
| FIPS | Federal Information Processing Standard |
| ISO/IEC | the International Organization for Standardization, The International Electrotechnical Commission |
| ITSEC | Information Technology Security Evaluation Criteria |
| OCSP | Online Certificates Status Protocol |
| OID | Object Identifier |
| MRSP | Mozilla Root Store Policy |
| PMA | Policy Management Authority |
| PIN | Personal Identification Number |
| PKCS | Public Key Cryptography Standard |
| PKI | Public Key Infrastructure |
| RA | Registration Authority |
| RCA | Root Certification Authority |
| RSA | Rivest, Shamir, Adleman (encryption algorithm) |
| URL | Universal Resources Location |

---
