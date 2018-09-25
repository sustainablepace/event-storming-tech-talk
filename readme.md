# Event Storming Tech Talk

Slides are taken from 
- [50000 Orange Stickies Later](https://de.slideshare.net/ziobrando/50000-orange-stickies-later) by Alberto Brandolini ([video](https://www.youtube.com/watch?v=1i6QYvYhlYQ))
- [Know the Flow](https://speakerdeck.com/martinschimak/ddd-exchange-london-2018-know-the-flow-events-commands-and-long-running-services) by Martin Schimak ([video](https://skillsmatter.com/skillscasts/11518-know-the-flow-events-commands-and-long-running-services))

## What is Event Storming tl;dr

- Fast and low overhead method for collaboratively discovering a business domain and enabling decision making, like
  - Identify core domain: Buy or make? 
  - Bottlenecks and pain points? Manual workarounds possible?
  - Context boundaries?
  - Building blocks?
- Individuals and interactions over processes and tools
  - enable conversations
  - empower people
  - create a shared mental model
- (Domain) Event + (Brain) Storming
- Conceived by Alberto Brandolini, still evolving

## Motivation 

### Understanding the problem domain is hard

- "Is the problem they want solved the problem that needs to be solved?"
- Social problem
- "If only we had asked Bob..."
- Scrum doesn't help

![50000 Orange Stickies Later](50000-orange-stickies-later-04.jpg)

Round-robin interviews with all domain experts not ideal

![Rashomon](rashomon.jpg)

- One crime, four versions of the truth
- Avoid being the detective: let all stakeholders figure out the truth collaboratively

## Big Picture Event Storming

![50000 Orange Stickies Later](50000-orange-stickies-later-01.jpg)

![Software Design Example](software-design/01.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-02.jpg)

### Finding the truth collaboratively (what happened?)
   
![50000 Orange Stickies Later](50000-orange-stickies-later-03.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-18.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-05.jpg)

### Outcome allows decision making

![50000 Orange Stickies Later](50000-orange-stickies-later-07.jpg)

Blockers, bottlenecks, pain points

![50000 Orange Stickies Later](50000-orange-stickies-later-08.jpg)

Context boundaries

![50000 Orange Stickies Later](50000-orange-stickies-later-19.jpg)

### Each discarded post-it represents a conversation or an act of learning

![Learning](learning.jpg)

### Example: Finding context boundaries (Domain "Organizing a meet-up")

![Big Picture](big-picture-1.jpg)

![Big Picture](big-picture-2.jpg)

![Big Picture](big-picture-3.jpg)

Indicators
- cluster on timeline
- triggered by potentially a single command
- ends potentially with a single event
- language different from other clusters
- different stakeholders

Read a [summary of the workshop](https://medium.com/jugthde/domain-driven-design-renaissance-event-storming-a193db8ef887)

## Other Scopes

![50000 Orange Stickies Later](50000-orange-stickies-later-21.jpg)

### Big Picture for complex environments

![Cynefin](Cynefin.png)

- low zoom events, birds eye view 
- emerging model
- defer consensus
- identify probing opportunities
- "throw away the model"

We need variations for less complex scenarios

## Process Modelling

![50000 Orange Stickies Later](50000-orange-stickies-later-10.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-11.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-12.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-13.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-14.jpg)

### Example: Order process

Policies might also represent context boundaries 

![Process Modelling](process-modelling-01.jpg)

![Process Modelling](process-modelling-02.jpg)

![Process Modelling](process-modelling-03.jpg)

![Process Modelling](process-modelling-04.jpg)

![Process Modelling](process-modelling-05.jpg)

![Process Modelling](process-modelling-06.jpg)

![Process Modelling](process-modelling-07.jpg)

![Process Modelling](process-modelling-08.jpg)

![Process Modelling](process-modelling-09.jpg)

![Process Modelling](process-modelling-10.jpg)

![Process Modelling](process-modelling-example.jpg)

An example of process modelling
- 45 minute experiment by Team Turtlez
- three different flows of order fulfillment: FFC 2.0, FFC 1.0, DHL (trivialized)
- understanding of whole process is vague  
- maybe an interesting experiment: are policies on the correct zoom level?

## Software Design

![50000 Orange Stickies Later](50000-orange-stickies-later-21.jpg)

### typically for complicated environments

![Cynefin](Cynefin.png)

- Scope is heavily constrained
- Identify patterns, good practices
- Consensus is needed
- maybe keep the model

### Example: Change email address

Problem: Customer wants to change her email address in online shop

Disclaimer: Not the original model, just a reconstruction

Scope is constrained :
![Software Design Example](software-design/02.jpg)

Pattern: Command, Aggregate (with invariants), Event
![Software Design Example](software-design/03.jpg)
![50000 Orange Stickies Later](50000-orange-stickies-later-16.jpg)


Decoupling with policies:
![Software Design Example](software-design/04.jpg)
![Software Design Example](software-design/05.jpg)
![50000 Orange Stickies Later](50000-orange-stickies-later-12.jpg)

Pattern repeats itself...model emerges
![Software Design Example](software-design/07.jpg)

Rethinking aggregates, introducing read models
![Software Design Example](software-design/08.jpg)
![Software Design Example](software-design/16.jpg)
![50000 Orange Stickies Later](50000-orange-stickies-later-17.jpg)

More read models...
![Software Design Example](software-design/09.jpg)
![Software Design Example](software-design/10.jpg)
![Software Design Example](software-design/11.jpg)
![Software Design Example](software-design/12.jpg)
![Software Design Example](software-design/13.jpg)
![Software Design Example](software-design/14.jpg)

Learned a lot :)
![Software Design Example](software-design/17.jpg)

A model that could almost be implemented
![Software Design Example](software-design/15.jpg)
![The picture that explains almost everything](almost-everything.jpg)

## Summary - different formats for different zoom levels

![50000 Orange Stickies Later](50000-orange-stickies-later-21.jpg)
