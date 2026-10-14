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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
