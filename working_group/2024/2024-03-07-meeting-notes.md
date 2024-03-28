# 2024 March 7 - Meeting notes

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**
  - Reminder that our new meeting cadence is the 1st and 3rd Thursday. See the [Salt Project community calendar](https://saltproject.io/calendar/) for specific dates and the Zoom link.
  - Our next meeting is on March 21.
  - [Salt 3007 is released!](https://saltproject.io/blog/salt-release-3007-is-now-available/)
- **Update from Alyssa from engineering**
  - After our last meeting, Alyssa took some of the working group's concerns to the engineers as well as the professional services and support teams at Broadcom for feedback.
  - When we get closer to the 3008 release, we have an agreement from engineering to have a really long release candidate (RC) period. Because the Salt extensions will be such a large change to the release, we've gotten agreement from the engineering teams, support teams, and professional services teams to do a thorough job of testing the impacts of the Salt extensions. Our goal will be to fully understand the impacts, to create a "happy path" to installation, to think through documentation, and more. So, you'll have the support from Broadcom for that RC period. Meanwhile, this working group can continue exploring and share any problems that we discover with those teams and hopefully make the process better for everyone.
  - Question: Can we have a pre-announcement before the code freeze period?
    - The core team was supportive of this idea, at least 2 weeks but possibly up to a month.
- **Update on salt-pip bugfix**
  - Recap from our previous meeting: Installation of Salt extensions has a blocker because you can't install more than one extension at a time with salt pip. Bootstrap would be the most effective installation method, but it could cause a race condition when you run minions on a highstate.
  - See this [merged relenv PR](https://github.com/saltstack/relenv/pull/173). It was in 3006.7 and it was also merged forward into 3007 as well. We encourage you to give that one a go.
  - Gary is working on a PR, but is a little delayed trying to get the tests to work.
  - Question: Speaking of testing, does anyone have the link to the Docker image that Terminalmage maintains for testing?
    - Yes: https://github.com/terminalmage/salt-docker/
    - The Docker image is great if you want to run all the tests, but don't necessarily want to run all of that on your laptop.
- **Feedback to the core Salt team about the modules**
  - Any concerns about this list that we need to raise with the core Salt team?
  - We need more clarity around what criteria is used to determine which module goes in which category.
  - It would be nice to know when the cut will occur for this PR: https://github.com/saltstack/salt/pull/65971
    - **Action:** Alyssa will follow up with dwoz to get a solid commitment. Alyssa will coordinate with Chunga about when to announce the PR is getting merged in. She will also clarify where those discussions can occur about the modules.
    - **Update a few days later:** Alyssa took an action item to find out the deadline for commenting on which modules go into which category (core, core extensions, and community extensions). Dwoz is hoping to merge in his PR with all the changes some time next week, so that's the timeline. The more eyes we can get on it, the better. So, get your comments in soon.
- **Discussion about Max's proposal to keep centralized documentation**
  - See [Keep the centralized module documentation at docs.saltproject.io](https://github.com/saltstack/salt/discussions/66144) on GitHub discussions.
  - Decision: We'll table this discussion item for the next meeting so that Derek can attend and provide insights.
- **Automation and testing for community extensions**
  - Murphy: If we could get the GitHub Actions tested and validated, that could be helpful for community extensions. Each community extension will be a law unto itself, so we'll need to make sure it's adequately tested.
  - Nick: Maybe instead the core team could take a look at what we're building and see if it fits the bill for what you are building. I've created a central artifacts repository which has all of the GitHub actions and they're all called as remote tasks. They're all running a centralized list instead of duplicating those YAML files; they're calling them from the central artifacts repository. So, that way it's not a situation where each one is doing it a different way. We have consolidated on one set at this point.
  - Max: It would be nice to schedule nightly tasks against the daily build for the extensions. That would ensure that every extension is tested nicely against the current main branch of Salt.
  - Murphy wasn't sure that the organization could pay for those tests.
  - Nick: From the perspective of the extensions, the extension shouldn't care about what is going on in Salt unless the interfaces have changed. How important is it to have nightly tests against the framework? How often would a scenario happen where the extension is broken by the Salt framework?
  - Max: We don't really know yet, but the formulas group has been able to do some early detection of problems. Perhaps that same principle could be applied here.
  - Nick: We'd have to identify which things would be most likely to cause an extension to break. Most remote execution modules will likely just work. But there could be changes in state modules, renderer modules, or utils that could cause problems.
  - In terms of costs, if it's in the community, it should work, but it will be throttled after it hits a maximum limit.
  - Alyssa: How do we validate that an extension is meeting our testing requirements?
- **Nick demoed his concept for a common community extensions org run by the community**
  - Nick: What we're trying to do is encourage people to come and host their extensions in our organization as part of our repos. The goal here is to resolve any issues people might have while working with extensions. Everyone can release them where they want, but we'd like to promote our path as a way to help people find community extensions and get the necessary documentation, release workflows, or other tools they might need.
  - Note: You can watch the recording of this working group meeting for Nick's demo of how the testing and other workflows currently work. (Link is at the top of the document.)
  - For people who prefer to host on GitLab, they could create a stub repository that points to GitLab or other sources for people who don't want to host in this org, but still want to be findable.
  - It would be great if we could delegate and get some extra help maintaining this org.
  - What are current blockers for people using this method?
    - Gary: GitLab is a big blocker because they have much better pipelines and it's difficult to replicate those in GitHub. But Nick's centralized testing model is appealing.
    - Melissa: Azure pipelines are my blocker.
  - How do people get their extension in here? Right now, Nick creates the repository and makes people the maintainer to help facilitate moving them into the framework we've established. It's not necessarily scaleable and we need some onboarding documentation.
  - Is there a CLA? Not currently. If we do decide to have different licenses outside of Apache, we should have badges that declare their license.


## Notable links

- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/