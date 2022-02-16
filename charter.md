(original source: [google doc](https://docs.google.com/document/d/1scr9uuvG1g1xpIHPs3314FqeFufE31ustTVnRMrX3gI/edit#))

## Background 

Chaos Engineering as a discipline has been around for a decade now, though its practice has been restricted to fewer (mature) organizations and teams, mostly involving experts from the Ops/SRE teams. The entry barrier for chaos engineering is usually seen to be high, helped in no small measure by its association with the philosophy of “testing in production”. The execution of chaos experiments is often done as part of “GameDays”, which is an elaborate and scientific procedure involving several stakeholders in the organization - leading to insights around application and infrastructure behavior.

## Overall goal of the working group

The goal of the working group is to help establish chaos engineering as a widely adopted practice for cloud-native application development. However, to get here, we would need to: 

- Dispel the notion of chaos engineering being reserved and applicable to only a few personae and organizations
- Lower the  barrier of entry for chaos engineering 
- Improve the safety and resilience of the cloud-native ecosystem


## How to achieve this

The working group will achieve these goals by:

- Developing educational materials and whitepaper on chaos engineering, that

  - Provides guidelines for designing, conducting, and evaluating chaos tests

  - Lists best practices around  integrating chaos engineering in application delivery workflows
    - Testing in production
    - Integrations into CD pipelines
    - Security chaos testing
    - Observability for chaos testing 

  - Showcasing use cases that go beyond simple testing scenarios
    - Chaos testing in multi-tenant systems
    - Chaos testing in hybrid cloud-native/non-cloud-native environments

- Developing tutorials on how to construct a specific scenario

  - To prevent king-making, methods to implement a fault will link to example implementations on each of the different available tools in the landscape 

- Active community outreach to support people on chaos engineering 
  - Outreach to the end-user community
  - Outreach to other CNCF projects. 


## Problem Statement 

Refer to this [document](./problem-statement.md)

## Expected Outcome of the WG

The group (which includes members from the different TAGs, chaos engineering projects as well as interested end-users) is expected to discuss the concepts, requirements and bring forth accepted and emerging patterns that address these while sharing learnings from the community/field around cloud-native chaos engineering. This would culminate in a [whitepaper](https://docs.google.com/document/d/10l262yuX_Zj8ht1pqKlSZAk4-KxY1tc-PaVmbqIsoDw/edit) that crystallizes information, provides an overview of the various tools & solutions available, and lists generic best practices/recommendations that would serve the end-users stepping into or getting a leg up in their chaos journey. 

To reiterate, WG aims to, via discussions, demonstrations & eventually the whitepaper, to aid & be of benefit to those that are new to the area of chaos engineering as well as existing practitioners who are moving to the cloud-native world. 
 
## Detailed Goals 

- Elaborate on what users/organizations in the cloud-native world mean (in terms of practices) when they have "adopted chaos engineering" ?
- A goal from a Security perspective is to ensure security resiliency is maintained at all times to protect against external threats. Hence the working group can identify standards and security controls that should be continually met by dev teams when developing services.
- Workgroup should also develop  some use cases for Security Chaos Engineering and validation that the security controls or changes to the controls happen in a rapid fashion to mitigate, thwart or contain active attack scenarios
- Identify methods to enable Kubernetes adoption via chaos engineering practice - across different personas (developers, QA, DevOps engineers, SREs) 



## Non-Goals 

- Compare chaos tools and recommend usage of specific platforms. No kingmaking
- No specific recommendations made on ecosystem tooling (ci/cd, observability, security). 


## Chairs/Sponsors
TBD

## Working Model 

The workgroup is expected to conduct user interviews and glean results from ongoing [surveys](https://docs.google.com/forms/d/1PbdSH8PEKfdpAJeVV60m2G_kCcuxpN0cjgIYQs-W5ig/edit) around chaos engineering trends and patterns

**Notes**: 
- The collaboration & interviews with end-users will be done via surveys (like the one linked in (a)) as well as, by inviting them to present their stories in the WG meetings. There might also be other ways, such as discussing reference implementations that are already in the public domain. It is expected that the members of the WG - which comprise maintainers/members of various CNCF chaos projects bring in the points-of-view of the end-users (of their respective platforms) they are already working with. 

- Some of this involves the advocacy of the workgroup and reaching out to users (SREs, developers, QA engineers)  in different channels (project slack/mailing lists)

