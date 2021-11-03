### Chaos Engineering

Chaos Engineering is the discipline of experimenting on a distributed system in order to build confidence in the system’s capability to withstand turbulent conditions in production. The goal of chaos engineering is to identify weakness in a system through controlled experiments that introduce random and unpredictable behavior in the system.

To use an analogy for the current times, Chaos Engineering is like a vaccine. We inject harm to build immunity from outages. 

The term chaos engineering is said to have been coined by Netflix around 2010-11, with chaos monkey being one of the first tools to aid the practice of this discipline. 

### Resiliency

Resiliency is the core objective of Chaos Engineering. A resilient system is a flexible system that can absorb an attack and change along with the evolving threat context of the environment. Another layman definition of application or infrastructure resilience is the ability to react to problems in one of its components and still provide the best possible service. 

### Robustness

It indicates the ability of a system to work with zero-to-minimal downtime, and be highly available. Spoken of in the same breath as Resilience. It is one of the attributes that characterizes a cloud-native application. Having said that, Focussing only on robustness gives false sense of security. Trying to prevent failures or trying to implement solutions only to prevent attacks leads to accumulation of risks that may lead to worse consequences when an incident happens.

### Principles of Chaos Engineering 

The basic tenets of chaos engineering were put together by folks from ealy practitioners like Netflix, AWS, Salesforce et al around 2011. A first formal single-page website describing this is available here: https://principlesofchaos.org/. A summarization is placed here: 

- Identify and validate steady state behaviour of your services
- Vary the failures 
- Experiment in production environments 
- Minimize and control failure blast radius 
- Automate experimentation for greater insights 

Some of the terms used here are explained subsequently. While the principles hold good to this day, there has been some evolution in the philosophy and practice of chaos engineering, especially with the emergence of cloud-native architecture and newer deployment environments like Kubernetes.  

Specifically in security chaos engineering the assumption is that the security controls will fail, so instead of seeking to stop failure the goal is to fail gracefully. Early detection of failure leads to reduced blast radius, so it is pertinent to embrace the ability to quickly detect and respond.

### Chaos Experiment

A scientific procedure, run manually or in automated fashion that targets an experimental group (service or infrastructure component) and injects a failure or places it under duress, accompanied by validation of system behaviour (hypothesis) via monitoring aids such as metrics, logs etc., and comparison with a control group not subjected to failures. 

Often, the experimentation procedure involves usage of some dedicated chaos tooling, to help with the said activities, with these tools providing a “standardized” template or “structure” for an experiment. 

### Blast Radius

The impact (often measured in terms of services impacted in the deployment environment, but could also extend to people and teams) that is caused by the experiment execution. A simple illustration is: faults injected to a container typically have a lesser blast radius compared to that injected on a virtual machine host that runs several containers. It is preferable to start the chaos engineering journey with experiments that have a smaller blast radius. 

### AUT (application under test)

A common terminology borrowed from the world of software testing that indicates the application service being subjected to chaos. 

### SUT (system under test)

The broader environment or infrastructure comprising the AUT, in which the chaos experimentation is carried out. 

### Steady State

The optimal operational characteristics of the application services or infrastructure components, often expressed as metrics and tracked by monitoring systems. This is the baseline against which deviations are recorded upon injection of faults. Invariably, the extent to which steady states deviate or should deviate forms the core expectation around the chaos experimentation process. 

### Hypothesis

The anticipated behaviour of the system upon a specific failure, the extent of deviation from steady-state OR the lack thereof (in highly resilient systems) forms the “Hypothesis”. This is always quantified and expressed as a measurement. Deemed as a prerequisite for chaos experimentation. 

### SLI (Service Level Indicator) 

A carefully defined quantitative measure of some aspect of the level of service that is provided. A good example is “latency” - how long it takes to return a response to a request. Other common SLIs include error rates, throughput etc., Typically these measurements are aggregated - i.e., they are collected/ sampled over a measurement window and turned into a rate, average or percentile. 

### SLO (Service Level Objective)

Simply stated, it is the accepted cutoff against one or more SLIs. An example of a valid SLO would be to ensure the average latency is less than 100 milliseconds. The SLOs, to the user, are about expectations on how a service performs. To the chaos engineer, it is often the basis for formulating the steady-state hypothesis for a chaos experiment. 

### Golden Signals (of SRE)

These are SLIs championed by the Google SRE teams for measuring health and performance of applications, which are generally an important part of experiment hypothesis. 

- Latency: The time it takes to service a request, with a focus on distinguishing between the latency of successful requests and the latency of failed requests.
- Traffic: A measure of how much demand is being placed on the service. This is measured using a high-level service-specific metric, like HTTP requests per second in the case of an HTTP REST API.
- Errors: The rate of requests that fail. The failures can be explicit (e.g., HTTP 500 errors) or implicit (e.g., an HTTP 200 OK response with a response body having too few items).
- Saturation: How “full” is the service. This is a measure of the system utilization, emphasizing the resources that are most constrained (e.g., memory, I/O or CPU). Services degrade in performance as they approach high saturation.

There might be other considerations as part of the hypothesis too (there is great scope for diversity here). Having said that, the golden signals are standard indicators used by the community. 

### Observability 

According to definition: It is a property of a system or infrastructure that tells us the extent to which it lends itself to inferring about its state from the knowledge of external outputs. In simpler terms, it is about how “observable” the system is: are there sufficient logs, metrics and events that are generated? Are these informative enough to help us derive the right information about how it is functioning? It is slightly different to “Monitoring” which is an action performed to determine the state of the system. Platforms that provide monitoring capabilities often also provide the ability to highlight information or events retrieved by the monitoring process. Such platforms, along with the right set of hooks built into the application services themselves - together constitute the “Observability Infrastructure”. 

Observability is a key prerequisite for definition and validation of the steady-state hypothesis, and thereby a critical requirement for chaos engineering. 

### SRE

The standard definition from wikipedia is that it is a set of principles and practices that incorporates aspects of software engineering and applies them to infrastructure and operations problems. Google likes to call it “treating operations as if it’s a software problem”. To the layman, it is a role or designation in which the engineer is responsible for availability, latency, performance, change management, monitoring, emergency/incident response, capacity planning, upgrades and other activities associated with maintaining services. The SRE, as can be understood by this description, does follow the devops paradigm, but is more concerned with maintaining a sane deployment infrastructure/production environment. 

Chaos Engineering as a discipline has grown along with the SRE role, so much so, that its practice is almost solely associated with this persona (though there are newer thought processes in this area). 

### Gamedays

Gamedays are the equivalent of fire drills and for a long time the practical expression of/actual activity associated with chaos engineering. This is the event in which a chaos experiment is carried out - either on production OR production-like environments, with all checkboxes around the experimentation process met (such as steady state hypothesis, mitigation/rollback plans and recovery procedures, sign-offs from various stakeholders etc.,). Reports are created on how the experiment was injected and how the system behaved and actionable data gleaned from them (they could involve: fixing application business logic, improving deployment practices, fixing the underlying infrastructure, improving monitoring systems OR if all went well, the details of next level faults/failures to be injected). Gamedays are held periodically and often involve manual fault injection using one or more chaos tools. 

### MTTD, MTTR 

Mean-Time-To-Detect (MTTD) & Mean-Time-To-Recovery/Repair (MTTR) are some of the most critical and used KPIs (key performance indicators) of a production system and feature majorly in the hypothesis of a chaos experiment (suite). The former describes the average time it takes to discover an issue within the system (which in turn determines how quickly they can be flagged, notifications sent etc.,) while the latter describes the time taken for restoration of the system to steady-state. The recovery could be automatic with self-healing capabilities built into the systems (as with most cloud-native systems) OR it could be manual, with human intervention. One of the goals of chaos engineering is to highlight and help fix delayed detection & also recovery times (especially in case of self-healing services).

These two KPIs are often paired with MTTF (Mean-Time-To-Fault) - which is an indicator of the system `uptime` or how long the system can survive w/o outages. While this is not an active part of the experiment hypothesis, it is a derived metric that can count as the KPI of a chaos engineering practice within an organization. An increased MTTF highlights the benefits brought about by chaos engineering. 

### Service Availability: Five 9s 

An indicator of the fraction of the time the service is usable. It is typically measured at an overall system/platform level and is often a part of SLAs (service-level-agreements) between the providers & consumers of the broader service (rather than being measured on a per “component” or “microservice” basis). Five nines is represented numerically as “99.999% availability”. While 100% is near-impossible and a theoretical measure, the overall goal of a chaos engineering practice is to drive it as close as possible to the figure. 











