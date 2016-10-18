Process Hacking with Rangle Flow

Yuri Takhteyev

# Why Agile?

Three Modes of development

#### Chaos model 

Where developers fly by the seat of their pants and make stuff up as they go - probably the most common software development process - the the most prone to problems of all kinds.

#### Waterfall

Where specific team members plan and plan and think and do project planning, architecture planning and more planning and requirements documentation and technical documentation - then hand it off to development to build the whole thing.

#### Agile 

Introduces some process - lots more process than chaotic development, but not as much as waterfall. The key idea is to reduce waste. How do we think about this? Imagine the project manager from hell. Don’t do what they would do. Don’t build long stuff. Only build what we actually need and limit work in progress. More is achieved when developers can get tasks done in shorter times.

*Why would we build what we don’t need?* Maybe developers don’t actually know what the users need. Often the product managers don’t know this either. Even the users don’t know what they need. If no one knows what’s needed, you end up building things you don’t need. Waterfall tries to fix this, but often fails due to all the extra steps introduced between user and developer and the lack of feedback during the development process.

*What’s the solution? *

Value and feedback through "early and continuous delivery" - Agile Manifesto

By creating an environment that encourages close collaboration through self-managing teams. Having teams solve problems, not individuals.

*What’s wrong with work in progress?*

Your WIP provides no value because it’s not actually available for users to try. You won’t have any knowledge of the value of the WIP until it’s released so you can get feedback - which provides you the understanding of the value and informs the direction of a project as it moves forward. 

Avoid WIP by breaking up the work into the smallest tasks possible. If tasks take a few days, make them smaller if possible. Always finish what you start before moving on.

# Doing Scrum By The Book

*The Book*

At Rangle, they decided "the book" was, *Scrum: The Art of Doing Twice the Work in Half the Time. *They provide each employee with a copy.

Strive to find, "An ideal balance between abstract principles and concrete practices" - *Large Scale Scrum*

Scrum is a great place to start. Do it as outlined and consider other approaches like Kanban later. 

Scrum is not meant to be dogmatic. It should be adapted based on your learning. However people start adjusting too early. Do it properly first. Then experiment to adjust for problem areas within your organization. Otherwise you end up with the same old process under a new name.

For example, stand-up meetings, often end up being an hour at the conference table - then the team says they are wasting time. But really you aren’t doing short stand-ups the right way.

*Key practices:*

The team consists of a scrum master, a product owner and the team members. Everyone outside the scrum master and product owner is a team member. No team leads, no tech leads. The product owner is typically the client. 

Prioritize the backlog of "user stories" - the stories keep you honest and focused on delivering the things that actually benefit someone. The priorities are meant to make sure the things you need most are done first.

Timeboxing through short sprints that lead to shippable software. Make sure the tasks will lead to a build that can be used and tested.

Scrum ceremonies. Series of meetings with purpose. Ie. The whole team needs to meet with the product owner.

Retrospectives: ideally at the end of a sprint the team discusses what went well and what they could do better.

# Adjustments

Rangle learned as they went that prioritizing is the heart of scrum. Without this you start working on the things you want to work on. Then something more important comes up and you work on that. Nothing gets done this way. Make sure the most important thing really is the top priority for the week.

Figure this out by asking, "What would we work on if this was the last sprint?" or “Can we ship it? Why not?” These questions can lead to the answer of what is top priority.

More emphasis needed to be placed on working with the product owner. They are new to scrum most likely, so work to bring them onboard with the process. You need the right person to be the product owner. If they have to always go ask the boss and can’t make decisions themselves, they aren’t the best product owner. If on the other hand, the product owner is only available to talk once a month, that doesn’t work either. Need to strike a balance.

Much of the scrum master’s work is in dealing with the product owner. This can require flexible arrangements. Rangle prefers the product owner write the user stories, but sometimes, this is the wrong person. Can allow someone else in an organization to do this. 

*Handling the product owner’s commitments:*

Product owners will say, "We need all of this!" - the scrum master needs to push back on this and really uncover the actual needs - what promises were made to the product owner’s  superiors or clients so that you can help determine the priorities and needs accurately.

*Handling scope discovery: *

It often turns out there are things that are absolutely needed, but can be missed out on at the outset. Really need to work to understand what the full set of high level requirements are up front so you can make sure you prioritize pieces that are sometimes taken for granted. For example, building an online store, you should probably prioritize your payment system. You can likely manage without a cart, but if you aren’t taking in money, your business is failing hard.

*Building trust: *

Many people are too often used to working on software projects where everything goes wrong. They have no visibility of the project during development and are delivered a broken pile of junk in the end that fails to meet the client’s needs. This is where delivering early really helps. It shows that what you are doing has value and is actually working rather than just a show of smoke and mirrors until the end.

*Continuous Delivery:*

Working software reduces uncertainty and builds trust. Continuous integration ensures your software keeps working and isn’t broken with new releases. This relies on using a proper GIT workflow. Nothing fancy, simply be sure to always use reviewed pull requests for merging code. Review for code quality and that it works. This should be religion. Someone on the team is really looking to make sure this code will not break the software. In an ideal world, each pull request would trigger continuous deployment once committed. Depending on the scenario, this may be the live product, or in many situations, it’s a staging server. You know that within a few minutes of completing a merge, the product owner will have access to this new build.

*What happens to QA?*

If you do scrum by the book there are no roles. But there are certain people who really understand quality. Bring them in early so that the focus is on preventing defects, rather than fixing the problems that QA caught. If you have people involved from the start who are good at this, they can surface potential problems before you even start. 

Do testing within the sprint. Even better, do it within the pull request. Regardless of who does the testing, QA pros or dev team, the code should be tested before merging.

*The Project Kickoff*

People want to get new projects going quickly, yet there is a lack of common ground between the client and software developers. Often the client hasn’t yet established their common ground amongst themselves.

Rangle has established what they call Clarity Canvas - a process for establishing common understanding. They bring in numerous people from the client and dev team and run a series of workshops to run through the product needs.

*Lean UX*

An approach for avoiding the very long up front design time frame. Sometimes you have to deal with prior design. But ideally you want to work on the design requirements in a flow with the development sprints and priorities.

Make sure you talk to users - ideally within the sprint, so the feedback can be incorporated into the upcoming sprints.

Leveraging analytics. Finding the truth in user actions to inform decisions is also important.

*Process Hacking*

"Everybody does Scrum today. Nobody does Scrum today."

"Everybody does something they call “Scrum"”

There is a stigma around the name and terms associated with Scrum and Agile. Sometimes you just need to be creative about what you call things either internally or to the client.

