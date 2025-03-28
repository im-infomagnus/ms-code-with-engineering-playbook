# Incorporating Design Reviews into an Engagement

## Introduction

Design reviews should not feel like a burden. Design reviews can be easily incorporated into the dev crew process with minimal overhead.

- Only create design reviews when needed. Not every story or task requires a complete design review.
- Leverage this guidance to make changes that best fit in with the team. Every team works differently.
- Leverage subject-matter experts (SME) as needed during design reviews. Not every story needs SME or leadership sign-off. Most design reviews can be fully executed within a dev crew.
- [Use diagrams](./preferred-diagram-tooling.md) to visualize concepts and architecture.

The following guidelines outline how Microsoft and the customer together can incorporate design reviews into their day-to-day agile processes.

## Envisioning / Architecture Design Session (ADS)

Early in an engagement InfoMagnus works with customers to understand their unique goals and objectives and establish a definition of done. The project team dives deep into existing customer infrastructure and architecture to understand potential constraints. Additionally, we seek to understand and uncover specific [non-functional requirements](../../design-patterns/non-functional-requirements-capture-guide.md) that influence the solution.

During this time the team uncovers many unknowns, leveraging all new-found information, in order to help generate an impactful design that meets customer goals. After ADS it can be helpful to conduct [Engineering Feasibility Spikes](../recipes/engineering-feasibility-spikes.md) to further de-risk technologies being considered for the engagement.

> **Tip**: All unknowns have not been addressed at this point.

## Sprint Planning

In many engagements InfoMagnus works with customers using a SCRUM agile development process which begins with sprint planning. [Sprint planning](../../../agile-development/ceremonies.md#sprint-planning) is a great opportunity to dive deep into the next set of high priority work. Some key points to address are the following:

1. Identify stories that require design reviews
1. Separate design from implementation for complex stories
1. Assign an owner to each design story

Stories that will benefit from design reviews have one or more of the following in common:

1. There are many unknown or unclear requirements
1. There is a wide distribution of anticipated workload, or story pointing, across the dev crew
1. The developer cannot clearly illustrate all tasks required for the story

> **Tip:** After sprint planning is complete the team should consider hosting an initial design review discussion to dive deep in the design requirement of the stories that were identified. This will provide more clarity so that the team can move forward with a design review, synchronously or asynchronously, and complete tasks.

## Sprint Backlog Refinement

If your team is not already hosting a [Sprint Backlog Refinement](../../../agile-development/advanced-topics/backlog-management) session at least once per week you should consider it. It is a great opportunity to:

1. Keep the backlog clean
1. Re-prioritize work based on shifting business priorities
1. Fill in missing descriptions and acceptance criteria
1. Identify stories that require design reviews

The team can follow the same steps from [sprint planning](#sprint-planning) to help identify which stories require design reviews. This can often save much time during the actual sprint planning meetings to focus on the task at hand.

## Sprint Retrospectives

[Sprint retrospectives](../../../agile-development/ceremonies.md#retrospectives) are a great time to check in with the dev team, identify what is working or not working, and propose changes to keep improving.

It is also a great time to check in on design reviews

- Did any of the designs change from last sprint?
- How have design changes impacted the engagement?
- Have previous design artifacts been updated to reflect new changes?

All design artifacts should be treated as a living document. As requirements change or uncover more unknowns the dev crew should retroactively update all design artifacts. Missing this critical step may cause the customer to incur future technical debt. Artifacts that are not up to date are `bugs` in the design.

> **Tip:** Keep your artifacts up to date by adding it to your teams [definition of done](../../../agile-development/team-agreements/definition-of-done.md) for all user stories.

## Sync Design Reviews

It is often helpful to schedule 1-2 design sessions per sprint as part of the normal aforementioned meeting cadence.
Throughout the sprint, folks can add design topics to the meeting agenda and if there is nothing to discuss for a particular meeting occurrence, it can simply be cancelled.
While these sessions may not always be used, they help project members align on timing and purpose early on and establish precedence, often encouraging participation so design topics don't slip through the cracks.
Oftentimes, it is helpful for those project members intending to present their design to the wider group to distribute documentation on their design prior to the session so that other participants can come prepared with context heading into the session.

It should be noted that the necessity of these sessions certainly evolves over the course of the engagement.
Early on, or in other times of more ambiguity, these meetings are typically used more often and more fully.

Lastly, while it is suggested that sync design reviews are scheduled during the normal sprint cadence, scheduling ad-hoc sessions should not be discouraged - even if these reviews are limited to the participants of a specific workstream.

## Wrap-up Sprints

Wrap-up sprints are a great time to tie up loose ends with the customer and hand-off solution. Customer hand-off becomes a lot easier when there are design artifacts to reference and deliver alongside the completed solution.

During your wrap-up sprints the dev crew should consider the following:

1. Are the design artifacts up to date?
1. Are the design artifacts stored in an accessible location?
