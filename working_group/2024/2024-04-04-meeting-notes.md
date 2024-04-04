# 2024 April 4 - Meeting notes

## Attendees

- Nicholas Hughes (leading)
- Meghann Cunningham
- Melissa Strong
- Gary Giesen
- Max Arnold
- Keisha Gamble
- Shane Lee (notes)

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist:
https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**
- **Discussion about Meghanns demo**
  Last time we talked about consolidated documentation. Meghann was going to
  research that. We followed up with Meghann to see where she got with it.
  - Did some work with github workflows to scan each repo in the salt
    extensions org and add it to the docs if it is missing. It auto generates
    a PR to add it to the mapping.
  - Needs to add a step to automate adding it to the RST which is kind of a
    central list of extensions.
  - Max Arnold suggested using a JSON or YAML file in extension repos to hold
    metadata about the extension which the centralized docs can use for building
    the RST. A user who wants their extension with associated docs to be listed
    in the main repository, they will add the JSON/YAML file to their extension
    repo. Max will work on a schema.
  - Discussed how the docs get built... on Merge? Probably Nightly to start.
  - This is currently in Meghann's repo. If we like this approach, then we
    would move it to a repo in the salt-extensions org. We need to create some
    boilerplate to get people started.
  - Max asked about steps forward. What are the next steps? Is it possible to
    have search, for example. We talked about Sphinx having some native search.
  - Max asked how we would include other stuff, core extensions for example, to
    the rollup page. Group community extensions together in their own group,
    core extensions in their own.
  - Max said we could maybe use extension.saltproject.io to host the github
    pages, or at least, redirect to the extension docs
  - Shane doesn't like the name "rollup", except for fruit snacks.

## Next Steps

- Meghann is going to get her work into the salt extensions org
- Max is going to look at the metadata schema that would go into each repo
- Nick is going to talk to Jean Luc about updating the copier template to
  include docs stuff, should also include the metadata schema Max is working on
- Nick is going to check with Derek about the old extensions page.
- Shane will put these notes here: https://github.com/salt-extensions/community

## Notable links

- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
