---
title: "Some Key Terms for Network Incident and Problem Management"
abbrev: "Incident Terminology"
category: info

docname: draft-davis-nmop-incident-terminology-latest
submissiontype: IETF
number:
date:
consensus: true
v: 3
area: "Operations and Management"
workgroup: "Network Management Operations"
keyword:
 - dddd
 - ddddd
 - dddd

author:
 -
    fullname: Nigel Davis
    organization: Ciena
    role: editor
    email: ndavis@ciena.com
 -
    fullname: Adrian Farrel
    organization: Old Dog Consulting
    role: editor
    email: adrian@olddog.co.uk
 -
    fullname: Thomas Graf
    organization: Swisscom
    email: thomas.graf@swisscom.com
 -
    fullname: Qin Wu
    organization: Huawei
    email: bill.wu@huawei.com
 -
    fullname: Chaode Yu
    organization: Huawei
    email: yuchaode@huawei.com

normative:

informative:


--- abstract

   This document sets out some key terms that are fundamental to a
   common understanding of network incident and problem management
   within the IETF.

   The purpose of this document is to bring clarity to discussions and
   other work related to network incident and problem management in
   particular YANG models and management protocols that report, make
   visible, or manage network incidents and problems.

--- middle

# Introduction

   Successful operation of large or busy networks depends on network
   management.  Network management comprises a virtuous circle of
   network control, network observability, network analytics, network
   assurance, and back to network control.  Network incident and problem
   management is an important aspect of network management and control
   solutions.  It deals with the reporting, inspection, correlation, and
   management of events within the network.  The intention is to focus
   on those events have a negative effect on the network's ability to
   forward traffic in an optimal way.  Incident and problem management
   extends to include actions taken to determine the causes of problems
   and to work toward recovery of optimal network behavior.

   A number of work efforts within the IETF seek to provide components
   of an incident management system, such as YANG models or management
   protocols.  It is important that a common terminology is used so that
   there is a clear understanding of how the elements of the management
   and control solutions fit together, and how incidents and problems
   will be handled.

   This document sets out some key terms that are fundamental to a
   common understanding of incident and problem management.  These terms
   are intended for use within IETF documents.


   Note that some useful terms are defined in {{?RFC3877}} and {{?RFC8632}}.
   The definitions in this document are informed by those documents, but
   they are not dependent on that prior work.

#  Terminology

   The terms are presented below in an order that is intended to flow
   such that it is possible to gain understanding reading top to bottom.
   The figures and explanations in Section 3 may aid understanding the
   terms set out here.

   System:
   :  An assembly of components that exhibits some behavior.

  External System:
   :  Beyond the scope of the control system.

   Controlled External System:
   :  An external system that is of interest
      to and is influenced by the control system.  Viewed as a
      collection of resources.

   Resource:
   :  A component, commodity, service, or capability that can be
      used in a valuable way in the performance of some activity.

      *  Resource is a recursive concept so that a resource may be a
         collection of other resources (for example, a network node is a
         collection of interfaces).

      *  Connectivity services and network capabilities may be realized
         by the collection of many resources, yet services and
         capablities may also be recognized as resources in their own
         right.

   Characteristic:
   :  Observable or measurable aspect or behavior
      associated with a resource or collection of resources.

      *  A characteristic may be considered with respect to the concept
         of dimensional that is built on facts (see 'value', below) and
         dimensions (the contexts and descriptors that identify and give
         meaning to the facts).

   Value:
   :  A measurable amount which may be in the form of an integer
      (e.g., a count) or on a continuous variable (e.g., an analogue
      measurement) associated with a characteristic.

   Condition:
   :  The interpretation of the values of a set of
      characteristics of the resource (with respect to working order or
      some other aspect relevant to the resource purpose/application).

   Change:
   :  Variation in values associated with a characteristic of a
      resource at a specific time or over time.

      *  Most changes are not noteworthy (i.e., are not relevant).

      *  Perception of change depends upon detection, the sampling
         rate/accuracy/detail, and perspective.

   Detect:
   :  To notice the presence of something (state, change,
      activity, form, etc.).

      *  Hence also to notice a change (from the perspective of the
         viewer).

   Event:
   :  The detected change in value (of a characteristic of a
      resource) at a measurable instant in time (i.e., the period is
      negligible).

      *  Compared with a change, which is over a period of time, an
         event happens at a measurable instant.

   State:
   :  A particular condition that something (e.g., a resource) is
      in (at a specific time).

      *  While a state may be observed at a specific moment in time, it
         is actually achieved by summarizing the measurement over time
         in a process sometimes called state compression.

   Relevance:
   :  Consideration of an event, state, or value (through the
      application of policy, relative to a specific viewpoint/
     perspective, intent, and in relation to other events, states, and
      values) to determine whether it is of note to the control system.

   Occurrence:
   :  A relevant event.
   : A particular relevant change.

      *  An occurrence may be an aggregation or abstraction of smaller
         occurrences.

      *  Applies to all scales and scopes, i.e., is essentially fractal
         (can recurse indefinitely).

      *  Note that occurrence is used here with respect to the temporal
         dimension.

   Incident:
   :  An occurrence that is not desired/required (as it may be
      indicative of a future undesired State).

   Problem:
   :  A state regarded as undesirable and may require remedial
      action.

      *  Note that there is a historic aspect to the concept of a
         problem.  The current state may be operational, but there could
         have been a failure that is unexplained, and the fact of that
         unexplained recent failure is a problem.

      *  Note that whilst a problem is unresolved it may continue to
         require attention.  A record of resolved problems may be
         maintained in a log.

      *  Note that there may be a state which is considered to be a
         problem from several perspectives (e.g., a loss of light state
         may cause multiple services to fail).  A state change (so that
         the light recovers) may cause the problem to be resolved from
         one perspective (the services are operational once more), but
         may leave the problem as unresolved (because the loss of light
         has not been explained).  There could be a further development
         (the reason for the temporary loss of light is traced to a
         microbend in the fiber that is repaired) resulting in that
         unresolved problem is now resolved.  But this leaves a further
         problem still unresolved (why did the microbend occur in the
         first place?).

   Symptom:
   :  An observable characteristic/state/condition considered as
      an indication of a problem or potential problem.

   Cause:
   :  The events (detected or otherwise) that gave rise to a
      problem.

   Root Cause:
   :  The fundamental cause that gave rise to all associated
      problems.

   Consolidation:
   :  The process of considering multiple problems,
      symptoms, and their causes to determine the root cause.

   Alert:
   :  The indication of an incident.

   Alarm:
   :  A continuous indication (to a human operator) highlighting
      the potential or actual presence of a problem.

   Three other terms may be helpful:

   Transient:
   :  A state, considered as a problem, that persists for a
      limited amount of time before becoming resolved without direct
      action by an operator or control system.

   Intermittent:
   :  A state that is not maintained, but keeps occurring in
      some meaningfully short time frame.

# Workflow Explanations

   The relationship between system, resource, and characteristics is
   shown in {{figure-1}}.  A Controlled External System is comprised of
   Resources, and Resources have Characteristics.

~~~~
     Characteristics
            ^
            |
         Resource
            ^
            |
Controlled External System
            ^
            |
     External System
~~~~
{: #figure-1 title="Relationship Between Elements of a System" artwork-align="center"}


   The Value of a Characteristic of a Resource is expected to change
   over time.  Specific changes in value may be noticed ay a specific
   time (as digital changes), Detected, and treated as Events.  This is
   shown on the left of {{figure-2}}.

   The center of Figure 2 shows how the Value of a Characteristic may
   change over time.  The value may be Detected at specific times or
   periodically and give rise to States (and consequently State
   changes).

   In practice, the Characteristic may vary in an analog manner over
   time as shown on the right hand side of {{figure-2}}.  The Value can be
   read or reported (i.e., Detected) periodically leading to Analogue
   Values that may be deemed Relevant Values, or may be evaluated over
   time as shown in {{figure-6}}.

~~~~
     Event                State                  Value

       ^                    ^                      ^
Detect :             Detect :               Detect :
       :                    :                      :

   ^        ^          ^     ^     ^                   /\
   :        :          :     :     :                  /  \
   :        :          :     :     :             /\  /    \
    __    __               _____                /  \/
   |        |             |     |            /\/
 __|        |__       ____|     |____       /

Change at a time     Change over time      Change over time
~~~~
{: #figure-2 title="Characteristics and Changes" artwork-align="center"}

   {{figure-3}} shows the workflow progress for Events.  As noted above, an
   Event is a Change in the Value of a Characteristic at a time.  The
   Event may be evaluated (considering policy, relative to a specific
   viewpoint/perspective, with a view to intent, and in relation to
   other Events, States, and Values) to determine if it is an Occurrence
   and possibly to indicate a change of State.  An Occurrence may be
   undesirable (an Incident) and that can cause an Alert to be
   generated, may be evidence of a Problem and could directly indicate a
   Cause.


~~~~
   Alert- - - - > Alarm
     ^
     |
     |     -----> Cause
     |    |
     |----------> Problem
     |
     |
 Incident
     ^
     |
     |
     |
Occurrence
     ^
     |
     |----------> State
     |
     |
   Event
~~~~
{: #figure-3 title="Events and Dependent Terms" artwork-align="center"}


   Parallel to the workflow for Events, {{figure-4}} shows the workflow
   progress for States.  As shown in Figure 2, Change noted at a
   particular time gives rise to State.  The State may be deemed
   Relevant considering policy, relative to a specific viewpoint/
   perspective, with a view to intent, and in relation to other Events,
   States, and Values.  A Relevant State may be deemed a Problem, or may
   indicate a Problem.

   Problems may be considered as Symptoms and may map directly or
   indirectly to Causes.  An Alarm may be raised as the result of a
   Problem.


~~~~
   Alarm
    ^
     |
     |       ----> Cause
     |      |
 Problem---------> Symptom
     ^
     |
     |
     |
Relevant State
     ^
     |
     |
     |
   State
~~~~
{: #figure-4 title="States and Dependent Terms" artwork-align="center"}

   {{figure-5}} shows how Incidens and Problems may be consolidated to
   determine Causes and the underlying Root Cause.

   A Cause can be indicated by or determined from Incidents, Problems
   and Symptoms.  It may be that one Cause points to another, and can
   also be considered as a Symptom.  The determination of Causes and the
   Root Cause can consider multiple inputs.


~~~~
            ------------
           | Root Cause |
            ------------
                 ^                 ---------
                 |  ------------- |         |
                 | |  ----------> | Symptom |
                 | | |            |         |
                 | | |             ---------
                 | v |                 ^
               ---------               |
    --------->|  Cause  |<----------   |
   |           ---------            |  |
   |             ^   |              |  |
   |             |   |              |  |
   |              ---               |  |
   |                                |  |
 ----------                      ---------
| Incident |------------------> | Problem |
 ----------                      ---------
~~~~
{: #figure-5 title=" Consolidation of Symptoms and Causes" artwork-align="center"}


   The final figure in this section ({{figure-6}}) shows how thresholds are
   important in the consideration of Analogue Values and Events.
   Analogue Values may be read or notified from the Resource and could
   transition a threshold, be deemed Relevant Values, or evaluated over
   time.  Events may be counted, and the Count may cross a threshold or
   reach a Releavnt Value.

   The Threshold Process may be implementation-specific and subject to
   policies.  When a threshold is crossed and any other conditions are
   matched, an Event may be determined, and treated like any other
   Event.


~~~~
Occurrence
     ^
     |
     |---------------------> State
     |
     |        -------
     |------>| Count |-------------------------> Relevant Value
     |        -------          |                       ^
     |           |             |                       |
     |           |             |                       |
     |           |             v                       |
     |           |        -----------           ----------------
   Event         |       | Evaluated |         |                |
     ^           |       | over time |<--------| Analogue Value |
     |           v        -----------          |                |
     |      -----------        |               |                |
     |     | Threshold |       |               |                |
     |<----|  Process  |<------                |                |
     |     |           |<----------------------|                |
     |      -----------                         ----------------
     |                                                 ^
     |                                                 |
     | Detect                                   Detect |
     |                                                 |
Change at a Time                                Change over Time
~~~~
{: #figure-6 title="Counts, Thresholds, and Values" artwork-align="center"}

#  Security Considerations

   This document specifies terminology and has no direct effect on the
   security of implementations or deployments.  However, protocol
   solutions and management models need to be aware of several aspects:

   *  The exposure of information pertaining to incidents may make
      available knowledge of the internal workings of a network (in
      particular its vulnerabilities) that may be of use to an attacker.

   *  Systems that generate management information (messages,
      notifications, etc.) when incidents occur, may be attacked by
      causing them to generate so much information that the management
      system is swamped an unable to properly manage the network.

   *  Reporting false information about incidents (or masking reports of
      incidents) may cause the management system to function
      incorrectly.


#  Privacy Considerations

   In general, Incident Management will not expose information about
   end-user activities or user data.  The main privacy concern is for a
   network operator to keep control of all information about incidents
   to protect their privacy and the details of how they operate their
   network.

# IANA Considerations

This document makes no requests for IANA action.


--- back

# Acknowledgments
{:numbered="false"}

   The authors would like to thank Med Boucadair and Wanting Du for
   their helpful comments.
