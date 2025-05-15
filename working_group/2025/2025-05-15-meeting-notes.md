# 2025 May 15 - Meeting notes

## Attendees
  - Shane Lee (@twangboy)
  - djivey
  - dafyddj
  - Max Arnold
  - Melissa Strong

## Agenda and notes

- **Welcome any newcomers**

- **Announcements**
  - 3007.2 released
    https://saltproject.io/blog/2025-05-14-new-release-salt-3007-2/

## Projects and Status
- Installation: Seems to be working
- Copier template: Major work is done
- Testing Infra: Major work is done

## Meeting items for discussion
- djivey is working on a Salt-Extension for the Boto Modules. Migrating to
  Boto3. Combining AWS and Boto3 salt utils so there is a single util for
  aws authentication. Also including the AWS cloud provider as part of the
  boto extension. Call the extension salt-aws or something instead of boto.
- Max Arnold asked about when 3008 would be released. We're looking at fall of
  2025 as of now. I'll follow Dwoz.
- salt extensions work on 3007 and seem to take priority over existing core
  modules. What is the difference in how things are imported with a salt
  extension?:
  core utils: import salt.utils.<module>
  ext utils:  import saltext.<extname>.utils.<module>
- daffydj - How will the move to 3008 effect regular users. May not be an
  immediate concern. We intend to extend 3006.x LTS support until 3008 is
  stable and all issues worked out.

## Action Items
- Shane: Follow up with Salt Core team about removing fragments, bring modules
  back in to Salt core
- Shane: Creating Stubs in Salt Docs for removed code
- Shane: Announce we're not going to remove salt supported extensions for now
         (See above)

- Next meeting is June 5, 2025.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://github.com/orgs/salt-extensions/projects/6
- https://salt.tips/whats-new-in-salt-chlorine/
