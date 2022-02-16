The advent of the cloud-native paradigm, especially the adoption of Kubernetes and in its wake the migration of services from “legacy” hosting platforms to Kubernetes (bringing along with it the re-architecture of applications to a microservices & containerized model) has made chaos engineering both more “ubiquitous” and “democratic”. By this, it is meant that organizations are looking at chaos engineering as a way to increase confidence in the new deployment models and testing out (as well as learning about) service behavior much before going to production, leading to its usage in development/staging (non-prod) environments (ubiquitous) as also in the persona that makes use of it: Application Developers, QA Engineers, Build & Release Engineers, etc., While chaos on production systems is still the goal of these new adopters/practitioners of chaos and is seen as the nirvana of a mature chaos engineering practice, it is attempted only after reasonably high reliability is displayed.  

The current scenario has spawned off a slew of requirements as well as patterns to address these (around how chaos is practiced and its artifacts are “consumed”), that have been espoused by the chaos engineering projects and toolsets in the CNCF. 

There is a need to educate and also learn from the community (comprising the cloud-native projects/vendors and importantly, the end-users) on how these requirements are being tackled, what the most well-accepted patterns (based on surveys/usage reports or reference implementations) are, what are the outstanding issues and review possible/upcoming solutions that resolve these challenges. It is also necessary to revisit the principles of chaos and place them in perspective based on the current context. 

Some of these areas/requirements/questions (by no means exhaustive) are listed here: 

- Kubernetes is both a development platform as it is one for deployment. The cloud-native developers or SREs today are accustomed to dealing with declarative models viz. their application and infrastructure intent. How does chaos fit into this model? 

- How to reduce the risk of user impacting incidents caused by chaos engineering practices (both real and perceived risk). 

- What/How are boundaries defined between standard system testing v/s chaos engineering in a cloud-native application delivery process. Can this be philosophically reconciled? 

- How does chaos engineering play a part in the world of daily releases and patches to production, driven as it is by CI/CD, GitOps flows as well as Operators model? 

- “Automated chaos tests”, their general structure and striking a balance between exploratory experimentation and automated chaos in CI/CD or as a background service. 

- Steady-State hypothesis & the role of SLOs and its evaluation/validation as aided by chaos experimentation. Declarative intent for SLOs. 

- Observability requirements for cloud-native chaos engineering. Generation as well as consumption of observability “data” within chaos experiments. 

- Chaos Engineering in a Multi-tenant world. Security considerations and security chaos experiments as a sub-category. 

- Chaos engineering methodologies for a hybrid environment comprising services on Kubernetes as well as non-Kubernetes infrastructure. 

- One of the requirements during Chaos engineering is to maintain Security Resilience thru-out the development, deployment, and runtime
