(original source: [google doc](https://docs.google.com/document/d/1scr9uuvG1g1xpIHPs3314FqeFufE31ustTVnRMrX3gI/edit#))

## Background 

Chaos Engineering as a discipline has been around for a decade now, though it’s practice has been restricted to fewer (mature) organizations and teams, mostly involving experts from the Ops/SRE teams. The entry barrier for chaos engineering is usually seen to be high, helped in no small measure by its association with the philosophy of “testing in production”. The execution of chaos experiments is often done as part of “GameDays”, which is an elaborate and scientific procedure involving several stakeholders in the organization - leading to insights around application and infrastructure behaviour. 

## Overall goal of the working group

The goal of the working group is to help establish chaos engineering as a widely adopted practice for cloud-native application development. This will be achieved by:

- Defining a tool-independent methodology for chaos testing 
- How to conduct chaos tests.
- Chaos scenarios and patterns
- Evaluation of chaos test results
- Good practices for integrating chaos engineering in application delivery workflows
- Integration into continuous delivery processes
- Chaos testing in production
- Security and chaos testing
- Observability for chaos testing
- Showcasing use cases that go beyond simple testing scenarios
- Chaos testing in multi-tenant systems
- Chaos testing in hybrid cloud-native/non-cloud-native environments

## How to achieve this

The working group will achieve this goals by:

- Developing educational materials and whitepapers on chaos engineering
- Guidelines for designing, conducting and evaluating chaos tests. 
- Active community outreach to support people on chaos engineering 
  - Outreach to the end user community
  - Outreach to other CNCF projects. 

## Problem Statement 

With the advent of the cloud native paradigm, especially the adoption of Kubernetes and in its wake the migration of services  from “legacy” hosting platforms to Kubernetes (bringing along with it the re-architecture of applications to a microservices & containerized model) has made chaos engineering both more “ubiquitous” and “democratic”. By this, it is meant that organizations are looking at chaos engineering as a way to increase confidence in the new deployment models and testing out (as well as learning about) service behaviour much before going to production, leading to its usage in development/staging (non-prod) environments (ubiquitous) as also in the persona that makes use of it: Application Developers, QA Engineers, Build & Release Engineers etc., While chaos on production systems is still the goal of these new adopters/practitioners of chaos and is seen as the nirvana of a mature chaos engineering practice, it is attempted only after reasonably high reliability is displayed.  

The current scenario has spawned off a slew of requirements as well as patterns to address these (around how chaos is practiced and its artifacts are “consumed”), that have been espoused by the chaos engineering projects and toolsets in the CNCF. 

There is a need to educate and also learn from the community (comprising the cloud native projects/vendors and importantly, the end users) on how these requirements are being tackled, what the most well-accepted patterns (based on surveys/usage reports or reference implementations) are, what are the outstanding issues and review possible/upcoming solutions that resolve these challenges. It is also necessary to revisit the principles of chaos and place it in perspective based on the current context. 


Some of these areas/requirements/questions (by no means exhaustive) are listed here: 

- Kubernetes is both a development platform as it is one for deployment. The cloud native developers or SREs today are accustomed to dealing with declarative models viz. their application and infrastructure intent. How does chaos fit into this model? 

- What/How are boundaries defined between standard system testing v/s chaos engineering in a cloud-native application delivery process. Can this be philosophically reconciled? 

- How does chaos engineering play a part in the world of daily releases and patches to production, driven as it is by CI/CD and GitOps flows. 

- “Automated chaos tests”, their general structure and striking a balance between exploratory experimentation and automated chaos in CI/CD or as a background service. 

- Steady-State hypothesis & the role of SLOs and its evaluation/validation as aided by chaos experimentation. Declarative intent for SLOs. 

- Observability requirements for cloud native chaos engineering. Generation as well as consumption of observability “data” within chaos experiments. 

- Chaos Engineering in a Multi-tenant world. Security considerations and security chaos experiments as a sub-category. 

- Chaos engineering methodologies for a hybrid environment comprising services on Kubernetes as well as non-Kubernetes infrastructure. 


## Expected Outcome of the WG

The group (which includes members from the different TAGs, chaos engineering projects as well as interested end-users) is expected to discuss the concepts, requirements and bring forth accepted and emerging patterns that address these, while sharing learnings from the community/field around cloud native chaos engineering. This would culminate in a whitepaper that crystallizes information, provides an overview of the various tools & solutions available and lists generic best practices/recommendations that would serve the end users stepping into or getting a leg up in their chaos journey. 

To reiterate, WG aims to, via discussions, demonstrations & eventually the whitepaper, to aid & be of benefit to those that are new to the area of chaos engineering as well as existing practitioners who are moving to the cloud-native world. 


## Detailed Goals 

- Elaborate on what users/organizations in the cloud native world mean (in terms of practices) when they have "adopted chaos engineering" ?
- Goal from a Security perspective is to ensure security resiliency is maintained at all times to protect against external threats. Hence the working group can identify standards and security controls which should be continually met by dev teams when developing services. (TBD)
- Identify methods to enable Kubernetes adoption via chaos engineering practice - across different personas (developers, QA, DevOps engineers, SREs) 


## Non-Goals 

- Compare chaos tools and recommend usage of specific platforms. No kingmaking
- No specific recommendations made on ecosystem tooling (ci/cd, observability, security). 


## Chairs/Sponsors
TBD

## Working Model 

Workgroup is expected to conduct user interviews and surveys/glean results from surveys around chaos engineering trends and patterns

**Notes**: 
- The collaboration & interviews with end users will be done via surveys, as well as, by inviting them to present their stories in the WG meetings. There might also be other ways, such as discussing reference implementations that are already in the public domain. It is expected that the members of the WG - which comprise maintainers/members of various CNCF chaos projects bring in the points-of-view of the end-users (of their respective platforms) they are already working with. 

- Some of this involves advocacy of the work group and reaching out to users (SREs, developers, QA engineers) in different channels (project slack/mailing lists)

