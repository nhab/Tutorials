```
## Feature
        :is a distinct function of the software which can provide capabilities to the business.
        Features are composed of Product Backlog Items and have target dates.

        :In agile development, a feature is a chunk of functionality that delivers business value. 
        Features can include additions or changes to existing functionality. 
        For planning purposes, some agile methodologies also use the notion of “work items”
        that can include features, bug fixes, documents, and other artifacts. 
        But features are the main unit of planning. 
        Ideally, a feature should adhere to the following criteria:
            - It should provide business value
            - It should be estimable
                – it must have enough definition for the development team 
                to provide an estimate of the work involved in implementing it
            - It should be small enough to fit within an iteration 
                – therefore, if it is too big, it should be broken down further
            - It should be testable
                – you should understand what automated or manual test a feature 
                should pass in order to be acceptable to the customer
    Feature Breakdown Structure (FBS)

        During detailed planning, agile development favors a feature breakdown structure (FBS) approach
        instead of the work breakdown structure (WBS) used in waterfall development approaches.
        Feature breakdown structures are advantageous for a few reasons:
            They allow communication between the customer and the development team in terms both can understand.
            They allow the customer to prioritize the team’s work based on business value.
            They allow tracking of work against the actual business value produced.
        It is acceptable to start out with features that are large and then break them out into smaller features over time.
        This allows the customer to keep from diving in to too much detail
        until that detail is needed to help facilitate actual design and delivery.

    User story
        =wish list of customer
        - informal statement in the language of the customer 
        -you can use to get feedback from your stakeholders and	find out if you are doing anything wrong.
    
    Product Backlog 
        :
        -Product Backlog Items are composed of Tasks and have estimated effort.
        -The Product Backlog items will then be ordered based on their business value,
        in a way that the higher an item is, the sooner it will be delivered by the Development Team. 
        -it is diffrent from feature list or Requirement in DSDM because it is in form of tasks list not feature list
    
    Sprint Planning event
    Velocity 
        :is measuring the rate at which scrum development teams consistently deliver business value. 
        To calculate velocity of your agile team,
        simply add up the estimates of the features, user stories, requirements or backlog items successfully delivered in an iteration.
    Initial Feature List
        Before release planning and iteration planning,
        the team needs to quickly draw up a list of as many potential features for the system as they can. 
        There is typically a single person responsible for collecting features
        (e.g. a Product Manager, a Customer, a Program Manager, Business Analyst, or some other customer proxy)
        , but feature requests can come from many sources. 
        Users, customers, Sales, Marketing, RFP’s, development team members, management, competitors,and Government regulations 
        can all be sources of features. 
        The team’s central feature list should have some controls to prevent duplicate items, 
        impossible features and overly vague requests. The team should be encouraged,
        however, to enter new features as they identify them, 
        so that they can be folded into the prioritization and planning process.

        An initial feature list can be a rough sketch, a superset,
        to be used as input for planning the release and first iteration.
        It represents the current potential of what the system could become,
        perhaps over several releases.
        You need not wait until all features are defined before getting started delivering software.
        And you need not adhere senselessly to the original list, original descriptions, or original priorities.
        One of the main points of agile development is that this list (like everything else) evolves, iteration by iteration
##  Roles
    Scrum recognizes only three distinct roles: product owner, scrum master, and team member:

###    Product Owner
        A development team represents a significant investment on the part of the business.
        There are salaries to pay, offices to rent, computers and software to buy and maintain and on and on. 
        The product owner is responsible for maximizing the return the business gets on this investment (ROI).

        One way that the product owner maximizes ROI is by directing the team toward the most valuable work, 
        and away from less valuable work. That is, the product owner controls the order, 
        sometimes called priority, of items in the team’s backlog. 
        In scrum, no-one but the product owner is authorized to ask the team to do work or to change the order of backlog items.

        Another way that the product owner maximizes the value realized from the team's efforts is to make sure
        the team fully understands the requirements.
        If the team fully understands the requirements, then they will build the right thing, 
        and not waste time building the wrong thing. The product owner is responsible for recording the requirements,
        often in the form of user stories (eg, “As a <role>, I want <a feature>, so that I can <accomplish something>”) 
        and adding them to the product backlog. Each of these users stories, when completed,
        will incrementally increase in the value of the product. 
        For this reason, we often say that each time a user story is done we have a new product increment.

####    The Product Owner Role in a Nutshell:

        holds the vision for the product represents the interests of the  business
        represents the customers
        owns the product backlog
        orders (prioritizes) the items in the product backlog
        creates acceptance criteria for the backlog items
        is available to answer team members’ questions
    
###     Scrum Master
        The scrum master acts as a coach, guiding the team to ever-higher levels of cohesiveness, self-organization, and performance.
        While a team’s deliverable is the product, a scrum master’s deliverable is a high-performing, self-organizing team.

        The scrum master is the team’s good shepherd, its champion, guardian, facilitator, and scrum expert.
        The scrum master helps the team learn and apply scrum and related agile practices to the team's best advantage.
        The scrum master is constantly available to the team to help them remove any impediments or road-blocks that 
        are keeping them from doing their work.
        The scrum master is not—we repeat, not—the team’s boss.
        This is a peer position on the team, set apart by knowledge and responsibilities not rank.

####    The scrum master role in a Nutshell:

        scrum expert and advisor
        coach
        impediment bulldozer
        facilitator
        
###     Team Member
        High-performing scrum teams are highly collaborative; they are also self-organizing. 
        The team members doing the work have total authority over how the work gets done. 
        The team alone decides which tools and techniques to use, and which team members will work on which tasks.
        The theory is that the people who do the work are the highest authorities on how best to do it. 
        Similarly, if the business needs schedule estimates, it is the team members who should create these estimates.

        A scrum team should possess all of the skills required to create a potentially shippable product. 
        Most often, this means we will have a team of specialists, each with their own skills to contribute to the team's success. 
        However, on a scrum team, each team member's role is not to simply contribute in their special area.
        The role of each and every team member is to help the team deliver potentially shippable product in each sprint. 
        Often, the best way for a team member to do this is by contributing work in their area of specialty.
        Other times, however, the team will need them to work outside their area of specialty in order to best move backlog items
        (aka user stories) from "in progress" to "done." What we are describing is a mindset change from "doing my job" to
        "doing the job."
        It is also a change in focus from "what we are doing" (work) to what is getting done (results).

####    The Team Member Role in a Nutshell:

        responsible for completing user stories to incrementally increase the value of the product
        self-organizes to get all of the necessary work done
        creates and owns the estimates
        owns the “ how to do the work” decisions
        avoids siloed “not my job” thinking
        So, how many team members should a scrum team have? The common rule of thumb is seven, plus or minus two. 
        That is, from five to nine. Fewer team members and the team may not have enough variety of skills 
        to do all of the work needed to complete user stories.
        More team members and the communication overhead starts to get excessive.
:? how to
    Common routine
        1 . Creating product backlog:
            A "product owner" creates a prioritized wish list called a product backlog.
        2 ."sprint planning"
            : During "sprint planning", the team pulls a small chunk from the top of that wish list,
            a . "sprint backlog", and B.decides how to implement those pieces.
        3.
            3 . 1 . The team has a certain amount of time — a sprint (usually two to four weeks) — to complete its work, 
            but it meets each day to assess its progress (daily Scrum).
            3 . 2 . Along the way, the ScrumMaster keeps the team focused on its goal.
        4 . At the end of the sprint, the work should be potentially shippable: ready to hand to a customer, 
        put on a store shelf, or show to a stakeholder.
        5 . The sprint ends with a sprint review and retrospective.
        6 . As the next sprint begins, the team chooses another chunk of the product backlog and begins working again.
    Accounting for Risk
        Additional consideration may be taken for the risk associated with certain features. Some features will involve designs, architectures, frameworks, or algorithms that are new to the team, or are otherwise risky. Even if such features do not deliver the highest business value, it often makes sense to bump their priority up enough to tackle them in early iterations. If a high-risk feature is addressed early in the project, and for some reason proves unworkable, the team still has time to react and work around it. This minimizes the overall risk to the project. It is up to the development team to work closely with the customer to help identify these types of issues, risks, and dependencies. It is ultimately up to the customer to prioritize features, but this critical process should not occur in a vacuum. The best teams work together to both deliver value and reduce risk throughout the life of a project.
    Estimating Features
        After identifying features, the customer often works with key development stakeholders to define feature estimates. Feature estimates are meant to be preliminary high-level estimates that are used to drive release planning and iteration planning. The stakeholders involved in estimating may include architects, tech leads, developers, testers, writers, and managers. Many organizations have set up processes where groups work together to quickly provide initial estimates. This step can be helpful in initially determining whether the feature should be broken down further.

        When initially estimating features, the goal is to quickly converge on a reasonable high-level estimate. Instead of focusing on whether a feature will require exactly 17.5 idea hours (or Gummi Bears, or NUTs, or whatever unit is being used; see below), the goal is to get reasonably close in a fraction of the time. If it takes 2 minutes to agree that the feature will take 2-3 ideal days to implement vs. 30 minutes to establish a precise 17.5 idea hour estimate, the former approach is preferred. To establish a single estimate when opinions in the group vary, teams can either take an average, develop a reasonable approximation, always use the best case scenario, or potentially use a calculation involving best case, worst case, and expected estimate if more complexity is appropriate. In any case, the discussions about differing estimates will often yield useful knowledge.

        This process of defining and estimating features can initially seem difficult, and when teams first implement it, they may require several meetings to get comfortable with a process that works well for them. Over time, it becomes easier to break down features into units of work that can be delivered within a single iteration. Teams get very good at what they practice and agile development allows teams to practice estimation every release and iteration.
        Estimation Units

        Estimates by their very nature are inaccurate. And developers have historically had difficulty producing useful estimates of all of the time required to complete a development task. Estimates of actual programming time are often inaccurate (especially if they are not rigorously compared to actual numbers). But non-programming time is even more difficult to nail down. What do you say if someone asks you how long it takes to drive across town? You use a relative measure. “An hour during non rush-hour, in good weather, if there is no construction, otherwise maybe 2 hours,” etc. These external factors are impossible to control and difficult to predict. In addition to developing code, programmers spend time testing, writing documentation, designing, participating in meetings and reviews, doing email, and so on. Compared to programming work, non-programmming work is difficult to predict or control. It can vary according to your industry, your organization, the time of year, and any manner of echanging xternal pressures on the organization.

        Some teams ask programmers to include each non-programmming activity in their estimates. But as we’ve said, this is not easy to do. For a given agile project, long before the team has an accurate measurement of time they spend doing non-programming stuff, they can know the relative work required to get different features done, and can plan accordingly. That’s why it is more typical of agile teams to focus their estimating on what can be most straightforwardly estimated and measured: actual programming. They focus on how much work each feature and each technical task will take, compared to other features and technical tasks. They allow the amount of time consumed by that non-programming stuff to become clear as actual velocity emerges after a few iterations. There are two main estimating units agile teams use to concentrate the focus on programming in this way:
            Work Units
            Ideal Time
        res: https://www.versionone.com/agile-101/agile-management-practices/agile-feature-estimation/
    Work Units

        A Work Unit is a relative measure that we hope cannot possibly be confused with actual time. Some such units:

            Points
            Gummi Bears
            Foot-Pounds
            NUTs (Nebulous Units of Time)

        These represent the relative amount of work required to implement a feature (or task), compared to other features (or tasks). Only once the team has settled into a consistent velocity, usually over a few iterations, can they begin to map these work units to units of actual time. That is exactly the point of velocity: to describe how much work the team can do per unit of actual time.

        Once the team or organization has agreed on an estimating unit, they should agree to make an effort to implement it consistently and stick to its original definition. Especially in the project’s early iterations, everyone should resist the urge to try to map these units to time units with any exact precision.
    Ideal Time

        Like Work Units, Ideal Time excludes non-programming time. When a team uses Ideal Time for estimating, they are referring explicitly to only the programmer time required to get a feature or task done, compared to other features or tasks. Again, during the first few iterations, estimate history accumulates, a real velocity emerges, and Ideal Time can be mapped to real, elapsed time.

        Many teams using Ideal Time have found that their ultimate effort exceeds initial programmer estimates by 1-2x, and that this stabilizes, within an acceptable range, over a few iterations. On a task by task basis the ratio will vary, but over an entire iteration, the ratios that teams develop have proven to remain pretty consistent. For a given team, a known historical ratio of Ideal Time to real time can be especially valuable in planning releases. A team may quickly look at the required functionality and provide a high level estimate of 200 ideal days. If the team’s historical ratio of ideal to real is about 2.5, the team may feel fairly confident in submitting an estimate of 500 project days. In fixed-bid scenarios, this kind of estimate can be reliable.
        Relative Estimation

        Many agile teams use the practice of relative estimation for features. Instead of estimating features across a spectrum of unit lengths, they select a few (3-5) relative estimation categories, or buckets, and estimate all features in terms of these categories.
        Feature vs. Task Planning

        While the emphasis at this initial stage of planning is on speed and on the relative work per feature, at some point features must be broken down to their respective tasks and estimated more precisely. This happens during release planning and iteration planning. We discuss these in more detail in separate articles. In general, feature estimates and task estimates serve different purposes:

            Feature estimates help drive scheduling across releases and iterations
            Task estimates help drive resource loading within an iteration

        Because they serve different purposes, a feature’s estimate need not align precisely with the sum of its task estimates.
        Over a range of features, however, there should be at least a rough correlation between feature estimates
        and the sum of the task estimates for the features.
        
Scrum Artifacts
These are the tools we scrum practitioners use to make our process visible.

The Product Backlog
The product backlog is the cumulative list of desired deliverables for the product. This includes features, bug fixes, documentation changes, and anything else that might be meaningful and valuable to produce. Generically, they are all referred to as “backlog items.” While backlog item is technically correct, many scrum teams prefer the term “user story,” as it reminds us that we build products to satisfy our users' needs.

The list of user stories is ordered such that the most important story, the one that the team should do next, is at the top of the list. Right below it is the story that the team should do second, and so on. Since stories near the top of the product backlog will be worked on soon, they should be small and well understood by the whole team. Stories further down in the list can be larger and less well understood, as it will be some time before the team works on them.

Each item, or story, in the product backlog should include the following information:

Which users the story will benefit (who it is for)
A brief description of the desired functionality (what needs to be built)
The reason that this story is valuable (why we should do it)
An estimate as to how much work the story requires to implement
Acceptance criteria that will help us know when it has been implemented correctly
The Sprint Backlog
The sprint backlog is the team’s to do list for the sprint. Unlike the product backlog, it has a finite life-span: the length of the current sprint. It includes: all the stories that the team has committed to delivering this sprint and their associated tasks. Stories are deliverables, and can be thought of as units of value. Tasks are things that must be done, in order to deliver the stories, and so tasks can be thought of as units of work. A story is something a team delivers; a task is a bit of work that a person does. Each story will normally require many tasks.

Burn Charts


A burn chart shows us the relationship between time and scope. Time is on the horizontal X-axis and scope is on the vertical Y-axis. A burn up chart shows us how much scope the team has got done over a period of time. Each time something new is completed the line on the chart moves up. A burn down chart shows us what is left to do. In general, we expect the work remaining to go down over time as the team gets things done. Sometimes the work remaining changes suddenly, when scope is added or removed. These events appear as vertical lines on the burn down chart: a vertical line up when we add new work, or down when we remove some work from the plan.

Task Board
When the team's tasks are visible to everyone from across the room, you never have to worry that some important piece of work will be forgotten.
The simplest task board consists of three columns: to do, doing and done. Tasks move across the board, providing visibility regarding which tasks are done, which are in progress, and which are yet to be started. This visibility helps the team inspect their current situation and adapt as needed. The board also helps stakeholders see the progress that the team is making.

Definition of Done
Done is a wonderful word; when the team gets a user story done it's time to celebrate! But sometimes there is confusion about exactly what that word "done" means. A programmer might call something done when the code has been written. The tester might think that done means that all of the tests have passed. The operations person might think that done means it's been loaded onto the production servers. A business person may think that done means we can now sell it to customers, and it's ready for them to use. This confusion about what "done" means can cause plenty of confusion and trouble, when the salesperson asks why the team is still working on the same story that the programmer said was done two weeks ago!

In order to avoid confusion, good scrum teams create their own definition of the word "done" when it is applied to a user story. They decide together what things will be complete before the team declares a story to be done. The team's definition may include things like: code written, code reviewed, unit tests passing, regression tests passing, documentation written, product owner sign-off, and so on. This list of things that the team agrees to always do before declaring a story done becomes the teams "definition of done." The team will likely print out their definition of done as a checklist, and post it next to their task board. When the team thinks a story is done, they all gather around and review each item, to confirm that it has been completed. Only then will the team declare the story as done.

The Sprint Cycle


The sprint cycle is the foundational rhythm of the scrum process. Whether you call your development period a sprint, a cycle or an iteration, you are talking about exactly the same thing: a fixed period of time within which you bite off small bits of your project and finish them before returning to bite off a few more. At the end of your sprint, you will be demonstrating working software or thy name is Mud.

The more frequently the team delivers a potentially shippable product increment, the greater freedom the business has in deciding when and what to ship. Notice that there are 2 separate decisions here:

Is the product potentially shippable? That is to say, is the quality high enough that the business could ship it? Are all of the current stories done? This is a decision for the team.
Does it make business sense to ship what we have at this time? Is there enough incremental value present to take the current product to market? This is a decision for the business.
Additionally, the more frequently the team delivers and demonstrates a potentially shippable product increment, the more frequently the team gets feedback, which fuels the important inspect-and-adapt cycle.  The shorter the sprint cycle, the more frequently the team is delivering value to the business.

As of this writing, it is common for scrum teams to work in sprints that last two weeks, and many teams are starting to work in one-week sprints. Much of the original writing about scrum assumed a month-long sprint, and at the time that seemed very short indeed!

The table below maps out the various meetings you would schedule during a one-week sprint. You don’t have to call them meetings if you’re allergic to the term or consider meetings to be a form of repetitive stress injury; you can call them ceremonies, as many scrum adherents do. The meeting lengths shown are an appropriate starting point for a team doing one-week sprints.



Sprint Planning Meeting
Sprint planning marks the beginning of the sprint. Commonly, this meeting has two parts. The goal of the first part is for the team to commit to a set of deliverables for the sprint. During the second part of the meeting, the team identifies the tasks that must be completed in order to deliver the agreed upon user stories. We recommend one to two hours of sprint planning per week of development.

PART ONE: “WHAT WILL WE DO?”
The goal of part one of the sprint planning meeting is to emerge with a set of “committed” stories that the whole team believes they can deliver by the end of the sprint. The product owner leads this part of the meeting.

One by one, in priority order, the product owner presents the stories he would like the team to complete during this sprint. As each story is presented, the team members discuss it with the product owner and review acceptance criteria to make sure they have a common understanding of what is expected. Then the team members decide if they can commit to delivering that story by the end of the sprint. This process repeats for each story, until the team feels that they can’t commit to any more work. Note the separation in authority: the product owner decides which stories will be considered, but the team members doing the actual work are the ones who decide how much work they can take on.

PART 2: “HOW WILL WE DO IT?”
In phase two of the sprint planning meeting, the team rolls up its sleeves and begins to decompose the selected stories into tasks. Remember that stories are deliverables: things that stakeholders, users, and customers want. In order to deliver a story, team members will have to complete tasks. Task are things like: get additional input from users; design a new screen; add new columns to the database; do black-box testing of the new feature; write help text; get the menu items translated for our target locales; run the release scripts.

The product owner should be available during this half of the meeting to answer questions. The team may also need to adjust the list of stories it is committing to, as during the process of identifying tasks the team members may realize that they have signed up for too many or too few stories.

The output of the sprint planning meeting is the sprint backlog, the list of all the committed stories, with their associated tasks. The product owner agrees not to ask for additional stories during the sprint, unless the team specifically asks for more. The product owner also commits to being available to answer questions about the stories, negotiate their scope, and provide product guidance until the stories are acceptable and can be considered done.

Daily Scrum
The daily scrum, sometimes called the stand-up meeting, is:

Daily. Most teams choose to hold this meeting at the start of their work day. You can adapt this to suit your team’s preferences.

Brief. The point of standing up is to discourage the kinds of tangents and discursions that make for meeting hell. The daily scrum should always be held to no more than 15 minutes.

Pointed. Each participant quickly shares:

Which tasks I've completed since the last daily scrum.
Which tasks I expect to complete by the next daily scrum.
Any obstacles are slowing me down.
The goal of this meeting is to inspect and adapt the work the team members are doing, in order to successfully complete the stories that the team has committed to deliver. The inspection happens in the meeting; the adaptation may happen after the meeting. This means that the team needn't solve problems in the meeting: simply surfacing the issues and deciding which team members will address them is usually sufficient. Remember, this meeting is brief!

Story Time
In this meeting you will be discussing and improving the stories in your product backlog, which contains all the stories for future sprints. Note that these are not the stories in the current sprint–those stories are now in the sprint backlog. We recommend one hour per week, every week, regardless of the length of your sprint. In this meeting, the team works with the product owner on:

Acceptance Criteria

Each user story in the product backlog should include a list of acceptance criteria. These are pass/fail testable conditions that help us know when then the story is implemented as intended. Some people like to think of them as acceptance examples: the examples that the team will demonstrate to show that the story is done.

Story Sizing (Estimation)

During story time, the team will assign a size (estimate, if you prefer that term) to stories that haven’t yet been sized. This is the team's guess at how much work will be required to get the story completely done.

Story Splitting

Stories at the top of the product backlog need to be small. Small stories are easier for everyone to understand, and easier for the team to complete in a short period of time. Stories further down in the product backlog can be larger and less well defined. This implies that we need to break the big stories into smaller stories as they make their way up the list. While the product owner may do much of this work on their own, story time is their chance to get help from the whole team.

As of this writing, the story time meeting isn’t an 'official' scrum meeting.  We suspect it will be in the future, as all of the high performing scrum teams we know use the story time meeting to help keep their product backlog groomed.

Sprint Review
This is the public end of the sprint; invite any and all stakeholders to this meeting.  It's the team's chance to show off its accomplishments, the stories that have met the team's definition of done.  This is also the stakeholders’ opportunity to see how the product has been incrementally improved over the course of the sprint. 

If there are stories that the team committed to but did not complete, this is the time to share that information with the stakeholders. Then comes the main event of this meeting: demonstrating the stories that did get done. Undoubtedly the stakeholders will have feedback and ideas, and the product owner and the team members will gather this feedback, which will help the team to inspect-and-adapt the product.

This meeting is not a decision-making meeting. It's not when we decide if the stories are done; that must happen before this meeting. It's not when we make decisions or commitments about what the team will do during the next sprint; that happens in sprint planning.

How long should the sprint review be? We recommend scheduling one-half to one hour for every week of development. That is, if you have a one-week sprint, then this meeting might be 30 – 60 minutes. If you have a two-week sprint, then this meeting might need one to two hours. After you have done it a few times, you will know how long your team needs–inspect and adapt!

Retrospective
While the sprint review is the public end of the sprint, the team has one more meeting: the retrospective. Scrum is designed to help teams continuously inspect and adapt, resulting in ever-improving performance and happiness. The retrospective, held at the very end of each and every sprint, is dedicated time for the team to focus on what was learned during the sprint, and how that learning can be applied to make some improvement.  We recommend one to two hours of retrospective time for each week of development.

Unlike the traditional “post mortem,” the aim of a retrospective is never to generate a long laundry list of things that went well and things that went wrong, but to identify no more than one or two strategic changes to make in the next sprint. It’s about process improvement.

Abnormal Sprint Termination: When Good Sprints Go Bad
In scrum, the basic agreement between management and the team is that management won’t change up requirements during a sprint. Still, every once in a while something happens that invalidates everything in the sprint plan—a business is sold, a game-changing technology enters the market, a competitor makes a move. The decision to terminate the sprint early is fundamentally a business decision, so the product owner gets to make the call on an “abnormal sprint termination.” Despite the name, neither Arnold Schwarzenegger nor James Cameron need get involved.

If the product owner does decide to terminate the sprint early, the team will back out any changes that they have made during the sprint to avoid the problems that come from half-done work. Holding a retrospective is especially important after a sprint is abnormally terminated, as it helps the team learn from the experience.

res
    https://www.scrumalliance.org/
```	
