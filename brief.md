Version: NAFATH-V4
Track: Networking

## Overview
A national service provider uses internet routes, software, and AI models that it did not create. The provider might not be aware if any of them are secretly compromised. A Software Bill of Materials lists the components that make up an application, and software teams must keep passwords and keys out of code. Log4Shell showed how thousands of systems can be exposed by a single library vulnerability. AI models can be tricked or poisoned, and mobile apps need a defined security standard so that they can be checked. Internet routes can also be taken over, which diverts traffic. All six fields ask the same question: how can we trust what we rely on?

## Software
The Twelve-Factor App says config should be kept in environment variables, not in the code. Config is anything that changes between deployments, such as database addresses and passwords for outside services. Code stays the same everywhere, so config and code should be kept apart. If secrets are written in the code, they can leak when the code is shared or made public. Environment variables are easy to change without touching the code and are rarely committed by accident.

Resource: The Twelve-Factor App - III. Config - https://12factor.net/config

## AI
NIST AI 100-2 groups attacks on machine learning by what the attacker wants: to break the service, to cause wrong results, or to steal private information. The attacks also differ in timing. Poisoning happens during training, when an attacker changes the training data or the model. Evasion happens after the model is in use, when an attacker changes an input a little so the model gives a wrong answer. Privacy attacks also happen after deployment.

Resource: NIST AI 100-2 E2025 - Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations - https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-2e2025.pdf

## Mobile
OWASP MASVS is a security standard for mobile apps. Developers use it to build secure apps, and testers use it to make their results complete and consistent. It is divided into control groups, such as storage, crypto, authentication, network, platform, code, resilience and privacy. To verify an app, a tester checks it against these controls, using the OWASP Testing Guide (MASTG) and the weakness list (MASWE) as companions.

Resource: OWASP MASVS - https://mas.owasp.org/MASVS/

## Networking
BGP trusts that a network announcing a prefix is allowed to do so. A hijacker can announce a prefix it does not own, so traffic goes to the wrong network. RPKI uses signed objects called ROAs to link a network to the address blocks it may announce. Routers can mark each route as valid, invalid or not found. However, RPKI only checks the origin of a route. It does not validate the path, so it does not stop AS-in-the-middle attacks.

Resource: RFC 6811 - BGP Prefix Origin Validation - https://www.rfc-editor.org/rfc/rfc6811

## Cybersecurity
Log4Shell (CVE-2021-44228) was a flaw in Apache Log4j2, a popular Java logging library. If an attacker could control a log message, the library could load and run code from an attacker's LDAP server. It was rated 10.0 critical because it can be attacked over the network, is easy to exploit, needs no login, and has a high impact. It was fixed by turning the feature off in version 2.15.0 and removing it in 2.16.0.

Resource: CVE-2021-44228 Detail - https://nvd.nist.gov/vuln/detail/CVE-2021-44228

## Data
A Software Bill of Materials (SBOM) is a list of the components that make up a piece of software, like the ingredients list on food. NTIA says an SBOM should have seven minimum data fields: supplier name, component name, component version, other unique identifiers, dependency relationship, author of the SBOM data, and timestamp. These fields help teams identify components and track them against vulnerability databases.

Resource: The Minimum Elements For a Software Bill of Materials (SBOM) - https://www.ntia.gov/sites/default/files/publications/sbom_minimum_elements_report_0.pdf

## Misconception in My Track
A common belief is that RPKI makes BGP fully secure. This is not correct. RPKI only helps a router check whether the network that originates a prefix is authorized to do so. It does not check the rest of the path, so it does not stop AS-in-the-middle attacks. An attacker only needs to prepend the valid origin AS to a forged route to defeat the protection. RFC 6811 says this in Section 6, "Security Considerations", and describes the protection as limited.

## Open Question
I would like to verify how many networks in my region have published ROAs, and whether BGPsec could add path validation in practice.
