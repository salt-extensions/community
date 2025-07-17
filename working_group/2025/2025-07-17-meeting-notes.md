# 2025 July 17 - Meeting notes

## Attendees
  - Shane Lee (@twangboy)
  - Dafydd (@dafyddj)
  - Peter Upton

## Agenda and notes

- **Welcome any newcomers**

- **Announcements**
  - 3006.13 & 3007.5 released
    https://saltproject.io/blog/2025-06-26-new-releases-salt-3006-13-3007-5/
  - 3006.14 & 3007.6 released
    https://saltproject.io/blog/2025-07-10-new-releases-salt-3006-14-3007-6/
  - 3008 - Fall 2025

## Projects and Status
- Installation: Seems to be working
- Copier template: Major work is done
- Testing Infra: Major work is done

## Meeting items for discussion
- Modules being brought back to Core. Create a PR and we'll discuss it there
- Should this be a Salt Extension or a Core Extension:
  https://github.com/saltstack/salt/issues/54791
  Peter Upton has written his own Salt Extension to do some basic stuff with
  network manager, but he doesn't feel that it's sufficient. His code is here:
  https://github.com/peterupton/saltext-nmcli/blob/main/src/saltext/nmcli/modules/nmcli_mod.py
  We will bring it up during the Salt Open Hour with dwoz to get his opinion

## Action Items
- Shane: Creating Stubs in Salt Docs for removed code

- Next meeting is Aug 7, 2025.

## Notable links

- [Extension Migration](https://github.com/orgs/salt-extensions/projects/5)
- [Working Group Tasks](https://github.com/orgs/salt-extensions/projects/6)
- [Salt Community Repo](https://github.com/saltstack/community)
- [Salt Extensions Index](https://extensions.saltproject.io/)
- [Module Migration PR](https://github.com/saltstack/salt/pull/65971)
- [Great Module Migration](https://github.com/saltstack/great-module-migration)
- [Salt Extensions Repos](https://github.com/orgs/salt-extensions/repositories)
- [Salt Working Groups](https://github.com/saltstack/community/tree/master/working_groups)
- [Salt Tips Website](https://salt.tips/whats-new-in-salt-chlorine/)
