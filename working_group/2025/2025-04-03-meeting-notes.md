# 2025 April 03 - Meeting notes

## Attendees
  - Shane Lee (@twangboy)
  - Jim Anderson
  - Dafydd
  - Derek Ardolf

## Agenda and notes

- **Welcome any newcomers**

- **Announcements**
  - David Murphy has decided to retire
    https://saltproject.io/blog/2025-04-02-david-murphy-retires/
  - CI/CD Status in Salt

## Projects and Status
- **Copier**
  - Being developed by JeanLuc
  - Seems to be working, will need some minor tweaks as issues are discovered
  - Can update extension templates created with an older version of copier
  - Can be automated with Renovate to autoupdate your extensions
- **Installation**
  - Does this work?
  - Are the current salt-extensions being published to PyPi
  - It's currently a semi-manual process. We need a way to automate this, or
    pass a list of extensions that need to be installed as part of the bootstrap
    script or passed as a list to the installer itself
  - Or create a way for the state system to detect that an extension module is
    missing and install it before applying the state
  - Maybe use a requires state... basically we need a "Best Practice" in the
    docs.
- Publishing to PyPi
  - Trusted publisher workflow, requires a bot (saltext-community)
    https://pypi.org/user/saltext-community/
  - TODO: Create an Organization request with PyPi for the salt-extensions org
- **Dependencies**
  - Salt
  - Between extensions
  - Setuptools no longer uses setup.py, that breaks installing Salt via pip
  - Idem tried to resolve this issue as well, ask Tyler about this
  - I don't think this is resolved
- **Documentation**
  - Megan's work
    - Did that ever make it into the salt-extensions org
  - Salt core team needs discuss creating Stubs to migrated modules
    - A single url to the new salt extension or to the holding repo
- **Discovery**
  - Megan was working on a website, not sure where this is now
  - We wanted to have a search mechanism
  - There was some discussion about an awesome list
- **Metadata**
  - Max Arnold's work
  - Was going to be a reference for the website to use to gather information
- **Extension Template**
  - This may be done
  - Allow users to apply for a new repo in the salt-extensions org
- **Redirection for moved extensions**
  - Maybe we need to have an error message in Salt to look in salt-extensions
    for missing modules
- Testing infrastructure
  - Copier template sets this up
  - Uses salt-factories from Salt
  - https://github.com/salt-extensions/central-artifacts
    - Contains workflows to be used by salt-extensions in this org for testing
- Messaging
  - PRs to salt for **existing** modules that have been migrated:
    - This module and its associated states and tests have been transitioned to
      community support and are no longer maintained by the Salt Core team. The
      code has been removed from the Salt code-base and can be found in this
      repository: https://github.com/salt-extensions/community-extensions-holding/
    
      There is currently discussion and work being done on the salt-extensions
      Discord channel (https://discordapp.com/channels/1200072194781368340/1208165123240370197)
      to document and build the infrastructure for community-supported salt
      extensions. There is also a Salt-Extensions Working Group that takes place
      on the 1st and 3rd Thursday of every month to coordinate salt-extension
      efforts.

  - PRs for **new modules** in Salt that should be extension modules
    - Starting in Salt 3008 non-core Execution and State modules have been
      migrated to community support. There is a GitHub org set up for this
      purpose: https://github.com/salt-extensions. This code would be better
      served as a salt-extension.

      There is currently discussion and work being done on the salt-extensions
      Discord channel (https://discordapp.com/channels/1200072194781368340/1208165123240370197)
      to document and build the infrastructure for community-supported salt
      extensions. There is also a Salt-Extensions Working Group that takes place
      on the 1st and 3rd Thursday of every month to coordinate salt-extension
      efforts.

- Long RC and Nightlies
  - We do have nightlies now for all branches in Salt
  - Publish `art.py` to the user guide showing how to pull down the artifacts
  - They're hard to get to, maybe they need to be published
  - Perhaps use a pre-release label
  - In salt-formulas, they were run on a template formula that tested against
    master on every commit. Maybe set up a simple salt-extension just for this 
    purpose.
    https://github.com/saltstack-formulas/template-formula

- **Meeting items for discussion.**
  - Should we create some kind of board or project for tracking this stuff?
  - Discuss this with Max and JeanLuc

- **Discussion of next steps with this working group.**

## Action Items

- Next meeting is April 17, 2025.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
