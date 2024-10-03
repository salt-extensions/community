# 2024 October 03 - Meeting notes

## Attendees

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl
Video from Sept. 5th and 19th, and today's Oct 3rd meetings still to be uploaded to youtube

## Agenda and notes

- **Welcome any newcomers**
    - Shane Less
    - Melissa Strong
    - David Murphy
    - Max Arnold
    - Dafydd

- **Announcements**

- **New extensions.**
    - saltext-apcups
    - saltext-nix
    - saltext-zfs
    - saltext-snap
    - saltext-influxdb
    - saltext-acme

- **Updates to copier.**
    - Copier has been updated, see **salt-extensions** on **Discord** for details


- **Meeting items discussed.**
    - Central Artifacts clarification, definitely use Copier artifacts with the enhanced workflow, however Copier is making use of Central Artifacts, see [https://github.com/salt-extensions/saltext-zfs/blob/main/.github/workflows/pr.yml](URL), where it referrences
        - uses: `salt-extensions/central-artifacts/.github/workflows/ci.yml@main`

    - Clean up  of files left over in master branch , and allocation to correct places that were missed in the
'Great Purge' as extensions are generated.
    - Still to contact Nick by other means, as unresponsive to emails.
    - Given the extension code has been working in Salt code base, starting extensions with 1.0.0 is fine.
    - Need to post and push Salt Extension work by the end of October once some core Salt work is completed and the Salt Core team will be focusing on the Core Extensions and increaed their experience on creating Salt
Extensions.


- **Discussion of next steps with this working group.**


## Next steps

- Next meeting is October 17th.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
