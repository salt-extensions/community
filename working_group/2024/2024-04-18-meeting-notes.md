# 2024 April 18 - Meeting notes

## Attendees

- Nick
- Alyssa
- Max
- Shane
- Gary
- Melissa
- Keisha
- Amarques

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist:
https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**
  - Open Hour is today!
  - The Great Module Migration got merged: https://github.com/saltstack/salt/pull/65971
    - If Nick gets a chance, he might go back and compare how the final PR matched up with the initial list that Gareth shared.
- **Recap from last meeting**
  - Meghann came up with an automated way for us to have static pointers to the main core Salt documentation, but also dynamically pull in extension documentation as well. It assumes a distributed location of module documentation that is pulled into the central documentation location; it then links out to the external documentation. She put in some PRs with the work to date and it puts the groundwork in place for us to come up with a good solution. See the recording for the previous meeting for a demo and in-depth discussion.
  - One nice thing about her work is that it could possibly also gather in notes from other working groups if those groups keep their notes in Markdown. Then, we could have them all in one centralized repository for all things community.
- **Proof of concept for metadata structure**
  - See https://github.com/max-arnold/salt-extensions-metadata/
  - The concept here is that we could have a yaml file that is placed in the repository for the extension. It could possibly be added to the copier tool for all new extensions. It could include the long description of the module, the documentation location, and so forth.
  - Max explained how it worked on a technical level. It auto-generated based on data queried from PyPi and builds a directory for each extension it finds.
  - He mentioned the difficulties in not having a single source of truth and trusting whether the data is trusted and valid. Those fields would have to be reviewed by a person.
  - Nick: We should consider making sure things are properly categorized to reflect differing levels of trust (core maintained ones, validated ones, etc.) We could make another category that could be a self-creating awesome list but which aren't yet vetted. Make sure it's clear when it's not vetted.
  - Max: I suggest putting all the parsers that scan sources for an extension into this repo and the end result could be a pull request that is reviewed by a person.
  - How can we establish which modules are trusted?
    - Max: The origin (source) is probably one of the primary methods, which indicates where it was discovered. It could be manual, which means automation can't update it. The second origin could be from GitHub and this metadata could be updated automatically, so it could pull metadata from the GitHub about maintenance data. The third origin is GitLab. We could add as many additional origins as we want.
  - Centralized metadata or distributed?
    - Nick: This metadata schema could have pieces of it living in different places. We could have a central spot that is looking at the Salt extensions org in GitHub and we build documentation links if we don't currently have them in the list already. The biggest problem is that we don't really know very much about the extension other than we found it. So the metadata in that case was something that was to be distributed amongst the different repositories and they could have the metadata in theirs and we could get some additional information. The upshot is that some amount of metadata needs to exist in the repository themselves, but we could do some metadata that we do at a central location. So a combination could work well.
    - Max: I hadn't considered a distributed metadata but instead built my proof of concept using only existing metadata from PyPi. I'm not sure we can rely on extension maintainers to keep their up to date. The security comes from having a human reviewer.
    - Nick: I worry about the scalability of having a human reviewer, so I'd prefer something where we could understand the trust level with more fidelity. Scanning the orgs themselves gives us the assurance that only people with authority to open PRs themselves have our trust.
  - **Action:** Nick will take a look at the initial proof of concept is done and maybe think about how it could be integrated into the Salt extensions workflow and the work that Meghann did.
- **Brainstorming initiatives**
  - Alyssa: Maybe we could create as-is/to-be end-to-end workflows for both the Salt extension maintainer and Salt extension user, then identify the pain points and work on those?
  - Nick: The problem with that idea is that things are in such a state of flux that the "as-is" is a little bit a dumpster fire right now.
  - Alyssa: What's the biggest pain point and where could we start?
    - Max and Gary felt like the biggest pain point was the necessity of writing unit tests. There's a lot of automation available in salt factories, but it's not documented and it's hard to understand what helpers are available. We're also not sure if it's stable. So far, people just come to Slack or Discord to ask questions, but it seems like something better could be possible.
    - Gary: Wayne's test clinics were helpful, but they weren't well-viewed. Discord seems to be less active.
    - Nick: It does seem quieter on Discord, but Stack Overflow and Reddit seemed to have picked up since the transition to Discord.
    - Max and Gary both felt this was the number one impediment to merge requests.
  - Nick: On first blush, I'd say firming up the frameworks and helpers for helping people creating extensions and then creating extensions for all the things that have been ripped out and ask for some help from the community to get some help.
  - Gary: My priorities largely mirror Nick's: 1) Make extensions easier to create (helper scripts, etc), 2) Make extensions discoverable.

## Next steps

- Nick will take a look at the initial proof of concept is done and maybe think about how it could be integrated into the Salt extensions workflow and the work that Meghann did.
- We'll continue talking about these initiatives next time.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
