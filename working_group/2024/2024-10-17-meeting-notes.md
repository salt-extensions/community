# 2024 October 17 - Meeting notes

## Attendees

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl
Video from Sept. 5th and 19th, and Oct 3rd meetings still to be uploaded to youtube

## Agenda and notes

- **Welcome any newcomers**
    - Melissa Strong
    - Max Arnold
    - David Murphy

- **Announcements**


- **Updates to copier.**
    - Copier has been updated, see **salt-extensions** on **Discord** for details


- **Meeting items for  discussion.**
    - Still no contact with Nick, unresponsive to emails, discussion stated that only access to PyPI is
      needed. Will check to see if some other access to PyPI is available.
    - Given the extension code has been working in Salt code base, starting extensions with 1.0.0 is fine.
    - Need to post and push Salt Extension work by the end of October once some core Salt work is completed and the Salt Core team will be focusing on the Core Extensions and increaed their experience on creating Salt
Extensions.
    - pip install of Salt 3006 is not installing dependency cryptography, being worked on
      https://github.com/saltstack/salt/pull/66977. Work-around is to include cryptography in pyproject.toml
      as a dependency. The fix should be in the next release of Salt 3006 (3006.10), Salt 3007 is unaffected.
    - master branch PR's are currently on hold until the master branch nightly builds are green (successful).


- **Discussion of next steps with this working group.**


## Next steps

- Next meeting is November 07th.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
