---
title: DevOps
description: 
published: true
date: 2023-10-29T14:39:01.108Z
tags: 
editor: markdown
dateCreated: 2023-10-29T14:39:01.108Z
---

# DevOps
## Members
- Brutus5000
- Sheikah
- Askaholic
- BlackYps
- p4block
- MazorNoob
- kubko
- Rowey
- MarcSpector

## Mission statement
We enable the promise of forever in Forged Alliance Forever.

This is achieved by following our key goals. Everything we do should be

 1. open and reproducible,
 2. built to last,
 3. built to scale,
 4. avoiding vendor lock-in & single point of failures and
 5. as simple as possible, but as complex as required.
 
*More details on these goals in the dedicated chapter "Conflict of goals".*

## Way of working
- The central place of communication is Zulip, with dedicated project or application streams if required and a dedicated `development` stream for all other topics or overarching topics.
- Zulip is invite only, but invitations are handed out for all interested persons.
- The central place of collaboration is [Github](https://github.com/FAForever), with dedicated repositories for the dedicated projects or applications.[1]
- All change requests have to be brought in as a Pull Request.
- Issues are used for bugs and feature requests.
- Releases are used to create & tag new version artifacts.
- For project planning & management we recommend Github projects, but it is not mandatory.
- Submissions via Pull Requests are accepted also from outside collaborators (no need to have a developer role)
- Repositories can have more specified way of working. This is to be documented in the repositories contribution file and referenced in the readme.
- In some cases (e.g. translations) the working platform is elsewhere. This is to be documented in the related projects or applications.

[1] Repositories for the game and featured mods are not covered in this team.

## Roles
In order to avoid chaos and achieve our key goals, we defined the following roles:

1. Team Lead
2. Server administrator
3. Application maintainer (application specific) [1]
4. DevOps & site reliability engineer
5. Application developer (application specific)
6. Tester
7. Translator

Any team member can have multiple roles. There shall be only one team lead, but he should call out a deputy.

[1] Maintainers are implicitly application developers too.

### Rights and responsibilities
Even though FAF is an open source project where everyone can come and go as they please, FAF as a legal entity has non-transferable duties that need to be fulfilled:

- Protect user data as per GDPR.
- Ensure resource usage following contractual limits and/or following fair-use policy of our service providers.
- Assert IT security to prevent server to become surface or source for malware, phishing or other sort of IT attacks.

In order to fulfill these duties, we need some dedicated team members that are

- qualified in related topics,
- willing to work on a common goal even if outside their personal interest,
- reliably available,
- willing to learn on topics as they occur and
- long-term committed.

As such they need to have higher authority over other team members in order to

- make decisions, that may be
	- fast (in case of time-critical incidents) or
	- unpopular (drop or reject a feature because it contradicts with certain goals such as maintainability) or
	- controversial (if there are multiple options and no suitable compromise is available),
- delegate tasks (and corresponding permissions) and
- ensure collaboration.

The order of the roles gives a first indication of the authority hierarchy, while not completely accurate.

### Team Lead
### Tabs {.tabset}
#### Required Skills
The team leads skill set can be summarized as: "Can fork and run FAF on a toaster."

The team lead

- has decent knowledge on running and maintaining Linux servers
- has advanced software engineering and architecture skills
- understands the infrastructure stack of FAF, especially which parts are critical and which parts are optional
- knows the role of all applications in FAF and how they depend on each other
- can estimate what impact changes will have on the overall system. As such he coordinates overarching topics between the maintainers.

#### Tasks & Responsibilites
- Monitor overall status of the FAF stack
- Planning & budgeting the FAF infrastructure (in cooperation with the treasurer)
- Keep track of required changes due to legal requirements
- Document the FAF infrastructure and application landscape
- Project management and coordination for over-arching topics
- Consultant for larger changes with architecture impact
- Software selection processes (for 3rd party software)
- Global Github owner & permission manager
- Recruits, appoints and dismisses
	- Server administrators
	- Application maintainers
	- DevOps & site reliability engineers
- Has the ultimate veto on which software / which changes get deployed to production
- Has the final word in architectural questions

#### Position Filling
Due to the required skills and associated responsibilities, the team lead is not elected in a democratic vote of the whole team, nor is its position restricted to a limited period of time.

The team leader can be replaced with a constructive vote of no confidence. This requires approval of 3/4 of the server admins and application maintainers (the team lead itself excluded). Persons embodying multiple roles still only have one vote.

Should the team lead resign, it is expected to be accompanied by a proposal for a new team lead. This proposal can only be overruled by the same rules as in a constructive vote of no confidence.

Should the team lead not propose a successor, the server admins and application maintainers have to elect one with an absolute majority. If an absolute majority is not achieved in the first ballot, a run-off election is held.





### Server Administrator
### Tabs {.tabset}
#### Required Skills
Each server admin needs to have at least some of these skills and together they should cover all of them:

- Linux administrator experience
- Knowledge in Docker / Containerization / Cloud infrastructure
- Skills in shell scripting
- Basic git skills
- Insights of the FAF application stack

#### Tasks & Responsibilites
- Maintain the servers, including
	- monitoring for security issues and apply patches
	- configuring and performing backups
	- monitor server health and load
	- tune server performance where applicable
- Perform server updates
	- Deploy updates for FAF & 3rd party applications in order of dependencies
	- Monitor issues after updates
	- Rollback if required
- Deploy featured mods
- Continuous improvement & automation of tasks


#### Position Filling
In general the process is simple:

1. Volunteers candidate for the position
2. DevOps team lead decides about application
3. Agreements on confidentially etc. are signed (GDPR related)

However the main issue is that server administrators require a maximum level on trust, therefore applicants need to earn that trust beforehand. There is not a regular process for this. Past experience shows, that server admins either had an application developer role before or just helped out with their knowledge on occasions.


### Application maintainer (application specific)
### Tabs {.tabset}
#### Required Skills
- Expert knowledge of the software, it's configuration and it's role in the FAF overall architecture
- Docker skills to manage a custom image
- Decent git skills

For self-developed software:

- Advanced skills of the applications programming language


#### Tasks & Responsibilites
- Design the application architecture
- Ownership of the application configuration
- Release management in coordination with server admins
- Manage the issue tracker (perform or delegate)
	- Fix bugs
	- Implement feature requests
	- Cleanup obsolete issues
- Review and merge pull requests
- Onboard new developers
- Keep documentation up to date


#### Position Filling
The application maintainer is appointed by the team lead. If there is no current maintainer, contact the team lead to apply for this position. Previous contributions to the applications are expected.

By default there should only be one maintainer per app. The team lead can appoint more in appropriate cases.

Should an application maintainer resign, it is expected to be accompanied by a proposal for a new maintainer. This proposal can only be overruled by the team lead.


### DevOps & site reliability engineer
### Tabs {.tabset}
#### Required Skills
- Expert in Linux / System administration and/or
- Expert in Docker & Kubernetes and/or
- Expert in FAF core technology (e.g. MariaDB, ZFS, RabbitMQ, ...)
- Expert in Cloud infrastructure and/or
- Expert in DevOps enabling technologies (e.g. CI/CD pipelines)

#### Tasks & Responsibilites
Depending on the skillset they will aid in designing, implementing and/or improving

- infrastructure landscape (e.g. server setup)
- server or application configuration (e.g. database or file system tuning)
- backup strategy & desaster recovery
- DNS & CDN setup
- automating regular tasks
- security / security reviews
- monitoring concepts

for all or single pieces of the FAF stack and its infrastructure.


#### Position Filling
- Start contributing on a regular basis
- Ask team lead and/or server admins where your skills can help
- On continous contribution the team lead will add you to the list



### Application developer (application specific)
### Tabs {.tabset}
#### Required Skills
- Basic knowledge of the applications programming language
- Basic knowledge of the applications inner working
- Basic Git knowledge

#### Tasks & Responsibilites
- Fix bugs
- Design features in alignment with the maintainer and write code to implement them
- Write tests
- Apply changes according to maintainers feedback
- Review other developers pull requests

#### Position Filling
- Regularly contribute to an application
- Contact the maintainer to get officially listed


### Tester
### Tabs {.tabset}
#### Required Skills
- Endurance to test the same thing over an over again
- Creativity to test out things that weren't intended by the developer
- Structured reporting of errors

#### Tasks & Responsibilites
- Use the pre-release of the application and check if new feature are broken and verify the old features keep working
- If something breaks write a Github issue (What did you do, what did happen, what did you expect to happen?)
- Participate in (rare) announced testing events

#### Position Filling
- Approach the application maintainer and offer your help


### Translator
### Tabs {.tabset}
#### Required Skills
- You should be a native speaker of the language you want to translate into
- Good grammar and punctuation

#### Tasks & Responsibilites
- Translating english into your native language in dedicated tools
- Regularly check for newly added translation strings

#### Position Filling
- Approach the application maintainer and offer your help

## Conflict of goals
On all levels on FAF (server infrastructure, application stack, inside an application) we face similar conflict of goals that need to be considered.

These are stated here to help contributors understand why not all ideas or feature requests are welcome or get accepted.

Some of these may sound redundant but have different factors:

## tabs {.tabset}
### Features
Users want as many features as possible. Because why not? Well because of the other factors!

TL;DR: Sometimes it makes sense to have less features in order for everything else to work better.

### Complexity
More features can mean:

- add more code to an existing application. But more code is harder to understand and makes it more complex. More complexity means more things to know and learn for new developers. It also means more time required for the application maintainer to do reviews.
- add another application or add plugins for an existing application. This pushes more work onto server admins and maybe also other maintainers due to
	- more dependency in between the applications
	- more configuration required (configure the app, configure all of its depndencies, tune the configuration)
	- more monitoring required (does the app work?)
	- more apps to consider for security updates and release management

### Risk
Every change has a risk.

- The risk of introducing a bug
- The risk to make an application or even an entiry system crash
- The risk to lose data

Risks have a probability of occurrence and a potential damage they do.
Minor risks such as uncritical bugs already have a high probability of occurence, but usually have low damage.
Major risks causing systems to fail have a low probability but a high damage.

Usually you weigh them by probability * potential damage. But that's not important for us. What is important is that risk is acumulated. The bigger the system gets, the more componants it contains, the more complexity we have, the risk will grow.

There are ways to reduce risk probability or to reduce the damage. But these things take up resources and knowledge that is not always available.

The best way to avoid risk is to avoid unnecessary complexity.

### Cost

FAF is an open source project running on limited donations.
So whatever we do, we have to keep costs at a minimum.

This has drawbacks, as it in general removes options to run on managed platforms (such as AWS) or single managed services (such as Twilio, MailJet, managed MariaDB or hosted NodeBB).

As a side note: FAF funds will never suffice to contract fulltime developers or admins. But this would questionable for other reasons anyway.

### Time

Time is the most important resource in FAF, but a scarce one too.

So every contributor has to make a choice how to spend the time available.
As such the choice can be either to fix a bug or develop feature

### Fault Tolerance


### Maintainability


### Performance


### Portability

Portability has two layers:

- The environment the application is running
- The environment the appliction is developed

Some things to take into account here are:

- The majority (90%+) of FAF users runs on Windows
- The majority (75%+) of FAF core developers use Linux
- Taking one-time or occasional developers into account the distribution is probably 50/50 or even 75% Windows.
- The FAF server landscape is Linux.
- The FAF server landscape is (planned to be) multi-machine
- A developer "landscape" is a single PC.

It is usually very hard to ensure things working on different environments (especially environments a developer does not have available). Therefore in justified cases (outweighing the other scopes) other environments are 2nd class citizens or completely unsupported.















