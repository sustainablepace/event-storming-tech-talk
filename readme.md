# Event Storming Tech Talk

## What is Event Storming

- (Domain) Event + (Brain) Storming
- Fast and low overhead method for collaborative discovering a business domain and enabling decision making
- Individuals and interactions over processes and tools: Fuzzy by design to enable conversations, empowering people to create a shared mental model
- Decision enabler
  - Identify core domain: Buy or make? 
  - Bottlenecks and pain points? Manual workarounds possible?
  - Context boundaries?
  - Building blocks?

The following slides are taken from "50000 Orange Stickies Later", a talk by Alberto Brandolini. The complete 
[slides](https://de.slideshare.net/ziobrando/50000-orange-stickies-later) and a video of the 
[talk](https://www.youtube.com/watch?v=1i6QYvYhlYQ) are available online. 

![50000 Orange Stickies Later](50000-orange-stickies-later-04.jpg)

Rashomon effect - let them figure out the truth by themselves, not by an analyst

![50000 Orange Stickies Later](50000-orange-stickies-later-18.jpg)

## Big Picture Event Storming

![50000 Orange Stickies Later](50000-orange-stickies-later-01.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-02.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-03.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-05.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-06.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-07.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-08.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-19.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-20.jpg)

Success is measured by discarded post its -> a lot of conversation happened

Indicators for clusters
- cluster on timeline
- triggered by potentially a single command
- ends potentially with a single event
- language different from other clusters
- different stakeholders


### Example: Organizing a meet-up

![Big Picture](big-picture-1.jpg)

![Big Picture](big-picture-2.jpg)

![Big Picture](big-picture-3.jpg)

Read a [summary of the workshop](https://medium.com/jugthde/domain-driven-design-renaissance-event-storming-a193db8ef887)

## Other Scopes

![50000 Orange Stickies Later](50000-orange-stickies-later-21.jpg)

![Cynefin](Cynefin.png)

## Process Modelling

![50000 Orange Stickies Later](50000-orange-stickies-later-09.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-10.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-11.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-12.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-13.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-14.jpg)

### Example: Order process

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

Taken from [Martin Schimak's talk on process modelling](https://skillsmatter.com/skillscasts/11518-know-the-flow-events-commands-and-long-running-services). Take a look at his [slides](https://speakerdeck.com/martinschimak/ddd-exchange-london-2018-know-the-flow-events-commands-and-long-running-services) for more details.

![Process Modelling](process-modelling-example.jpg)

A trivial example of process modelling, showing three different flows of order fulfillment: FFC 2.0, FFC 1.0, DHL

## Software Design

![50000 Orange Stickies Later](50000-orange-stickies-later-15.jpg)

![50000 Orange Stickies Later](50000-orange-stickies-later-16.jpg)
    
![50000 Orange Stickies Later](50000-orange-stickies-later-17.jpg)


### Example: Change email address

![Software Design Example](software-design/01.jpg)
![Software Design Example](software-design/02.jpg)
![Software Design Example](software-design/03.jpg)
![Software Design Example](software-design/04.jpg)
![Software Design Example](software-design/05.jpg)
![Software Design Example](software-design/06.jpg)
![Software Design Example](software-design/07.jpg)
![Software Design Example](software-design/08.jpg)
![Software Design Example](software-design/09.jpg)
![Software Design Example](software-design/10.jpg)
![Software Design Example](software-design/11.jpg)
![Software Design Example](software-design/12.jpg)
![Software Design Example](software-design/13.jpg)
![Software Design Example](software-design/14.jpg)
![Software Design Example](software-design/15.jpg)
![Software Design Example](software-design/16.jpg)
![Software Design Example](software-design/17.jpg)

Read model: Form with input fields for new email address and confirmation
Command: Create change email request

Aggregate: Change email request
- New email is available? 
- New email is valid?
- Confirmation matches?
- Is a change email process already active?

Event: Started change email request, create token with limited lifetime
or Event: Resume change email request, reset token lifetime
Policy: Whenever the change email request has been started or resumed
Command: Create email to old email address with activation link
Event: Mail sent

Policy (manual): Mail received by user
Read model: mail
Command: User clicks link in mail

Aggregate: Change email request
Event: Token is valid
Read model: User can set a new password
Command: set new password
Event: Password reset
Read model: Password reset successfully

Policy: Whenever an email address is reset, send confirmation mail
or Event: Token is invalid or expired
Read model: Password reset form with error message

## Summary - different formats for different zoom levels

![50000 Orange Stickies Later](50000-orange-stickies-later-21.jpg)
