# 2024 June 6 - Meeting notes

## Attendees

- Alyssa
- Daniel (Dwoz)
- Dafydd
- David
- Max

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist:
https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- Question for the group: for the summer time when people tend to go on a lot of vacations, should we drop to a  once a month cadence?
  - We didn't have enough people present to make this decision, but Alyssa will circle back with Nick and then make a final decision.
- Today's agenda is: In this meeting, let's talk about any serious concerns about the Salt Extensions project in general that you would like to discuss with this working group. Main area of concerns:
- **Risk**
  - The [great module migration PR](https://github.com/saltstack/salt/pull/65971) impacted around half a million lines of code. To me, that's a very large change and the possibility that unforeseen problems will occur as a result of this change is approaching near certainty. We also won't be able to fully anticipate or know what the problems will be in advance just because the change is so large.
  - For example, many people will discover they were using some of those extensions and suddenly their systems will start breaking. So we'll suddenly get a lot of requests for how to get those extensions back into their system. That then leads into my second area of concern, which is...
- **Installation**
  - Once people realize that several extensions they relied on were ported out to the extensions repository, they will ask how they can easily restore them and get them back so that they can "stop the bleeding" and the immediate pain in their system. Can we make that process easy and lightweight?
  - Also, how do they know that missing extensions are the root of the problem in their system? Will there be effective error messaging to help point them realize that it's not working because the extension is missing now?
- **Documentation and discovery of new extensions**
  - How do we make it so that people can easily discover new extensions as we move away from a mono-repo model to a distributed multi-repo model?
  - How do they get access to the documentation for those extensions so that they can effectively use those extensions?
- **Can maintainership scale?**
  - A lot of the people who are volunteering to maintain extensions are doing this in their spare time. Is there a way that we can make our maintainership processes scale?
- **Developing a plan B and considering making 3008 an STS release instead:**
  - Max: The project seems to lack sufficient resources to ensure the project is ready before the 3008 release in October. I think we should develop a plan B in which we assume that the community extensions will not be extracted, supported, and tested as an extension in time for that release.
  - Dwoz: I also don't expect that all the community extensions will be maintained by then.
  - Max: If that's the case and we all agree that it's a given, then we need to set expectations and begin communicating right away so that people don't upgrade blindly and start discovering that modules are no longer there. And maybe we should work on a path for getting the modules back in a quick way, such as getting them back into the state tree quickly. Then we could direct them to the porting process and encourage them to participate in the maintenance project.
  - David: We should consider changing 3008 from an LTS release to an STS (short-term) release to better signal that it is less well-tested. Maybe 3009 should instead be the LTS release.
  - Max: I agree. 3008 will likely have a lot of breaking features and making it an LTS would be risky.
  - Alyssa: I like this plan because it buys us time. What would it take for us to have confidence that a release that removes all the extensions be good enough for an LTS release? What blockers would we need to resolve to have a LTS release with the extensions removed?
  - Dwoz: For me, I think I'd like to see 3006 be more stable first. I'd like to see a state where those bugs were resolved and there were not new ones going in.
- **Community and core team support**
  - Dafydd: My thoughts are that we would need a large investment of manpower in the Salt Extensions project from the community or the core Salt team and I'm not entirely sure that's available at the moment.
  - Dwoz: Yes, part of the impetus of this project itself is to push the community to take more ownership over the maintenance of the project. The way I see it, it's part of the core team's responsibility to enable anything that needs to happen in the code. So that involves making sure that pip-install works, that changes in the code base don't break any extensions, and so on. But then the community would take on the actual work of maintaining the extensions, writing all the tests, and worrying about the packaging. And that's the point of pulling these out: to force the people who actually do use them to shoulder the burden of maintaining them. Breaking the system is part of the wake-up call. When they ask us who is maintaining it, we say: no one. It will be up to the person who needs it or someone else, but it won't be the core team.
  - Alyssa: I don't mind that vision of the future all that much. The only thing I would say is that we would need ot have a way to catch those people when they ask that question and get them into the maintainership system. I would love it if when they ask who will maintain it, we could say: "Well, you could maintain it. And there's an easy path to get there. Here's the path: join this meeting, hook into this process and workflow, connect with the leaders of this program..." We're not there today, but I think there's possibly a way to get there.
  - Dwoz: A lot of that is going back to what Max was saying around communication and documentation.
- **Maintaining the core extensions**
  - What is the plan for maintaining the core-maintained extensions?
  - Dwoz: We plan to keep maintaining them for the foreseeable future. Whether they stay in the core codebase in the future is difficult to say. At some point we would like to start pulling them out, especially some of the big ones. But right now, we're still acclimating to the changes that occurred from removing the community extensions. It will be a long time out first.
- **Extension template**
  - Max: I pointed the people to the extension template and it broke. Then the community pointed them toward the community copier template.
  - Alyssa: If memory serves, it seems like we agreed in a past meeting that the community maintained copier template is now the superior template and we should probably deprecate the core maintained one.
- **Testing the release candidate**
  - Max: Can we make the release candidate available 2 months before the release to ensure it is adequately tested?
  - Dwoz: It's too early to agree to that. I agree we need to have a decent amount of time for RCs, but also historically people don't test our RCs. We give time, we give announcements (and we'll continue to do that), but I'm skeptical that people will robustly test our RC.
  - Alyssa: In this case, I feel like it's a tragedy of the commons where in order to have a good release, we need adequate testing of the RC in production. But when people test the RC, they are assuming a certain amount of work and risk in doing so. And so we don't get adequate RC testing because the incentives aren't there. But then when the official release occurs, that's whey they do the testing and then get mad that things broke.
  - Dafydd: I have tested RCs in the past and the problem I have is that there is a different installation process, so you really have to go out of your way to install an RC. So, the process of installing an RC needs to be made easier.
  - Alyssa: Do you think if rollback was easier that would help too?
  - Dafydd: Possibly.
  - Max: If an early release candidate isn't an option, are there nightly builds? Are they only for the master branch?
  - Dwoz: Yes. But we only cut a release branch when we get close to an RC. Once we have an RC, nightly builds will be available.
- **Exploring what happens if we make 3008 an STS or an LTS release**
  - Alyssa: So, I like the idea of making 3008 an STS release in order to buy time and give the community a chance to rally, to build the workflows and processes necessary to support the maintainership program. However, we would also be kicking the can down the road a bit. We do need people to try a version of Salt without the extensions in production to begin surfacing the problems, too. Thoughts on that?
  - Max: Well, if 3008 is an LTS release, will the core Salt team be able to iterate on it and release point releases fast enough to respond to the problems?
  - Dwoz: For me, that's why I think our focus for now should be on stabilizing the process for 3006 as much as possible. If we could get everything fixed as much as possible in 3006, that would give us a clean baseline for comparison. Then we could make a decision about 3008 later, perhaps on the August timeframe.
  - Max: Would there be problems upgrading and jumping over a release from 3006 to 3008? 3007 also had some major changes. Would it be too drastic?
  - David: I don't think it would be too drastic. The big change is more around the removal of the extensions.
- **Scaling maintainership**
  - Alyssa: So we identified earlier that the extensions project is mostly going to succeed if the community rallies around this project and agrees to take on more of maintaining extensions. Is this the kind of problem where we need to get more people into this group as maintainers or is the problem one where we need to build out the "engine" (the system of workflows and processes) for maintaining extensions and then bringing people in? My hunch is that its the later. We need to build the engine first, and then we can bring more maintainers in at scale.
  - Dafydd: My question is where are all the other companies in this? You hear all the time about big companies that use Salt, but we never see them here in the community playing an active role in contributing to the project, which is important to the overall health and life of the project. Don't they have a vested interest in this transition succeeding? Where are they?
  - Dwoz: We do have a large group of people from other companies that make contributions, but there's also a very large contingent of users who are purely consuming it. They may not even be technically inclined enough to make contributions.
  - Max: Could Broadcom make a list of these companies and invite them explicitly into this process, whether it be the Salt Extensions project or the project in general?
  - Alyssa: It seems like a model worth exploring. There are companies I can think of that specifically pay for developers to contribute to open source project that are business critical for them. One example is Facebook (Meta), which pays developers to contribute directly to React, since their business relies on them.
- **Advice from the core team**
  - Alyssa: So, we've spoken at length today about how the success of this project will depend on the strength of our community and whether they rally around this project or not. For the core team, if you were giving advice to this group on what they should focus on first in order to increase the chances that this will succeed, what advice would you give?
  - Dwoz: I think a good place to start would be building out the copier template, then coming up with a solid way to get testing in place on an extension. Automated testing and releases would be pretty crucial to lowering the burden to testing and releasing. Those are the same things we've been working on in Salt, so it applies here as well.
  - David: We should all use the same tools for getting and extracting the extension and we should all use the same tool for testing. The infrastructure for pulling those tests in should all be the same so that we're all testing similarly. That would be better than having many disparate testing environments. If there was a way to do the builds and the extraction framework where you're essentially plugging in your extension (tests and source code) and then it executes it to build it and run the tests. It should also throw errors if there are no tests provided. It could also give out code coverage results so that we could see how well the extension has been tested. I fear that we'll have to spend more time building out this infrastructure for the community than we'll have time to develop new features for Salt.


## Next steps

- Next meeting is June 20.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
