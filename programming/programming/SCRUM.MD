```
:terms
    feature
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
res
    https://www.scrumalliance.org/
```	