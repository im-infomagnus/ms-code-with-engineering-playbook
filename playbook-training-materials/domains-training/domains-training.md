---
marp: true
theme: default
paginate: true
title: "Engineering Playbook Domains Overview"
---

<style>

@import url('https://fonts.googleapis.com/css2?family=Mona+Sans:wght@400;600&display=swap');

* {
  font-family: 'Mona Sans', system-ui, sans-serif;
}



/* Slide Theme Styling */
section {
box-sizing: border-box;
  padding-top: 40px;
  padding-bottom: 40px !important;
  margin-bottom: 40px !important;
  background: 
              /* InfoMagnus logo — upper left */
              url('../images/spaceman-4.png') no-repeat top 18px left 24px / 70px auto,
              /* Light bloom — top-left corner */
              radial-gradient(ellipse at -5% 0%,   hsla(188, 85%, 65%, 0.50) 0%, transparent 45%),
              /* Light bloom — bottom-right corner */
              radial-gradient(ellipse at 105% 100%, hsla(275, 75%, 65%, 0.45) 0%, transparent 45%),
              /* Teal mid-left shimmer */
              radial-gradient(ellipse at 18% 42%,  hsla(192, 70%, 60%, 0.28) 0%, transparent 38%),
              /* Purple mid-right shimmer */
              radial-gradient(ellipse at 78% 28%,  hsla(268, 65%, 55%, 0.30) 0%, transparent 40%),
              /* Soft aqua top-right accent */
              radial-gradient(ellipse at 90% 10%,  hsla(195, 75%, 70%, 0.22) 0%, transparent 32%),
              /* Deep purple lower-left accent */
              radial-gradient(ellipse at 8%  82%,  hsla(272, 60%, 40%, 0.28) 0%, transparent 35%),
              /* Centre-left warm teal facet */
              radial-gradient(ellipse at 38% 65%,  hsla(186, 68%, 55%, 0.18) 0%, transparent 30%),
              /* Upper-centre cool violet facet */
              radial-gradient(ellipse at 60% 18%,  hsla(258, 62%, 50%, 0.20) 0%, transparent 28%),
              /* Dark base — deeper & richer */
              linear-gradient(135deg, hsl(192, 62%, 22%) 0%, hsl(255, 58%, 28%) 55%, hsl(272, 62%, 32%) 100%);
          
}

/* Title slide — large spaceman at center-right */
section.title {
  background:
    url('../images/spaceman-6.png') no-repeat center right 0px / 540px auto,
    /* Light bloom — top-left corner */
    radial-gradient(ellipse at -5% 0%,   hsla(188, 85%, 65%, 0.50) 0%, transparent 45%),
    /* Light bloom — bottom-right corner */
    radial-gradient(ellipse at 105% 100%, hsla(275, 75%, 65%, 0.45) 0%, transparent 45%),
    /* Teal mid-left shimmer */
    radial-gradient(ellipse at 18% 42%,  hsla(192, 70%, 60%, 0.28) 0%, transparent 38%),
    /* Purple mid-right shimmer */
    radial-gradient(ellipse at 78% 28%,  hsla(268, 65%, 55%, 0.30) 0%, transparent 40%),
    /* Soft aqua top-right accent */
    radial-gradient(ellipse at 90% 10%,  hsla(195, 75%, 70%, 0.22) 0%, transparent 32%),
    /* Deep purple lower-left accent */
    radial-gradient(ellipse at 8%  82%,  hsla(272, 60%, 40%, 0.28) 0%, transparent 35%),
    /* Centre-left warm teal facet */
    radial-gradient(ellipse at 38% 65%,  hsla(186, 68%, 55%, 0.18) 0%, transparent 30%),
    /* Upper-centre cool violet facet */
    radial-gradient(ellipse at 60% 18%,  hsla(258, 62%, 50%, 0.20) 0%, transparent 28%),
    /* Dark base */
    linear-gradient(135deg, hsl(192, 62%, 22%) 0%, hsl(255, 58%, 28%) 55%, hsl(272, 62%, 32%) 100%);
}



/* Global image constraints to prevent cutoff */
a {
  color: #93c5fd;
  font-weight: 600;
}


/* Global image constraints to prevent cutoff */
img {
    max-width: 90%;
    max-height: 40vh;
    object-fit: contain;
    display: block;
    margin: 10px auto;
}

/* Utility classes for specific sizing needs */
.img-small { max-height: 30vh; }
.img-medium { max-height: 50vh; }
.img-large { max-height: 70vh; }
.img-full { max-height: 80vh; max-width: 95%; }
.img-xl { max-height: 90vh; max-width: 95%; }
.img-split { max-width: 48%; display: inline-block; }
.img-center { margin: 0 auto; display: block; }

/* Scoped overrides for slides that need larger screenshots */
section.larger-images {
    text-align: center;
}

section.larger-images img {
    max-width: 95%;
    max-height: 70vh;
}

/* ── Bullet list styling ── */
ul {
    list-style: none;
    padding-left: 0.2em;
    margin: 0.2em 0;
}

ul li {
    position: relative;
    padding-left: 1.1em;
    margin-bottom: 0.25em;
}

ul li::before {
    content: '';
    position: absolute;
    left: 0;
    top: 0.42em;
    width: 0.42em;
    height: 0.42em;
    background: rgba(255, 255, 255, 0.2);
    border-radius: 2px;
    transform: rotate(45deg);
    box-shadow:
        /* top-left highlight — simulates light source */
        -1px -1px 0px rgba(255, 255, 255, 0.55),
        /* bottom-right shadow — depth */
        2px 2px 3px rgba(0, 0, 0, 0.50),
        /* outer glow — keeps the palette feel */
        0 0 7px hsla(200, 80%, 70%, 0.45);
}

/* Nested bullets — smaller, softer diamond */
ul li ul {
    margin-top: 0.1em;
    padding-left: 0.2em;
}

ul li ul li::before {
    width: 0.30em;
    height: 0.30em;
    top: 0.50em;
    background: rgba(255, 255, 255, 0.2);
    box-shadow:
        -1px -1px 0px rgba(255, 255, 255, 0.55),
        2px 2px 3px rgba(0, 0, 0, 0.50),
        0 0 7px hsla(200, 80%, 70%, 0.45);
}

/* Scoped overrides for slides with long bullet lists */
section.small-bullets ul,
section.small-bullets ol {
    font-size: 0.85em;
    line-height: 1.15;
}

/* TEXT OVERWRITES */

section {
  font-size: 2.35em;
  line-height: 1.15;
  color: white;
  border-bottom: 4px solid rgba(255, 255, 255, 0.22);
}

/* Scoped overrides for slides that need slightly smaller body text */
section.small-text {
  font-size: 2em;
  line-height: 1.15;
}

section.med-text {
  font-size: 2.35em;
  line-height: 1.15;
}

section.large-text {
  font-size: 3em;
  line-height: 1.15;
}


section.xl-text {
  font-size: 3.5em;
  line-height: 1.15;
  text-shadow: 0 3px 24px rgba(0, 0, 0, 0.40) !important;
}

/* Title slide — large spaceman at center-right */
section.title {
  background:
    url('../images/spaceman-6.png') no-repeat center right 0px / 540px auto,
    /* Light bloom — top-left corner */
    radial-gradient(ellipse at -5% 0%,   hsla(188, 85%, 65%, 0.50) 0%, transparent 45%),
    /* Light bloom — bottom-right corner */
    radial-gradient(ellipse at 105% 100%, hsla(275, 75%, 65%, 0.45) 0%, transparent 45%),
    /* Teal mid-left shimmer */
    radial-gradient(ellipse at 18% 42%,  hsla(192, 70%, 60%, 0.28) 0%, transparent 38%),
    /* Purple mid-right shimmer */
    radial-gradient(ellipse at 78% 28%,  hsla(268, 65%, 55%, 0.30) 0%, transparent 40%),
    /* Soft aqua top-right accent */
    radial-gradient(ellipse at 90% 10%,  hsla(195, 75%, 70%, 0.22) 0%, transparent 32%),
    /* Deep purple lower-left accent */
    radial-gradient(ellipse at 8%  82%,  hsla(272, 60%, 40%, 0.28) 0%, transparent 35%),
    /* Centre-left warm teal facet */
    radial-gradient(ellipse at 38% 65%,  hsla(186, 68%, 55%, 0.18) 0%, transparent 30%),
    /* Upper-centre cool violet facet */
    radial-gradient(ellipse at 60% 18%,  hsla(258, 62%, 50%, 0.20) 0%, transparent 28%),
    /* Dark base */
    linear-gradient(135deg, hsl(192, 62%, 22%) 0%, hsl(255, 58%, 28%) 55%, hsl(272, 62%, 32%) 100%);
}



/* Scoped overrides for slides with two-column lists */
section.two-columns ul,
section.two-columns ol {
    columns: 2;
    column-gap: 2em;
}

section.two-columns li {
    break-inside: avoid;
}

/* Scoped overrides for slides with dense tables */
section.compact-table table {
    font-size: 0.75em;
    line-height: 1.1;
}

section.compact-table th,
section.compact-table td {
    padding: 0.2em 0.45em;
    vertical-align: top;
}

section.compact-table th {
    text-align: left;
    background: rgba(15, 30, 60, 0.92);
    color: white;
}

section.compact-table td {
    background: rgba(245, 248, 255, 0.94);
    color: #0f1e3c;
}

/* Blockquote styling */
blockquote {
    border-left: 5px solid rgba(255, 255, 255, 0.65) !important;
    background: rgba(0, 0, 0, 0.25);
    padding: 0.85em 1em 0.85em 1.4em;
    margin: 0.8em 0;
    font-style: italic;
    color: rgba(255, 255, 255, 0.92);
    border-radius: 8px;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.22);
    backdrop-filter: blur(8px);
}

/* Text alignment utilities */
.centered { text-align: center; margin-top: -30px; font-size: 1.4em;}

/* Two-column image grid layout */

.two-columns {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 1em;
    align-items: center;
}

.two-columns img {
    max-width: 100%;
    max-height: 60vh;
    width: 100%;
    object-fit: contain;
    margin: 0;
}

/* Three-column image grid layout */

.three-columns {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 1em;
    align-items: center;
}
   
.three-columns img {
    max-width: 100%;
    max-height: 55vh;
    width: 100%;
    object-fit: contain;
    margin: 0;
}

/* Heading styles */
h1, h2, h3 {
    color: white;
    text-shadow: 0 2px 12px rgba(0, 0, 0, 0.30);
}

h1 {
    font-weight: 700;
    letter-spacing: -0.01em;
}

h2 {
    border-left: 5px solid rgba(255, 255, 255, 0.55);
    padding-left: 0.45em;
    font-weight: 600;
}

/* Dark hero variant — apply with <!-- _class: hero --> on a slide */
section.hero {
    background:
        radial-gradient(circle at 80% 15%, hsla(275, 70%, 60%, 0.40) 0%, transparent 50%),
        radial-gradient(circle at 15% 80%, hsla(195, 80%, 55%, 0.35) 0%, transparent 45%),
        radial-gradient(circle at 55% 55%, hsla(230, 60%, 40%, 0.20) 0%, transparent 40%),
        linear-gradient(135deg, hsl(215, 55%, 12%) 0%, hsl(260, 55%, 22%) 100%);
    color: white;
    border-bottom: 4px solid rgba(255, 255, 255, 0.12);
}

section.hero h1,
section.hero h2 {
    color: white;
    text-shadow: 0 4px 30px rgba(0, 0, 0, 0.50);
    border-left: none;
    padding-left: 0;
}

section.title h1,
section.title h2,
section.remove-border h2 {
    border-left: none;
    padding-left: 0;
}

section.hero a {
    color: #93c5fd;
}

/* Hanging indent for ☐ checkbox items */
section.checklist p {
    padding-left: 1.4em;
    text-indent: -1.4em;
    margin: 0.15em 0;
}


</style>



<!-- _class: xl-text title -->


# ENGINEERING PLAYBOOK:
## DOMAINS OVERVIEW

---

<!-- _class: two-columns -->

 The engineering playbook contains a substantial amount of information, guidance and resources to support engineers and other important roles that serve InfoMagnus.

**Domains included are:**

- Agile Development
- Automated Testing
- CI-CD
- Code Reviews
- Design
- Developer Experience
- Documentation
- Engineering Feedback
- GH Migration
- ML and AI Projects
- Naming Conventions
- Non-Functional Requirements
- Observability
- Sales and Project Discovery
- Security 
- Source Control
- UI/UX

---
<!-- _class: large-text -->


> This slide deck serves to introduce those domains, and detail what topics are covered within the playbook for each domain.

---
<!-- _class: xl-text -->


# AGILE DEVELOPMENT

---

<!-- _class: remove-border -->

> ## Why Agile Development
> - We want to be quick to respond to change
> - We want to get to a state of working software fast, and iterate on it to improve it
> - We want to keep the customer/end users involved all the way through
> - We care about individuals and interactions over documents and processes

---

## The Fundamentals

- We care about the goal for each activity, but not necessarily about how they are accomplished. The suggestions in parenthesis are common ways to accomplish the goals.
- We keep a shared backlog of work, that everyone in the team can always access (ex. Azure DevOps or GitHub)
- We plan our work in iterations with clear goals (ex. sprints)
- We have a clear idea of when work items are ready to implement (ex. definition of ready)
- We have a clear idea of when work items are completed (ex. definition of done)

---

- We communicate the progress in one place that everyone can access, and keep the progress up to date (ex. sprint board and daily standups)
- We reflect on our work regularly to make improvements (ex. retrospectives)
- The team has a clear idea of the roles and responsibilities in the project (ex. Dev lead, TPM, Process Lead etc.)
- The team has a joint idea of how we work together (ex. team agreement)
- We value and respect the opinions and work of all team members.


---


<!-- _class: small-text checklist-->

# THE ESSENTIALS:

☐ Process Lead (fixed/rotating) runs the daily standup

☐ The agile process is clearly defined within team.

☐ The Dev Lead (+ PO/Others) are responsible for backlog management and refinement.

☐ A working agreement is established between team members and customer.

☐ All items are tracked in GH Boards (or similar).

☐ The board is organized (swim lanes, feature tags, technology tags).

☐ Retrospectives are conducted each week/at the end of each sprint.

☐ The team identifies 1-3 proposed experiments to try each week/sprint to improve the process.

☐ Experiments have owners and are added to project backlog.

☐ The team conducts longer retrospective for Milestones and project completion.

More details on [agile development](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/agile-development/README.md) and [retrospectives](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/agile-development/ceremonies.md#retrospectives)

---
<!-- _class: two-columns -->

# CORE TOPICS COVERED

- Agile Ceremonies
- Sprint Planning
- Sprint Goal 
- Stories
- Tasks
- Time Estimation 
- Scrum Practices / Scrum Roles
- Retrospectives
- Sprint Demo
- External Feedback
- Stand-Up

---

<!-- _class: xl-text -->

# AUTOMATED TESTING

---
<!-- _class: remove-border -->

> ## Why Automated Testing
> - We want to find flaws in our software before they reach production — not after
> - We want tests to document intent, so the code is understandable without extra explanation
> - We want to save time compared to manual testing — automated tests run faster and more consistently
> - We want to safely change and refactor our code without introducing regressions

---

## The Fundamentals

- We consider code to be incomplete if it is not accompanied by tests
- We write unit tests (tests without external dependencies) that can run before every PR merge to validate that we don’t have regressions
- We write Integration tests/E2E tests that test the whole system end to end, and run them regularly
- We write our tests early and block any further code merging if tests fail.
- We run load tests/performance tests where appropriate to validate that the system performs under stress

---

<!-- _class: checklist -->

# THE ESSENTIALS:

☐ Unit tests cover the majority of all components (>90% if possible).

☐ Integration tests run to test the solution e2e.

☐ Project runs CI with automated build and test on each PR.

☐ Project uses CD to manage deployments to a replica environment before PRs are merged.

☐ Main branch is always shippable.

More details on [automated testing](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/automated-testing/README.md)

---
<!-- _class: two-columns small-text -->

# CORE TOPICS COVERED

- Technology Specific Testing
- Consumer-Driven Contract Testing (CDC)
- Why Consumer-Driven Contract Testing
- Consumer-Driven Contract Testing Design Blocks
- Consumer Tests with Provider Mock
- Contract
- Provider Contract Verification
- CDC Testing Frameworks and Tools
- E2E Testing (User Functions, Conditions, Test Cases)
- Test Metrics
- E2E Testing Frameworks and Tools (Gauge, Robot Framework, TestCraft, Ranorex Studio, Katalon Studio, BugBug.io, )
- E2E Testing Methods (Horizontal Test, Vertical Test)
- E2E Test Cases Design Guidelines
- Postman Testing
- Fault Injection Testing
- Integration Testing
- Performance Testing
- Load Testing 
- Shadow Testing / Smoke Testing
- Synthetic Monitoring Tests
- Building Containers with GH Actions and Testing
- Unit Tests
- Dependency Injection & Dependency Testing                                                    |

---
<!-- _class: xl-text -->

# CI-CD

---
<!-- _class: remove-border -->

> ## Why CI/CD
> - We want to have an automated build and deployment of our software
> - We want automated configuration of all components
> - We want to be able to quickly re-build the environment from scratch in case of disaster
> - We want the latest version of the code to always be deployed to our dev/test environments
> - We want a reliable release strategy, where the policies for release are well understood by all


---

## The Fundamentals

- We run a quality pipeline (with linting, unit tests etc.) on each PR/update of the main branch
- All cloud resources (including secrets and permissions) are provisioned through infrastructure as code templates – ex. Terraform, Bicep (ARM), Pulumi etc.
- All release candidates are deployed to a non-production environment through an automated process (ex Azure DevOps or Github pipelines)
- Releases are deployed to the production environment through an automated process
- Release rollbacks are carried out through a repeatable process
- Our release pipeline runs automated tests, validating all release candidate artifact(s) end-to-end against a non-production environment

---


<!-- _class: checklist -->

# THE ESSENTIALS 

☐ Project runs CI with automated build and test on each PR.

☐ Project uses CD to manage deployments to a replica environment before PRs are merged.

☐ Main branch is always shippable.

More details on [continuous integration](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/CI-CD/continuous-integration.md) and [continuous delivery](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/CI-CD/continuous-delivery.md)

---
<!-- _class: two-columns small-text -->


# CORE TOPICS COVERED

- DevOps / DevSecOps
- Tools
  - GH Actions
  - Azure Pipelines
  - Jenkins
  - TravisCI
  - CircleCI
  - AppVeyor
- Release Strategy
- Application Release and Environment Promotion
- Modeling Your Release Pipeline
- Azure DevOps Service Connection Security
- Azure DevOps Pipeline
- Secure Service Connection
- Pipeline Security
- Service Connection Checks
- Branch Control
- Dependency and Container Scanning
- Penetration Testing
- Secrets Management
- Credential Scanning
- Secrets Rotation
- Managed Identity
- Static Code Analysis
- GitOps
- Deployment Strategy
- CI Pipeline for Better Documentation
- Inclusive Linting
- Reusing Dev Containers Within a Pipeline
- Terraform

---

<!-- _class: xl-text -->


# CODE REVIEWS

---
<!-- _class: remove-border -->

> ## Why Code Reviews
> - We want to catch defects early, before they are introduced into shared branches
> - We want to build shared understanding of the codebase across the entire team
> - We want to learn and grow by exposing developers to new patterns, languages, and practices
> - We want to ensure code meets agreed standards and avoids common pitfalls
> - We want to spread knowledge and prevent dangerous knowledge silos on the team

---

## The Fundamentals

- Every pull request requires a peer code review before merging to the main branch
- We establish a code review SLA and add it to the team working agreement
- We keep PRs small and focused — more code makes it harder to catch bugs and do a good review
- We use automation (linters, code analyzers, unit tests) to handle style/syntax checks so reviewers can focus on logic and design
- Reviews are inclusive — we assign reviews equitably across the team and always assume positive intent from the author
- Reviewers focus on business logic correctness, readability, maintainability, and test correctness
- We enforce review policies via branch policies (minimum reviewer count, required passing builds)

---

<!-- _class: checklist -->

# THE ESSENTIALS:

☐ There is a clear agreement in the team as to function of code reviews.

☐ The team has a code review checklist or established process.

☐ A minimum number of reviewers (usually 2) for a PR merge is enforced by policy.

☐ Linters/Code Analyzers, unit tests and successful builds for PR merges are set up.

☐ There is a process to enforce a quick review turnaround.

More details on [code reviews](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/code-reviews/README.md)

---
<!-- _class: two-columns -->



# CORE TOPICS COVERED

- Inclusion in Code Review
- Culture and Code Reviews
- Dealing with the Impostor Phenomenon
- Pull Requests
- Pull Request Templates
- Testing
- Code Review Tools
- Evidence & Measures
- Measuring Code Review Process
- PR Author Guidance
- PR Reviewer Guidance


---
<!-- _class: xl-text -->
# DESIGN

---
<!-- _class: remove-border -->

> ## Why Design
> - We want to front-load design decisions before implementation begins — changes cost far less at the design stage than after code is written
> - We want to reduce technical debt by establishing a clear architecture before the team starts building
> - We want to generate useful technical artifacts (decision logs, ADRs, trade studies) that the team and customer can reference throughout the project
> - We want to involve the whole team, domain experts, and customer stakeholders early to surface the widest range of perspectives
> - We want to capture non-functional requirements (performance, security, availability, scalability) early, when they are cheapest to address

---

## The Fundamentals

- We conduct design reviews for each major component of the solution and document the outcomes, including alternatives considered
- We capture design decisions in a decision log (Architecture Decision Records) so context is preserved as the team evolves
- We document non-functional requirements early, making them specific, measurable, and testable
- We link stories and PRs to the corresponding design documents to maintain traceability
- We use technical spikes to evaluate the impact of new technology before committing to it
- We invite domain experts, SMEs, and customer engineers to participate in design reviews — sync for co-located teams, async PRs for distributed teams
- We track risks and opportunities and review them regularly throughout the engagement

---


<!-- _class: checklist -->

# THE ESSENTIALS

☐ Process for conducting design reviews is included in the [Working Agreement](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/agile-development/team-agreements/working-agreement.md).

☐ Design reviews for each major component of the solution are carried out and documented, including alternatives.

☐ Stories and/or PRs link to the design document.

☐ Each user story includes a task for design review by default, which is assigned or removed during sprint planning.

☐ Project advisors are invited to design reviews or asked to give feedback to the design decisions captured in documentation.

☐ Discover all the reviews that the customer's processes require and plan for them.

☐ Clear non-functional requirements captured (see [Non-Functional Requirements Guidance](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/design/design-patterns/non-functional-requirements-capture-guide.md))

☐ Risks and opportunities captured (see [Risk/Opportunity Management](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/agile-development/advanced-topics/backlog-management/risk-management.md))

More details on [design reviews](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/design/design-reviews/README.md)

---

<!-- _class: two-columns small-text -->

# CORE TOPICS COVERED

- Exception Handling / Exception Constructs
- Custom Exceptions / Custom Exception Hierarchy
- Error Details in API Response
- Design Patterns
- Cloud Resource Design Guidance
- Data and DataOps Fundamentals
- Isolation
- Concurrency Control
- Distributed System Design 
- Data Tiering (Data Quality)
- Data Validation
- Idempotent Data Pipelines
- Testing
- CI/CD, Source Control and Code Reviews
- Security and Configuration
- Observability

- End to End and Azure Technology Samples
- Network Architecture Guidance for Azure
- Networking and VNet Setup
- Firewall and Security
- DNS
- IP Allocation
- Resource Allocation
---
<!-- _class: two-columns small-text -->
### CORE TOPICS COVERED (cont.)

- Network Architecture Guidance for Hybrid
- Hub-and-Spoke Topology
- Non-Functional Requirements Capture
- Operational Requirements
- Performance Requirements
- Security and Compliance Requirements
- System Maintainability Requirements
- User Experience Requirements
- Object-Oriented Design Reference
- REST API Design Guidance
- Common API Design Decisions
- Creating API Contracts
- Design-First Approach
- Code-First Approach
- Design Reviews
- Design Measures
  - Cost of Change
  - Reviewer Participation
  - Time To Potential Solutions
  - Time to Decisions
- Impact
- Facilitation Guidance
- Async Design Reviews via Pull-Requests
- Technical Spike
- Design Documentation
- Design Decision Log
- ADRs
- Decision Log
- Incorporating Design Reviews into an Engagement
- Feedback Loop
- Targeted Conversations

---- 

<!-- _class: xl-text -->
# DEVELOPER EXPERIENCE (DevEx)

---
<!-- _class: remove-border -->

> ## Why Developer Experience
> - We want developers spending the majority of their time writing code — not fighting their tools, waiting on environments, or manually setting up dependencies
> - We want fast feedback loops so developers can verify changes locally before pushing to shared branches
> - We want easier onboarding — when essential tasks are automated, new team members get productive faster with less documentation to read
> - We want improved quality — when it's easy to debug and test, developers do more of it, which means fewer defects introduced
> - We want benefits that outlast the engagement — the customer continues to accrue velocity gains long after the project is delivered

---
<!-- _class: small-text checklist-->

## The Fundamentals

- We define and standardize the four essential tasks for every project: **Build**, **Test**, **Start**, and **Debug**
- We target the **F5 Contract** — a developer should be able to clone the repo, set config values, and press F5 to run the full solution end-to-end with debugging attached
- We minimize remote dependencies for local development; where remote services are unavoidable, we use emulators or DI-based mocks
- We standardize essential tasks across all solution components so they can be automated at the solution level — not repeated per component
- We keep the number of repositories minimal to reduce the multiplied overhead of branching, CI, and PR management
- We designate a **DevEx Champion** to actively seek improvements and translate friction into backlog stories
- We build for cross-platform compatibility so developers on different operating systems can all perform essential tasks without manual workarounds


--- 

# THE ESSENTIALS

Developers on the team can:

☐ Build/Compile source to verify it is free of syntax errors and compiles.

☐ Execute all automated tests (unit, e2e, etc).

☐ Start/Launch end-to-end to simulate execution in a deployed environment.

☐ Attach a debugger to started solution or running automated tests, set breakpoints, step through code, and inspect variables.

☐ Automatically install dependencies by pressing F5 (or equivalent) in their IDE.

☐ Use local dev configuration values (i.e. .env, appsettings.development.json).

More details on [developer experience](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/developer-experience/README.md)

---
<!-- _class: two-columns small-text -->

# CORE TOPICS COVERED

- DevEx Champion Actively Seek Improvements
- Make Tasks Cross Platform
- Create an Onboarding Guide
- Standardize Essential Tasks
- Solution-level Essential Tasks
- Observability
- Minimize the Number of Repositories
- Atomic Pull Requests
- Minimize Remote Dependencies for Local Development
- Use an Emulator
- Use DI + Toggle to Mock Remote Dependencies
- Separating Client Apps from the Services They Consume During Development
- Embedded Mocks
- Local Services
- Copilot / GH Copilot
- ChatGPT / Bing Chat
- Prompt Engineering
- Dev Containers
- Executing Pipelines Locally
- Fake Services Inner Dev Loop
- API
- Onboarding Guide Template

---
<!-- _class: xl-text -->

# DOCUMENTATION

---
<!-- _class: remove-border --> 

> ## Why Documentation
> - We want new team members to get productive quickly — without good onboarding docs, environment setup alone can cost days
> - We want decisions, processes, and context to be findable by the whole team, not buried in chat history or someone's head
> - We want documentation to evolve alongside the code — outdated or inaccurate docs are often worse than no docs at all
> - We want clean project handoffs — documentation is what allows a customer or new team to own the solution after the engagement ends
> - We want to reduce repeated questions and interruptions by making key information self-serve

---

## The Fundamentals

- Documentation is source-controlled alongside the code — it follows the same PR and review process as everything else
- Every repository has a README covering: setup, how to build/test/run, branch policy, and contributing guide
- We create documentation continuously throughout the project — not as an afterthought at the end
- We prefer automation over documentation where possible (Dev Containers, launch configs, scripts)
- We keep documentation accurate and current — stale docs are removed or updated as part of the same PR that changes the code
- We use a consistent, centralized structure so documentation is discoverable — a single source of truth, not scattered across wikis, chat, and email
- We document design decisions in a decision log (ADRs) so the team always knows the "why" behind key choices

---


<!-- _class: two-columns small-text -->

# CORE TOPICS COVERED

- What Documentation Should Exist
- Best Practices
- Tools
- 'Recipes'
- Resources
- Replacing Documentation with Automation
- Dev Containers in Visual Studio Code
- Launch Configurations and Tasks in Visual Studio Code
- Establishing and Managing Documentation
- Creating Good Documentation
- Code
- Implementation Comments
- Documentation Comments
- Engineering Feedback
- Projects and Repositories
- Documentation Specific to a Repository
- Common Documentation to all Repositories
- Pull Requests
- REST APIs
- Using Microsoft TypeSpec
- Agile Context
- Languages (Markdown, Mermaid)
- Wikis

---
<!-- _class: xl-text -->

# ENGINEERING FEEDBACK

---
<!-- _class: remove-border -->

> ## Why Engineering Feedback
> - We want to surface customer pain points and blockers to the product teams that can actually resolve them
> - We want feedback to drive real product improvements — not sit unread in a backlog
> - We want to capture friction while it's fresh, not scramble to reconstruct it at the end of the engagement
> - We want to give product teams enough context to understand, prioritize, and act on the issues we report
> - We want to build a pattern of continuous feedback that benefits both the current customer and future customers facing the same challenges

---

## The Fundamentals

- Engineering feedback is submitted on an **ongoing basis** throughout the engagement — not batched at the end
- Good feedback is **Goal Oriented, Specific, and Actionable** — it states what the customer was trying to accomplish, details the specific challenge, and includes enough information for a decision to be made
- Include reproduction steps, pre-requisites, and assets (scripts, logs, screenshots) so others can confirm and replay the issue
- Categorize feedback by Azure service, type (blocker, feature request, docs, etc.), stage, and priority (P0–P3)
- Link to relevant documentation, issues, or announcements when submitting — and follow up internally until the issue is addressed
- Feedback should represent the customer's perspective and business impact, not just a technical observation

---

<!-- _class: checklist -->

# THE ESSENTIALS

☐ The team submits feedback on business and technical blockers that prevent project success

☐ Suggestions for improvements are incorporated in the solution

☐ Feedback is detailed and repeatable

More details on [engineering feedback](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/engineering-feedback/README.md)

---

# CORE TOPICS COVERED

- Engineering guidance details and examples

---
<!-- _class: xl-text -->

# GITHUB MIGRATIONS FRAMEWORK

---
<!-- _class: remove-border -->

> ## Why GitHub Migration
> - We want organizations to consolidate their DevOps toolchain onto a single, modern platform that supports the full software development lifecycle
> - We want migrations to be structured and low-risk — not ad hoc efforts that break pipelines, lose history, or disrupt teams
> - We want to preserve institutional knowledge: commit history, CI/CD pipelines, security policies, and access controls all need to survive the move
> - We want teams to be productive on GitHub quickly, with proper onboarding and training as part of the migration process
> - We want migrations to align with business priorities — phased, validated, and traceable from inventory through closeout

---

## The Fundamentals

- Migrations follow a structured four-phase process:<br> **Pre-Migration → Dry Run → Production Migration → Closeout**
- We start with a full inventory of all assets: repositories, pipelines, users, permissions, policies, and integrations
- We perform a **Dry Run** first — test, validate, document findings, and refine before executing the production migration
- We use **GitHub Projects, Issues, and Actions** to manage the migration backlog, track blockers, and automate post-migration validations
- We validate CI/CD pipelines, security rules, secrets, and access controls after every migration phase — not just at the end
- We assign clear roles: Migration Lead, Technical Migration Engineers, Product Owners, and a Project Manager
- We close out every engagement with final documentation, developer onboarding, and a handoff to the operational team

---


# CORE TOPICS COVERED

- Team Cadence & Governance
- Artifacts & Templates
- Integration with GitHub Project Tools
- Migration Execution Phases

---
<!-- _class: xl-text -->


# MACHINE LEARNING <br>&<br>AI PROJECTS

---
<!-- _class: remove-border -->

> ## Why ML & AI Projects
> - We want to help customers unlock the business value of their data through principled, production-grade ML/AI solutions — not just one-off experiments
> - We want to ensure that ML work follows the same engineering rigor as software development: testing, version control, CI/CD, and code review
> - We want to reduce the risk of investing in the wrong solution by front-loading feasibility studies and data exploration before committing to a full build
> - We want ML models to reach production — not stall in notebooks — by applying MLOps practices throughout the project lifecycle
> - We want to build Responsible AI into every engagement: fairness, transparency, and accountability are not optional

---

## The Fundamentals

- Every ML project follows a structured lifecycle: **Envisioning → Feasibility Study → Model Milestone → Experimentation → Operationalization**
- We conduct a feasibility study before committing to a full solution — validating that the problem is solvable with available data
- We apply Agile methodology with adaptations for research: user stories use T-shirt sizing, and each sprint targets a concrete deliverable (model, pipeline, or documented hypothesis)
- Data scientists and software engineers share one backlog, attend the same ceremonies, and are jointly accountable for the MLOps solution
- We use engineering fundamentals throughout: version control, code reviews, automated testing, and CI/CD — even for experimental work
- We define the ML model interface (API) as early as possible so engineering integration work can proceed in parallel
- We embed Responsible AI practices into every phase: bias review, transparency, data privacy, and compliance are addressed proactively


---
<!-- _class: two-columns small-text -->


# CORE TOPICS COVERED

- Agile Development Considerations for Machine Learning/AI Projects
- Agile Process During Exploration and Experimentation
- Examples of ML Deliverables for each Sprint
- Collaboration Between Data Scientists and Software Developers
- Data Exploration
- Data Exploration Workshop
- Purpose of the Data Exploration Workshop
- Accessing Resources
- Envisioning and Problem Formulation
- Workflow
- Generic Envisioning Summary
- Responsible AI Review
- Feasibility Studies
- ML Fundamentals Checklist
- ML Model Production Checklist
- Important Questions Regarding Model Considerations
- Monitoring Drift in Data Characteristics
- Model Experimentation
- Data Quality (garbage in -\> garbage out)

--- 
<!-- _class: xl-text -->

# NAMING CONVENTIONS

---
<!-- _class: remove-border -->

> ## Why Naming Conventions
> - We want code, files, and cloud resources to be immediately understandable to anyone on the team — without needing context or explanation
> - We want to reduce cognitive load and merge conflicts caused by inconsistent or arbitrary naming choices
> - We want onboarding to be faster — consistent naming patterns mean new team members can navigate the codebase without a guide
> - We want naming to communicate intent: a good name should tell you what something is, what it does, and where it belongs
> - We want consistency across all layers of the stack — code, files, cloud resources, pipelines, schemas, and APIs should all follow predictable patterns

---

## The Fundamentals

- We use **PascalCase** for namespaces, classes, and public methods; **camelCase** for local variables and parameters; **UPPER_SNAKE_CASE** for environment variables
- File names use **hyphens or underscores** to separate words and are descriptive of their content (e.g., `user-profile.html`, `config.dev.json`)
- Cloud resources include the customer, project, environment, and region in their names (e.g., `customername-projectname-prod-westus`)
- CI/CD pipeline and job names describe their purpose clearly (e.g., `projectname-build`, `build-and-test`, `deploy-to-prod`)
- Database names include the project and environment; table names use singular PascalCase nouns (e.g., `User`, `Order`)
- API endpoints follow RESTful conventions with versioning (e.g., `/api/v1/users`); private methods use lowercase
- We follow Microsoft naming guidelines as the baseline standard and document any project-specific deviations in the team working agreement

---

<!-- _class: checklist -->

# THE ESSENTIALS

☐ The team has agreed on and documented naming conventions in the Working Agreement

☐ Code naming follows PascalCase for classes/methods and camelCase for variables/parameters

☐ File names use hyphens or underscores and are descriptive of their content

☐ Cloud resources include the customer, project, environment, and region in their names

☐ Environment variables use UPPER_SNAKE_CASE

☐ CI/CD pipeline and job names clearly describe their purpose

☐ API endpoints follow RESTful conventions with versioning (e.g., `/api/v1/resource`)

---

# CORE TOPICS COVERED

- Naming convention guidance pertaining to:
  - Code (Namespaces, Classes, Methods, Variables)
  - File Names
  - Cloud Resources
  - CI/CD Pipelines
  - Data Schemas
  - API Endpoints
  - Environment Variables

---


<!-- _class: xl-text -->


# NON-FUNCTIONAL REQUIREMENTS

---
<!-- _class: remove-border -->

> ## Why Non-Functional Requirements
> - We want to ensure that the systems we build are not just functionally correct, but also reliable, secure, performant, and maintainable in production
> - We want NFRs captured early — when they are cheapest to design for — not retrofitted after the system is built
> - We want clear, measurable criteria for qualities like availability, performance, and compliance so they can be tested and verified
> - We want to protect our customers' users through accessibility, privacy, and data integrity standards baked into every solution
> - We want to reduce long-term operational cost and risk by addressing non-functional qualities as first-class requirements, not afterthoughts

---

## The Fundamentals

- We identify and document NFRs during the design phase and attach them to specific components and user stories
- NFRs must be **specific and measurable** — "the system should be fast" is not an NFR; "p99 response time < 500ms under 1000 concurrent users" is
- We address **accessibility** from the start using inclusive design principles and automated linting tools (e.g., Accessibility Insights, axe linter)
- We define **availability** targets (uptime SLAs, RTO, RPO) and design redundancy and failover mechanisms accordingly
- We enforce **compliance** requirements (GDPR, HIPAA, etc.) through privacy-by-design, audit logging, and documented data handling practices
- We validate NFRs through load testing, security reviews, accessibility scans, and disaster recovery drills — not just at launch, but continuously
- We treat **maintainability** as an NFR: modular design, consistent naming, comprehensive documentation, and automated testing are non-negotiable



---
<!-- _class: two-columns small-text -->


# CORE TOPICS COVERED

- Inclusive Design
- Tools (Accessibility Insights)
- Practices (Accessibility Testing)
- Code and Documentation Basics
- Availability
- Capacity
- Compliance
- Data Integrity
- Disaster Recovery and Continuity
- Internationalization and Localization
- Interoperability
- Maintainability
- Performance
- Portability
- Privacy fundamentals
- Privacy and Data
- Handling Data in Engagements
- Privacy Related frameworks
- Reliability
- Autoscaling
- Load shedding & DOS Protection
- Backup Data
- Target Uptime & Failing Gracefully
- Chaos Testing
- Failure Analysis
- Scalability
- Usability

--- 

<!-- _class: xl-text -->


# OBSERVABILITY

---
<!-- _class: remove-border -->

> ## Why Observability
> - We want to know how our systems are behaving in production — before users report problems, not after
> - We want to measure application health, system performance, and business outcomes from a single, holistic view
> - We want to diagnose and resolve failures faster by having the right data — logs, metrics, and traces — already in place when something goes wrong
> - We want to build confidence in our releases by monitoring live behavior against expected baselines
> - We want to maintain compliance by ensuring sensitive data never appears in logs and that audit trails are always available

---
<!-- _class: small-text -->

## The Fundamentals

- We instrument every system with the three pillars of observability: **Logs** (discrete events), **Metrics** (health and performance signals), and **Traces** (end-to-end request flows)
- We attach a **Correlation ID** to every incoming request and propagate it through all downstream services so any transaction can be reconstructed across the stack
- We define **Service Level Objectives (SLOs)** based on user-visible impact and alert on meaningful thresholds — not internal noise
- We manage alerts, dashboards, and monitoring configuration as code (Terraform, ARM, Bicep) so observability is versioned, reviewable, and repeatable
- We never log Personally Identifiable Information (PII) — log sanitization is enforced at the component level and reviewed during code review
- We monitor dependent services (Redis, Service Bus, databases) explicitly — failures in dependencies are surfaced, not silently swallowed
- We conduct post-mortems after every significant incident and update our monitoring and alerting to detect that scenario in the future

---


<!-- _class: checklist -->

# THE ESSENTIALS

☐ Significant business and functional events are tracked and related metrics collected.

☐ Application faults and errors are logged.

☐ Health of the system is monitored.

☐ The client and server side observability data can be differentiated.

☐ Logging configuration can be modified without code changes (eg: verbose mode).

☐ [Incoming tracing context](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/tree/main/docs/observability/correlation-id.md) is propagated to allow for production issue debugging purposes.

☐ GDPR compliance is ensured regarding PII (Personally Identifiable Information).

More details on [observability](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/tree/main/docs/observability/README.md)


---

<!-- _class: two-columns -->

# CORE TOPICS COVERED

- Best Practices / Recommended Practices
- Usage Guidance
- Overviews
- Insights / Dashboards
- Tooling / Diagnostic Tooling
- Use Cases
- Telemetry
- Observability in Microservices
- Observability in Machine Learning
- Observability of CI/CD Pipelines
- Guidance for Alerting
- Correlation IDs
- Profiling

---
<!-- _class: xl-text -->


# SALES & PROJECT DISCOVERY

---
<!-- _class: remove-border -->

> ## Why Sales & Project Discovery
> - We want to ensure every engagement starts with a clear, shared understanding of the customer's goals, constraints, and definition of success — before a single line of code is written
> - We want to prevent project failures caused by misaligned scope, underestimated effort, or unresolved dependencies discovered too late
> - We want to protect our team and the customer by confirming access, funding, approvals, and readiness before the delivery team is engaged
> - We want proposals to be technically credible — grounded in real requirements and vetted estimates, not boilerplate assumptions
> - We want a clean, documented handoff from sales to delivery so the project team can start with context, not confusion

---

## The Fundamentals

- Discovery follows a five-phase lifecycle: **Lead Qualification → Discovery Session → Solution Design → Proposal & Approval → Project Handoff**
- The **Technical Lead** owns discovery — gathering requirements, assessing feasibility, and reviewing estimates before any proposal is finalized
- All findings, decisions, and estimates are documented in the **CRM-linked GitHub Issue** — not in email or informal notes
- We do not engage the delivery team until signatures, funding, and customer readiness are confirmed — partial starts waste hours and erode trust
- For GitHub-focused engagements, discovery explicitly captures: number and size of repos, pipelines, third-party integrations, and migration constraints
- Partner portal opportunities (GitHub/Microsoft) are created and tracked by the Alliance Manager in parallel with the CRM record
- Every project closes with a formal handoff: internal review, PM introduction, and a customer kick-off meeting — no silent transitions

---

<!-- _class: two-columns small-text -->


# CORE TOPICS COVERED

- Roles & Responsibilities
  - Sales Representative
  - Alliance Manager
  - Practice Director
  - Technical Lead
  - Customer Stakeholders
- Key Tasks & Steps
- Discovery Session Best Practices
- Common Discovery Pitfalls
- Handling Customer Questions
- Partner Coordination (GitHub & Microsoft)
- Resource Planning & Staffing
- Estimating & Budgeting
- CRM & Documentation Standards
- Red Flags to Watch For

--- 
<!-- _class: xl-text -->


# SECURITY

---
<!-- _class: remove-border -->

> ## Why Security
> - We want to protect our customers' users, data, and systems — security failures cause real harm and destroy trust
> - We want to catch vulnerabilities early, when they are cheap to fix, not after they have been exploited in production
> - We want every engineer on the team to understand the OWASP Top 10 and know how to prevent the most common classes of attack
> - We want security to be continuous — built into our CI/CD pipelines, code reviews, and design sessions — not a checkbox at the end
> - We want clear, documented threat models so the whole team understands the attack surface and the mitigations in place

---

<!-- _class: checklist -->

## The Fundamentals

- We follow the **OWASP Top 10** as the minimum security baseline for every web-facing application
- We practice **DevSecOps** — security scanning (SAST, dependency scanning, credential scanning) runs automatically in every CI pipeline
- We never store secrets in code — all credentials, keys, and connection strings go in a vault (Azure Key Vault, GitHub Secrets) and are rotated on a schedule
- We apply **least privilege** everywhere: access is granted on a need-to-have basis, and permissions are reviewed and tightened over time
- We perform **threat modeling** at the design stage using the STRIDE framework to identify threats before code is written
- Data is **encrypted in transit** (TLS) and **at rest** (AES-256) for all customer or confidential data
- We follow rules of engagement for security testing and never perform denial-of-service or phishing attacks against real users or live systems

--- 

# THE ESSENTIALS

☐ Access is only granted on an as-needed basis

☐ Secrets are stored in secured locations and not checked in to code

☐ Data is encrypted in transit (and if necessary at rest) and passwords are hashed

☐ Is the system split into logical segments with separation of concerns? This helps limiting security vulnerabilities.

More details on [security](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/tree/main/docs/security/README.md)

---


# CORE TOPICS COVERED

- OWASP
- Azure DevOps Security
- DevSecOps
- Recommended Tools
  - Static Application Security Testing (SAST)
  - Dynamic Application Security Testing (DAST)
  - Software Composition Analysis (SCA)
  - Container Security
  - Runtime Security
  - Binary Authorization

---
### CORE TOPICS COVERED (cont.)


- Threat Modeling Example
- Architecture & Data Flow
- Threats
  - Threat Modeling
  - Threat List
  - Threat Identification
  - Threat Visualization Model
  - Threat Properties
  - Threat Mitigation 

---
<!-- _class: xl-text -->


# SOURCE CONTROL

---
<!-- _class: remove-border -->

> ## Why Source Control
> - We want every change to the codebase to be tracked, attributed, and reversible — so we can always understand what changed, why, and by whom
> - We want to enable geo-distributed teams to collaborate asynchronously without overwriting each other's work
> - We want code quality enforced through branch protection and required pull request reviews before anything lands in the main branch
> - We want a clean, readable commit history that serves as documentation for the evolution of the codebase
> - We want secrets and credentials kept out of version control entirely — a leaked secret in commit history is a permanent vulnerability

---
<!-- _class: small-text checklist-->

## The Fundamentals

- Every project agrees on a **branch, merge, and release strategy** before writing code — documented in the Working Agreement
- The default branch is always **locked**: changes only arrive via Pull Requests with required reviewer approvals and passing builds
- We use **semantic versioning** (`major.minor.patch`) to communicate the nature of changes — breaking, additive, or patch — to consumers and dependencies
- Commit messages are **descriptive and structured** — following Conventional Commits or a team-agreed convention — so history is readable and automatable
- We **never commit secrets** — all credentials, keys, and tokens go in `.gitignore`-excluded files or a secrets vault; credential scanning runs in CI to catch any slips
- Branch names follow a consistent convention (e.g. `user/alias/feature-name`) so ownership and purpose are immediately clear
- We prefer **linear commit history** (rebase + squash) over messy merge commits to keep the log readable

--- 

# THE ESSENTIALS

☐ The default target branch is locked.

☐ Merges are done through PRs.

☐ PRs reference related work items.

☐ Commit history is consistent and commit messages are informative (what, why).

☐ Consistent branch naming conventions.

☐ Clear documentation of repository structure.

☐ Secrets are not part of the commit history or made public. (see [Credential scanning](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/blob/main/docs/CI-CD/dev-sec-ops/secrets-management/credential_scanning.md))

☐ Public repositories follow the [OSS guidelines](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/tree/main/docs/source-control/README.md#creating-a-new-repository), see `Required files in default branch for public repositories`.

More details on [source control](https://github.com/im-infomagnus/ms-code-with-engineering-playbook/tree/main/docs/source-control/README.md)

---
<!-- _class: two-columns small-text -->


# CORE TOPICS COVERED

- General Guidance
- Creating a New Repository
- Contributing to an Existing Repository
- Mixed DevOps Environments
- Component Versioning
- Challenges with Versioning in a Monorepo
- Semantic-release Configuration Examples
- Component Versioning Resources
- Git Guidance
  - Git installation
  - Git config commands
  - Cloning Repos
  - Committing Changes
  - Pushing Changes
  - Merging 
  - Merge Conflicts
  - Stashing
  - Final Steps
  - Recovering Lost Commits
  - Commit Best Practices
---
<!-- _class: small-text -->


### CORE TOPICS COVERED (cont.)

- Managing Remotes
- Working With Forks
- Updating the Remote if a Repository Changes Names
- Rolling Back Changes
- Interactive Rebase for Undoing Commits
- Using Submodules
- Working with Images, Video and Other Binary Content
- Working with Large Repositories
- Git tools
- Using Git LFS and VFS for Git
- Merge Strategies
- Squash Merge: Pros and Cons
- Naming Branches
- Working with Secrets in Source Control (including: What To Do If You Commit a Secret)


---

<!-- _class: xl-text -->

# User Interface (UI) <br> & <br> User Experience (UX)

---
<!-- _class: remove-border -->

>## Why UI/UX
>- We want the products we build to be usable, accessible, and enjoyable for the widest possible range of users — not just the average case
>- We want UI decisions to be driven by user needs and design intent, not by whatever framework a developer is most comfortable with
>- We want to front-load the design process >— desired outcomes, user personas, and trade studies — before any code is written
>- We want consistency across the application through a shared design system, so the product feels cohesive and is easy to maintain
>- We want to build securely from the start: secrets out of the frontend, XSS risks mitigated, and authentication done correctly

---
<!-- _class: small-text -->

## The Fundamentals

- Every UI project begins with four non-negotiable pillars: **Accessibility, Usability, Maintainability, and Stability** — address all four from day one
- We always define **desired outcomes** and **user personas** (including users with disabilities) before choosing a technology or starting a design
- We conduct **trade studies** to evaluate solutions — comparing frameworks, architectures, and approaches before committing
- We use **Design Ops** practices: approved designs in Figma before development begins, a shared component/design system (Fluent UI where applicable), and documented design decisions
- We use **TypeScript** for all new web projects and organize React codebases using a component-based, service-layered structure
- We never store secrets or bearer tokens in localStorage or frontend code — environment variables, `.gitignore`, and MSAL handle authentication securely
- We apply React Hooks patterns, keep dependencies evaluated for stability and security, and run `npm audit` regularly


---

# CORE TOPICS COVERED

- General Guidance
- Maintainability
- Design Process
- Design Ops
- Establishing a Web Application's Architecture
- Framework Options: Fundamentals
- Recommended Technologies
- Managing Secrets with Environmental Variables
- Common Security Pitfalls
- Incorporating Axios for REST API Calls
