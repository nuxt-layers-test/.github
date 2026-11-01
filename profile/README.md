# Nuxt Layers — Testing & Validation

> **Independent functional, integration and security acceptance testing for the [Nuxt Layers](https://github.com/nuxt-layers) ecosystem.**

This organisation provides the infrastructure and independent consumer applications used to validate Nuxt Layers capabilities through their published contracts.

Our objective is to establish that each capability behaves correctly, securely and independently before validating its integration into the wider ecosystem.

---

## Architecture

**Nuxt Layers builds the capabilities. Nuxt Layers Tests verifies them.**# Nuxt Layers

The platform is designed as a collection of independently reusable Nuxt layers with explicit interfaces and clear separation of concerns.

Composable, reusable Nuxt layers for building secure, maintainable web applications.

---

## Application Test Template

The **[`application_test_template`](https://github.com/nuxt-layers-tests/application_test_template)** is the standard foundation for capability-testing applications.

Built with Nuxt, it provides a reusable application environment in which individual layers can be composed, exercised and evaluated as they would be in a real consuming application.

### What it provides

- **Standard application shell:** responsive layout with collapsible sidebar navigation and a dedicated workspace for capability-provided screens.
- **Consistent presentation:** integration with Theme Manager for host-controlled themes, design tokens and semantic styling.
- **Independent testing:** capability-specific scenarios, deterministic fixtures and isolated test infrastructure.
- **Functional verification:** positive and negative acceptance checks against published interfaces.
- **Security verification:** support for testing access controls, failure conditions, isolation and fail-closed behaviour.
- **Accessibility:** a common foundation targeting WCAG 2.2 AA.

### How to use it

1. Create a new repository from `application_test_template` using GitHub's **Use this template** facility.
2. Name the application for the capability under test, for example `authorisation-test`.
3. Compose the capability through its documented Nuxt entry point and public contracts.
4. Add the required host adapters, isolated infrastructure, fixtures and acceptance scenarios.
5. Expose the capability's supplied screens through the standard navigation.
6. Validate behaviour locally and through CI, recording the results and any identified defects.

Each application owns its capability-specific configuration and tests. Improvements to the shared testing foundation belong in the template.

### Why this architecture?

**A capability should be tested as a consumer experiences it, not merely as its implementation expects it to behave.**

The template deliberately separates three responsibilities:

| Responsibility | Ownership |
|---|---|
| Application shell, navigation and testing conventions | Application Test Template |
| Business behaviour, permissions and supplied screens | Capability under test |
| Theme selection and semantic design vocabulary | Theme Manager, composed by the host (`application-test` in this case) |

This separation helps detect integration defects, undocumented contract assumptions and accidental dependencies between capabilities.

Test applications consume published interfaces rather than relying on private implementation details. The template remains capability-neutral and does not reproduce the functionality being tested.

## Testing and assurance

Our development and verification process follows:

**Functional acceptance → Capability security audit → Remediation and verification → Suite integration → Suite-level security audit.**

Acceptance tests use reproducible fixtures and both positive and negative controls. Security reviews examine architecture, implementation, data handling, adversarial behaviour and public contracts.

Passing tests provide evidence for defined requirements; they do not constitute independent security certification.

### Testing principles

- **Contract-first:** consume capabilities exclusively through their published interfaces.
- **Independent verification:** test behaviour from the perspective of a consuming application.
- **Security by design:** verify fail-closed behaviour, isolation, access controls and failure conditions.
- **Positive and negative controls:** prove intended functionality as well as rejection of invalid operations.
- **Reproducibility:** use isolated environments, deterministic fixtures and documented acceptance criteria.
- **Accessibility:** target WCAG 2.2 AA for user-facing interfaces.
- **Consistent presentation:** compose Theme Manager through the host application without coupling capabilities to its implementation.

### Development and assurance

Our workflow progresses through:

**Functional acceptance → Capability security audit → Remediation and verification → Suite integration → Suite-level security audit.**

Testing evidence and audit findings inform development in the [Nuxt Layers organisation](https://github.com/nuxt-layers). Passing tests provide evidence for specific requirements; they do not constitute independent security certification.

---

## AI-driven development

Nuxt Layers and Nuxt Layers Test is an experimental, AI-driven software engineering initiative. AI assists with architecture, implementation, testing, documentation and security assessment under human direction.

The project owner retains responsibility for requirements, acceptance and governance.
---

**[Nuxt Layers](https://github.com/nuxt-layers) builds the capabilities. Nuxt Layers Tests verifies them.**

See **platform-architecture** for the architecture, conventions and governance used across the organisation.
