# 2025 February 06 - Meeting notes

## Attendees
 - David Murphy
 - Dafydd
 - David (yevi.1)
 - Max Arnold
 - Melissa Strong

## Agenda and notes

- **Welcome any newcomers**

- **Announcements**

- **Meeting items for  discussion.**
    - Max asked 3 questions:
        - Trusted Publishing
            - Pointed out jeanluc's docs for publishing worked well just before Christmas when publishing
              saltext-cassandra, see https://github.com/salt-extensions/salt-extension-copier/blob/main/docs/topics/publishing.md
        - Migration of files
            - Noted that during development of saltext-cassandra, found mistakes in the 'Great Migration PR' of
              files, where files relevant to Cassandra where in core, core extensions and community extensions
              incorrectly. Hence expect to find the 'Great Migration PR' to have mistakes that need
              correction, but these will only really be found at the implementation stage.
            - Also expect extensions to move between core and community, back and forth, depending on usage
              etc. which will only be found over time and use.  That is, location of extensions are not fixed
              in stone, but things can be expected to move around over time based on how extensions are used,
              since initial assumptions are liable to change over time, or found to be incorrect over time. That is, some assumed to be core could end up being community, and vice versa.
        - Profiler Output - extensions for each or one large extension
            - Comments from those present were not really strong on the matter, and probably will be liable to
              change over time. Proposed, those small, simple profiler outputters could be grouped together,
              but those profiler outputters which are large and complicated should be their own extension.

- **Discussion of next steps with this working group.**

## Next steps

- Next meeting is February 20th 2025.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
