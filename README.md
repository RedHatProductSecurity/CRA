# CRA Stewardship Guidelines and Templates

This repository contains guidelines and templates for open source projects for which **Red Hat, Inc.** acts as an open source software steward under the [EU Cyber Resilience Act (CRA) (Regulation 2024/2847)](https://eur-lex.europa.eu/eli/reg/2024/2847/oj/eng).

## What is the EU Cyber Resilience Act?

The EU Cyber Resilience Act establishes cybersecurity requirements for products with digital elements sold in the EU. It introduces the concept of an **Open Source Software Steward** (Article 3(14)) — an organization that provides support, oversight, or coordination for open source projects without placing those products on the market commercially.

Red Hat fulfills this steward role for a number of open source projects, accepting defined obligations around vulnerability management, security disclosures, and coordination with the broader open source community.

## Repository Contents

| Path | Description |
|------|-------------|
| `Templates/Security_MD_template.md` | Template `SECURITY.md` for CRA-stewarded projects |
| `Guidelines/eu-cra-incident-and-vulnerability-reporting-guidelines.md` | Guidelines for stewarded projects on reporting actively exploited vulnerabilities and severe incidents to Red Hat |

## Using the Templates

### `SECURITY.md`

Every CRA-stewarded project should have a `SECURITY.md` file at the root of its repository. This file tells users and researchers how to report vulnerabilities and what to expect in response.

**Steps to adopt:**

1. Copy `Templates/Security_MD_template.md` to `SECURITY.md` in your project repository.
2. Replace all `<!-- ... -->` placeholder comments with project-specific values:
   - Security contact email address
   - Response timeline
   - Link to the latest supported version
   - Link to your support matrix and vulnerability management policy
3. Remove or fill in the optional sections (GPG key, disclosure status).

The template already includes the required **EU Cyber Resilience Act — Open Source Steward Statement** identifying Red Hat as the steward and referencing the CRA regulation.

## Projects Under Red Hat CRA Stewardship

Red Hat has formally identified itself as an Open Source Software Steward for the following projects:

| Project | Repository |
|---------|------------|
| <a href="https://github.com/ansible.png"><img src="https://github.com/ansible.png?size=48" height="24" alt="Ansible"></a> Ansible | [ansible/ansible](https://github.com/ansible/ansible) |
| <a href="https://fedoraproject.org/wiki/File:Logo_fedoralogo.png"><img src="https://fedoraproject.org/w/uploads/2/2d/Logo_fedoralogo.png" height="24" alt="Fedora"></a> | [src.fedoraproject.org](https://src.fedoraproject.org) |
| <a href="https://github.com/CentOS.png"><img src="https://github.com/CentOS.png?size=48" height="24" alt="CentOS Stream"></a> CentOS Stream | [redhat/centos-stream](https://gitlab.com/redhat/centos-stream) |
| <a href="https://github.com/konflux-ci.png"><img src="https://github.com/konflux-ci.png?size=48" height="24" alt="Konflux"></a> Konflux | [konflux-ci](https://github.com/konflux-ci) |
| <a href="https://github.com/quay.png"><img src="https://github.com/quay.png?size=48" height="24" alt="Quay"></a> Quay | [quay/quay](https://github.com/quay/quay) |
| <a href="https://github.com/stackrox.png"><img src="https://github.com/stackrox.png?size=48" height="24" alt="StackRox"></a> StackRox | [stackrox/stackrox](https://github.com/stackrox/stackrox) |
| <a href="https://github.com/okd-project.png"><img src="https://github.com/okd-project.png?size=48" height="24" alt="OKD"></a> OKD | [okd-project/okd](https://github.com/okd-project/okd) |
| <a href="https://github.com/containers/crun/blob/main/docs/crun.svg"><img src="https://raw.githubusercontent.com/containers/crun/main/docs/crun.svg" height="24" alt="crun"></a> crun | [containers/crun](https://github.com/containers/crun) |
| hermeto | [hermetoproject/hermeto](https://github.com/hermetoproject/hermeto) |
| <a href="https://github.com/release-engineering.png"><img src="https://github.com/release-engineering.png?size=48" height="24" alt="IIB"></a> IIB | [release-engineering/iib](https://github.com/release-engineering/iib) |
| <a href="https://github.com/maistra.png"><img src="https://github.com/maistra.png?size=48" height="24" alt="Maistra"></a> Maistra | [maistra](https://github.com/maistra) |
| <a href="https://github.com/osbuild.png"><img src="https://github.com/osbuild.png?size=48" height="24" alt="OSbuild"></a> OSbuild | [osbuild/osbuild](https://github.com/osbuild/osbuild) |
| <a href="https://github.com/pulp.png"><img src="https://github.com/pulp.png?size=48" height="24" alt="Pulp"></a> Pulp | [pulp](https://github.com/pulp) |
| <a href="https://github.com/user-attachments/assets/1a338ecf-dc84-4495-8c70-16882955da47"><img src="https://github.com/user-attachments/assets/1a338ecf-dc84-4495-8c70-16882955da47" height="24" alt="RamaLama"></a> RamaLama | [containers/ramalama](https://github.com/containers/ramalama) |
| <a href="https://github.com/SSSD.png"><img src="https://github.com/SSSD.png?size=48" height="24" alt="sssd"></a> sssd | [SSSD/sssd](https://github.com/SSSD/sssd) |

For more details, see [Red Hat's CRA stewardship guidelines](https://access.redhat.com/security/eu-cyber-resilience-act-stewardship-guidelines).

## Contact

For questions about CRA stewardship obligations or this repository, contact Red Hat at **cra-steward@redhat.com**.
