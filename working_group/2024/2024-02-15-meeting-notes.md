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
- **Concerns about extensions brought up in Slack**
  - Max: An observation: refactorings like [this one](https://github.com/saltstack/salt/pull/64351/files) (replace deprecated `ifconfig` with ip in four different modules `lxc`, `network`, `nspawn`, `vagrant`) are much less likely to be made synchronously in the new fragmented codebase. We'll need some new tools (mass-grep across all extensions, or maybe some integration tests, or something like `salt-rewrite`) to achieve the same efficiency (and responsive maintainers of these modules). Or maybe more DRY code consolidated in the utils namespace (but the function extraction process will be complicated, with long deprecation cycle and multiple releases in multiple projects).
- **Next steps**
  - What do we want to work on together as a group? Are there any tasks related to the general process of building and maintaining a Salt extension that we need to address or make better?
  - Which extensions would you like to become a maintainer of?



## Notable links

- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/