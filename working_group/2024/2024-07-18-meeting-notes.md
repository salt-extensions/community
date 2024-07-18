# 2024 July 18 - Meeting notes

## Attendees

- Alyssa
- Shane
- Max
- Jerry
- Melissa

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist:
https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**
  - Today we're announcing a change in working group leadership. Alyssa has left Broadcom to go work for another company and is stepping down as one of the working group leads. David Murphy will take over in her place.
- **What is the plan for core extensions? Will the core maintainers be responsible for those extensions and when are they coming out?**
  - Yes, the core maintainers will continue to maintain those extensions. They are not going to come out for the 3008 release. The core team first needs to set up the infrastructure to pull them out (such as testing, documentation, installation methods). The good news is that the necessary infrastructure is exactly what the community needs as well, so the core team can work together with the community to find good solutions.
- **Which process should people (be able to) follow to include a fresh extension (not a ported one) into the org?**
  - Gareth created a tool for extension migration. It works okay, but Max thinks it needs some tweaks. One nice thing about that tool is that it preserves the Git history..
  - In terms of porting existing extensions vs. creating a net new extension, there isn't really a substantial difference between the process. The same process can be used for both scenarios.
- **Where are we in the process of module migration? Is anyone still actually working on porting modules? Also: How can we minimize friction in this process and most effectively prioritize work?**
  - Comment from Jean-Luc: Automation mostly works fine from my experience with saltext-vault and saltext-pushover, awareness/documentation is lacking, possibly interest as well
  - Alyssa feels like the goal should be to make the process as easy as possible and have a clear happy path to maintaintership. Once that happy path is in a good place, the community should work with Chunga to evangelize the process and raise awareness, encourage maintainership.
- **Is there anything that can be done to ensure the organization stays healthy in the absence of Nick?**
  - Nick has unfortunately been missing in action for several months now, not responding to emails or messages. This is a problem because no one can merge anything into his [Salt extensions org](https://github.com/orgs/salt-extensions/). He is one of the only maintainers, along with Miguel Diaz, who is not on the Discord server. We agree that this doesn't necessarily bode well for his proposed centralized model of commmunity extension maintainership.
  - In the best case scenario, hopefully Nick will return soon and will be open to having conversations about expanding org rights to trusted members of the community, such as Max or Jean-Luc.
  - In the worst case scenario, we might have to switch to a decentralized model in which everyone maintains their own extension. This model is less than ideal because it loses some of the benefits from discoverability, standardized testing infrastructure, and documentation hosting. It also would result it duplication of work.
  - Hopefully Nick will return eventually and can engage in this discussion.
- **Should the `salt-extension` tool be retired in favor of the Copier template?**
  - Having two tools causes confusion (https://github.com/saltstack/salt-extension/pull/49#issuecomment-2155450876) Context: https://github.com/saltstack/salt-extension/pull/45#issuecomment-1919464696
  - **Action:** Shane took an action item to mention the need to deprecate the core tool in favor of the superior copier tool at the next core standup.

- Discussion of next steps with this working group.

## Next steps

- Next meeting is August 1.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
