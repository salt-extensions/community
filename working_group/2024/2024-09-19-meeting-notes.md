# 2024 September 19 - Meeting notes

## Attendees

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl
Video from Sept. 5th meeting still to be uploaded to youtube.

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**

- **Discussion of testing with this working group.**
    - Ensure use Pytest for testing (unless exception due to circumstance)
    - Ensure move all test files for extension from Salt, and adjust for extension
    - Testing files should use Python tests where possible, for example: Python mock instead of Salt's tests/support/mock.py
    - Any other testing ideas ?

- **Discussion of GitHub Actions with this working group.**
    - Central Artifacts - use these workflows to perform all actions ?

- **Answers for items raised in last meeting with this working group.**
    - **Issue Tracking**
        - Q. Max raised the issue of fixes being pushed to salt-extensions rather than Salt core code. Currently some issues are being fixed in Salt branches (3006, 3007, master) and whether these fixes should be pushed to the various salt extensions that are available, and those not, to recommend extension extraction.  David pointed out that this is being done already, but in an inconsistant manner, which shows room for improvement. For example: fixes for Vault or Azure, recommendation is to have the fixes made to their salt extensions, but this needs to be done for all existing extensions, and a suggestion to the person to create the extension for their appropriate fix. Current problem is resources and need to start 3008 development (and salt-extensions) in earnst, once 3007.2 is released.
        - A. Started pushing to salt-extensions for fixes, see Issue # https://github.com/saltstack/salt/issues/66847#issuecomment-2338481989
    - **Security**
        - Q. Max raised issue in need to have security scanning, vuln testing, etc. consistent across community and core extensions. David plans on salt core extensions to be in the same extensions repository and subject to same workflows, scanning, etc. as the community extensions, to ensure consistancy for all extensions.
        - A. Got confirmation from Salt management, that the core extensions can be in the extensions repository, making sure all the extensions go throught the same processes, etc.

    - **Trusted Publishing**
        - Need to allow for Trusted Publishing on a per extension basis
        - Need to review granting Maintainer ownership for a specific extension to their maintainer before Trusted Publishing is implmented
        - David to ping Nichcolas, as to Trusted Publishing and when he might return to the working group.
            - Sent email but no reply to date.

- **Discussion of next steps with this working group.**


## Next steps

- Next meeting is October 3rd.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
