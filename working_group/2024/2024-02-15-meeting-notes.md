# 2024 February 1 - Meeting notes

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**
  - New repository for meeting notes: https://github.com/salt-extensions/community
- **Feedback to the core Salt team about the modules**
  - Let's review the list of modules that will be core, core extended, and community supported. See [this pull request](https://github.com/saltstack/salt/pull/65971) and [the great module migration repo](https://github.com/saltstack/great-module-migration).
  - Any concerns about this list that we need to raise with the core Salt team? (Be aware that the core team is willing to listen to feedback, especially from trusted community members who make a good argument and are willing to help pull their weight in the community.)
  - We maybe need a clearer explanation of the general principles behind how the core team decides why certain extensions are put into each category. From what we can tell, it seems that:
    - **Core** is deliberately very small and includes only what is necessary for the general functioning of Salt.
    - **Core extensions** are pieces of code that are business critical from a Broadcom perspective and the core team will continue to maintain these extensions from a code quality and security perspective.
    - **Community extensions** are everything else and they will fall to the community to maintain.
- **Concerns about extensions**
  - The group identified a few main concerns:
    - **Installation** - How does an extension get into the user's system so that the can use it?
      - They're currently not available on pip, which is needed for a bootstrap installation.
      - This is currently a blocker because you can't install more than one extension at a time with salt pip. Bootstrap would be the most effective installation method, but it could cause a race condition when you run minions on a highstate.
      - Has anyone installed extensions at scale?
      - It might be nice if there was a switch for salt pip to make it not install in the extras directory.
      - It might be possible to fix it with relenv.
      - David Murphy is currently rewriting the bootstrap script to allow it to pass a list of Salt extensions. Windows will need a modification in order to accept a list of extensions.
      - Could there be a pip installable wheel?
      - It would be great if you could install just one extensions thing and get all your extensions back.
    - **Inter-dependencies between extensions** - Fragmenting the codebase means that everything has to be changed and refactored wholesale.
      - Max (from Slack): An observation: refactoring like [this one](https://github.com/saltstack/salt/pull/64351/files) (replace deprecated `ifconfig` with ip in four different modules `lxc`, `network`, `nspawn`, `vagrant`) are much less likely to be made synchronously in the new fragmented codebase. We'll need some new tools (mass-grep across all extensions, or maybe some integration tests, or something like `salt-rewrite`) to achieve the same efficiency (and responsive maintainers of these modules). Or maybe more DRY code consolidated in the utils namespace (but the function extraction process will be complicated, with long deprecation cycle and multiple releases in multiple projects).
      - It will be very difficult to upgrade Salt. There could be conflicting requirements. Salt requires may require one version of a dependency while an extension requires another. When Salt bumps a version of its dependency, we'll need integration testing to see if the extension still works with Salt. Possibly we'd need a huge integration test in the community repo that tries to see if there's conflicts.
      - We might need different combinations of different extensions and pin them to certain versions based on Salt. We might need to indicate things like "this extension works with this supported version of Salt."
      - We might need something like the `__virtual` function with the module that returns something to self to determine capability. Do we mandate that? Is that the way forward?
      - One example to look for might be the Azure SDK. Slackstorm bundles every one so that it contains its own virtual environment for plugins.
      - We might need to indicate things like "this extension works with this supported version of Salt."
    - **Standardization** - We need to create standard and frameworks for all extensions.
      - We also need to find efficiencies in the system where very similar modules should be bundled together or consolidated.
    - **Documentation** - There's currently a documentation gap. In the new user guides and the installation guide, there's no mention of how to use extensions or install them.
      - We need to spend some time thinking about this transition. Is there a way to still have centralized documentation for modules? And make sure that everyone has a header or metadata that links to the source files. It would be nice to also have GitHub badges that state which version of Salt the module is compatible with.
      - A centralized repository would also help with discovery and communication about security issues. We need something for automation or review processes.
      - Alyssa will take an action item to ensure Derek is at the next working group meeting to join us for this discussion.
- **Next steps**
  - The biggest thing is ensuring the final list is correct and firmed up, especially while the core Salt team is running on full speed with these extensions. Let's try to justify why something is a high priority or a must-have.



## Notable links

- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/