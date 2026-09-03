# Frequently Asked Questions — EU CRA and Stewarded Open Source Projects

This FAQ covers questions relevant to open source projects under stewardship in the context of the [EU Cyber Resilience Act (CRA)](https://eur-lex.europa.eu/eli/reg/2024/2847/oj/eng). It focuses on the stewardship model and practical obligations for project maintainers.

For Red Hat's official guidelines on stewarded open source projects under the CRA, see the [Red Hat EU CRA Stewardship Guidelines](https://access.redhat.com/security/eu-cyber-resilience-act-stewardship-guidelines).

For questions about the ENISA Single Reporting Platform (SRP), including how the platform works, registration, data fields, reporting workflows, and CSIRT responsibilities, see the [ENISA SRP FAQ](https://www.enisa.europa.eu/topics/product-security/single-reporting-platform-srp/frequently-asked-questions).

---

## General

<details>
<summary>1. What is an Open Source Software Steward?</summary>
  
> An Open Source Software Steward is defined in Article 3(14) of the CRA as a legal person — other than a manufacturer — that has the purpose or objective of systematically providing support on a sustained basis for the development of products with digital elements that are free and open source software, and that are intended for commercial activities. The steward ensures that the projects it oversees meet the CRA's cybersecurity and reporting requirements without placing those products on the market commercially itself.

</details>

<details>
<summary>2. How does stewardship differ from being a manufacturer under the CRA?</summary>

> A manufacturer places a product with digital elements on the EU market and bears full conformity obligations (CE marking, essential cybersecurity requirements, conformity assessment). A steward, by contrast, does not place the product on the market but supports the open source project behind it. Steward obligations are lighter and focused on facilitating security processes, vulnerability handling coordination, and cooperation with market surveillance authorities — not on product certification.

</details>

<details>
<summary>3. Does CRA stewardship change the project's governance or license?</summary>

> No. Stewardship under the CRA is about cybersecurity obligations and regulatory coordination. It does not alter the project's open source license, decision-making governance, or community structure. The project retains its existing maintainership model.

</details>

<details>
<summary>4. What obligations does a steward have under the CRA?</summary>

> Under Article 24 of the CRA, a steward shall:
>
> - Put in place and document a cybersecurity policy to foster the development of a secure product and effective handling of vulnerabilities by the developers of that product.
> - Cooperate with market surveillance authorities regarding mitigating cybersecurity risks posed by the product.
> - Report actively exploited vulnerabilities and severe incidents in accordance with Article 14.
> - Provide the aforementioned documentation to market surveillance authorities upon request.
>
> Stewards are not required to perform conformity assessments or apply CE marking — those obligations apply to manufacturers.

</details>

<details>
<summary>5. Why does a project need to be stewarded?</summary>

> An open source project falls under stewardship when a legal entity — such as a company or foundation — systematically provides sustained support for its development, and the resulting software is intended for commercial activities. This support can take many forms: direct funding, employing developers who contribute to the project, providing infrastructure (build systems, CI/CD, hosting), or coordinating the development effort.
>
> The key trigger is the combination of **systematic, sustained support** and **commercial intent**. If a manufacturer (or another organization) invests in an open source project that is then integrated into products placed on the EU market, the CRA recognizes that the supporting organization bears a degree of responsibility for the project's cybersecurity posture — even if the organization does not place the product on the market itself.
>
> In practice, many open source projects that form the foundation of commercial products are developed with significant backing from companies that ship those products downstream. The stewardship model ensures that these projects benefit from coordinated vulnerability handling and incident reporting without burdening individual volunteer contributors with regulatory obligations.

</details>

<details>
<summary>6. When does the CRA start applying?</summary>

> The CRA entered into force on 10 December 2024. Most obligations apply from **11 December 2027**, including essential cybersecurity requirements and conformity assessment. However, reporting obligations for actively exploited vulnerabilities and severe incidents apply earlier, from **11 September 2026**.
>
> **Note:** There is no retroactive reporting obligation. Manufacturers and stewards are not required to report actively exploited vulnerabilities they were already aware of before 11 September 2026. The obligation applies only where active exploitation is newly discovered, or the manufacturer/steward newly becomes aware of it, on or after that date. (See Commission guidance C(2026) 5252 final, point 217.)

</details>

---

## Obligations for Stewarded Projects

<details>
<summary>7. What do I need to do as a maintainer of a stewarded project?</summary>

> At minimum:
>
> 1. **Adopt a SECURITY.md** in your repository using the [provided template](Templates/Security_MD_template.md), so vulnerability reporters and users know how to reach you.
> 2. **Establish or document a vulnerability handling process** — how your project receives, triages, fixes, and discloses security issues.
> 3. **Report actively exploited vulnerabilities (AEVs) and severe incidents** to your steward, following the [reporting guidelines](Guidelines/eu-cra-incident-and-vulnerability-reporting-guidelines.md). The steward (Red Hat) is responsible for submitting the report to the SRP.

</details>

<details>
<summary>8. Do I have to report every CVE to the SRP?</summary>

> No. Only **actively exploited vulnerabilities** and **severe incidents** require mandatory reporting. A CVE that exists in your code but is not being actively exploited in the wild is not reportable under the CRA. Similarly, a vulnerability appearing in public catalogues (e.g., CISA KEV or ENISA EUVD) does not by itself trigger a reporting obligation — there must be reliable evidence of actual malicious exploitation.

</details>

<details>
<summary>9. What counts as a "severe incident" for a stewarded project?</summary>

> An incident is a real event that has actually occurred — not a theoretical weakness. For it to be severe under Article 14(5), it must either:
>
> - **(a)** Negatively affect or be capable of negatively affecting the product's ability to protect the availability, authenticity, integrity, or confidentiality of sensitive or important data or functions; **or**
> - **(b)** Have led or be capable of leading to the introduction or execution of malicious code in the product or in users' network and information systems.
>
> Example: an attacker successfully injecting malicious code into a project's release pipeline would qualify.

</details>

<details>
<summary>10. What if I am not sure whether something is reportable?</summary>

> Contact the steward. For Red Hat stewarded projects, email [secalert@redhat.com](mailto:secalert@redhat.com). Red Hat will analyze the situation and advise whether it meets the CRA reporting threshold. Given the tight deadlines (24-hour early warning), early engagement is always better than a late report.

</details>

<details>
<summary>11. Who reports to the SRP?</summary>

> Under the CRA, the legal obligation to report actively exploited vulnerabilities and severe incidents to the SRP lies with the **steward** (Red Hat), not with the open source project. Project maintainers are neither manufacturers nor stewards under the CRA and do not bear a direct reporting obligation. You perform an initial analysis, send the details to [secalert@redhat.com](mailto:secalert@redhat.com), and Red Hat handles the submission to the SRP and manages the follow-up notification stages. See the [reporting guidelines](Guidelines/eu-cra-incident-and-vulnerability-reporting-guidelines.md#how-to-report) for full details. (See Commission guidance C(2026) 5252 final, points 79–82.)

</details>

---

## Scope and Applicability

<details>
<summary>13. Does the CRA apply to all open source software?</summary>

> No. The CRA explicitly excludes free and open source software that is developed or supplied outside the course of a commercial activity (Recital 18). The regulation targets products with digital elements placed on the EU market. Open source software that is not monetized and not integrated into commercial products is generally outside scope.

</details>

<details>
<summary>14. If my project is stewarded, does that mean it is "in scope" of the CRA?</summary>

> Stewardship means the steward has accepted certain obligations regarding the project's cybersecurity posture and reporting. The project itself is not treated as a commercial product placed on the market by the steward. However, downstream manufacturers who integrate the project into their commercial products bear full CRA obligations for those products.

</details>

<details>
<summary>15. I am a contributor, not a maintainer. Do I have CRA obligations?</summary>

> The CRA does not impose obligations on individual open source developers or contributors who are not acting in a commercial capacity. Obligations fall on manufacturers (who place products on the EU market) and stewards (organizations systematically supporting open source projects intended for commercial activities). As an individual contributor, you are not liable under the CRA for your contributions.

</details>

<details>
<summary>16. Does the CRA apply to internal or non-EU deployments of the project?</summary>

> The CRA applies to products with digital elements placed on the EU market. If the software is used purely internally within an organization and not made available on the EU market, or if it is only deployed outside the EU, the CRA obligations for that specific use do not apply. However, stewardship obligations exist regardless, as the steward role relates to the project itself, not individual deployments.

</details>

---

## SECURITY.md and Vulnerability Handling

<details>
<summary>17. Why does my project need a SECURITY.md?</summary>

> A SECURITY.md file tells vulnerability reporters and users how to responsibly disclose security issues to your project. It is part of establishing a documented cybersecurity policy, which the CRA requires stewards to put in place and document. It also includes the CRA steward statement identifying your steward, meeting transparency requirements.

</details>

<details>
<summary>18. What should the SECURITY.md contain?</summary>

> Use the [provided template](Templates/Security_MD_template.md). Key sections include:
>
> - How to report vulnerabilities (contact email, GPG key if applicable)
> - Expected response timeline
> - Supported versions and security update policy
> - The EU CRA Open Source Steward statement

</details>

<details>
<summary>19. Do I need a separate vulnerability management policy beyond SECURITY.md?</summary>

> SECURITY.md is the public-facing disclosure document. Your project should also have internal processes for triaging, fixing, and disclosing vulnerabilities. This can be documented as part of your project's existing contribution or governance documents. See the [Red Hat stewardship guidelines](https://access.redhat.com/security/eu-cyber-resilience-act-stewardship-guidelines) for recommendations.

</details>

---

## Contact

- **Reporting actively exploited vulnerabilities or severe incidents**: [secalert@redhat.com](mailto:secalert@redhat.com)
- **General CRA stewardship questions**: [cra-steward@redhat.com](mailto:cra-steward@redhat.com)
