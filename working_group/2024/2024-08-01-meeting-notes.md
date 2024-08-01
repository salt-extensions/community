# 2024 August 01 - Meeting notes

## Attendees

- David
- Melissa
- Max
- Shane

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**
    - Introduction of David Murphy taking over from Alyssa, due to her leaving Broadcom.

- **What is the plan for core extensions? Will the core maintainers be responsible for those extensions and when are they coming out?**
    - Yes, the core maintainers will continue to maintain those extensions. They are not going to come out for the 3008 release. The core team first needs to set up the infrastructure to pull them out (such as testing, documentation, installation methods). The good news is that the necessary infrastructure is exactly what the community needs as well, so the core team can work together with the community to find good solutions.

- **Which process should people (be able to) follow to include a fresh extension (not a ported one) into the org?**
    - The core tool (https://github.com/saltstack/salt-extension) is being deprecated, archived with a message redirecting users to the superior copier tool (https://github.com/salt-extensions/salt-extension-copier)

- **Where are we in the process of module migration? Is anyone still actually working on porting modules? Also: How can we minimize friction in this process and most effectively prioritize work?**
    - David used copier to make core extension for Cassandra, and generated issues for additional files, for example: CODE-OF-CONDUCT.md

- **Is there anything that can be done to ensure the organization stays healthy in the absence of Nick?**
    - Nick who unfortunately been missing in action for several months now, has Max and Jean-Luc co-maintainers
    - Need to update Salt Extensions page Slack to Discord

- **Should the `salt-extension` tool be retired in favor of the Copier template?**
    - Done, Shane took an action item to mention the need to deprecate the core tool in favor of the superior copier tool

- **Discussion of Reddit article on purge of community extensions**
    - Max raised following issues:
      - Missing extensions when 3008 is released and where to direct people
        - David dicussed possible execution list of moved to salt-extensions functionality that is directly loaded when  3008 is installed, but there is the problem of unwanted functionality, perhaps those could be split into sections, for example: database, network, etc.
      - Extensions Maintainence, PR's, Issues, et al. Ensuring that these are addressed in timely manner
      - Best place for questions, this should be Discord Salt Extensions Channel (https://discord.com/channels/1200072194781368340/1208165123240370197) for noobie and experienced.
      - PyPI steps for uploading to, see (https://github.com/salt-extensions/salt-extension-copier/issues/15), should have simple steps with link to advanced options (PyPI Instructions)
      - Documentation for individual salt-extensions, need to have document generated automated by CI/CD, and loaded into their GitHub Pages. Should also as part of accepting a new extension into the Salt Extensions repositories, ensure that the extension has adequate documentation (not a measure of its quality, but that it exists sufficiently)

- **Discussion of next steps with this working group.**
  - **Discussion of Reddit article on purge of community extensions**
      - Max raised following issues:
        - Missing extensions when 3008 is released and where to direct people
          - David dicussed possible execution list of moved to salt-extensions functionality that is directly loaded when  3008 is installed, but there is the problem of unwanted functionality, perhaps those could be split into sections, for example: database, network, etc.
        - Extensions Maintainence, PR's, Issues, et al. Ensuring that these are addressed in timely manner
        - Best place for questions, this should be Discord Salt Extensions Channel (https://discord.com/channels/1200072194781368340/1208165123240370197) for noobie and experienced.
        - PyPI steps for uploading to, see (https://github.com/salt-extensions/salt-extension-copier/issues/15), should have simple steps with link to advanced options (PyPI Instructions)
        - Documentation for individual salt-extensions, need to have document generated automated by CI/CD, and loaded into their GitHub Pages. Should also as part of accepting a new extension into the Salt Extensions repositories, ensure that the extension has adequate documentation (not a measure of its quality, but that it exists sufficiently)


## Next steps

- Next meeting is September 5th.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
