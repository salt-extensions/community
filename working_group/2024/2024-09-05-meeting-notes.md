# 2024 September 05 - Meeting notes

## Attendees
    - Dafydd
    - Melissa Strong
    - Max Arnold
    - Derek Ardoff
    - David Murphy

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**

- **salt-extension-copier improvements**
    - Writeup of Saltext work GIST
    - https://gist.github.com/lkubb/b29760f2b954faddf78e6e7d1da197a7
        - Presented GIST page and showed examples of links to for Documentation, Repo request template etc.



- **Dicussion of Community PRs?**
    - ***Add repo request issue template*** https://github.com/salt-extensions/community/pull/15
    - ***Templates*** https://github.com/salt-extensions/community/pull/6
    - ***MVP of Central Docs*** https://github.com/salt-extensions/community/pull/5
        - Presented the links above and recommended reviewing the changes

- **Discussion of tools**
    - ruff
    - uv
        - Discussion of using ruff/uv for a single extension to prove the concept and allow other extensions to utilise that work as a template. Issues of platform agnostism with uv won't be fully known until implementation phase, but given Salt is typically platform agnostic, it may not be too large an issue.
        - Request for any other tools that could be utilized.
        - It was noted that, could use tools not regularily used by Salt to develop extensions, since once published to PyPI, the pip installation from PyPI should be straightforward, so long as those tools publish compatibly with pip etc.

- **Discussion of next steps with this working group.**
    - **Issue Tracking**
        - Max raised the issue of fixes being pushed to salt-extensions rather than Salt core code. Currently some issues are being fixed in Salt branches (3006, 3007, master) and whether these fixes should be pushed to the various salt extensions that are available, and those not, to recommend extension extraction.  David pointed out that this is being done already, but in an inconsistant manner, which shows room for improvement. For example: fixes for Vault or Azure, recommendation is to have the fixes made to their salt extensions, but this needs to be done for all existing extensions, and a suggestion to the person to create the extension for their appropriate fix. Current problem is resources and need to start 3008 development (and salt-extensions) in earnst, once 3007.2 is released.
    - **Security**
        - Max raised issue in need to have security scanning, vuln testing, etc. consistent across community and core extensions. David plans on salt core extensions to be in the same extensions repository and subject to same workflows, scanning, etc. as the community extensions, to ensure consistancy for all extensions.
    - **Trusted Publishing**
        - Need to allow for Trusted Publishing on a per extension basis
        - Need to review granting Maintainer ownership for a specific extension to their maintainer before Trusted Publishing is implmented
        - David to ping Nichcolas, as to Trusted Publishing and when he might return to the working group.


## Next steps

- Next meeting is September 19th.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
