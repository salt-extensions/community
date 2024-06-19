# 2024 February 1 - Meeting notes

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Introductions** - Tell us about yourself, where you're at in the world, how you use Salt and your experience level, why you are interested in this group, and what you hope to get out of it.
- **How we work**
  - Decision: We will record the meeting and let it be posted on YouTube.
  - Decision: We will keep meeting notes in markdown in a community repository.
  - Action: Nick will create the community repository and Alyssa will post the meeting notes.
- **Publishing packages to PyPi**
  - We had a discussion about publishing packages to PyPi. Jaimie wanted to ensure there is redundancy among the PyPi maintainers to ensure consistent access is maintained.
  - Everything is published by [saltext-community](https://pypi.org/user/saltext-community/) in PyPi. Nick has the credentials in his company account and can add others if needed.
- **Companies that host their own extensions**
  - We discussed how to handle extensions that are hosted and maintained by a third party. How do we ensure that we don't have inaccessible packages or repositories?
  - Decision: If you are a company, that's different than just being an individual because it's more likely to be maintained. We can create a placeholder or a clone in the `salt-extensions` repository.
  - Who can access and publish to enable extensions discovery?
  - Let's start with a minimum viable product such as an awesome list or README list to start. Then we can iterate or build more sophisticated discovery mechanisms from there. If working group members feel motivated to come up with a better solution, we can let them work on it as part of a larger initiative in this working group.
  - Action: Nick will create an awesome repository.
  - Open questions we still need to resolve:
    - For community maintained extensions, how will people be able to see the status of an extensions, such as when it breaks?
- **Redirecting from previous extensions**
  - How will we redirect people from the old module to the new one?
  - We should replace the code with some placeholder text or docs that explain where the extension is now.
  - Maybe we could load redirect paths into a bot and set up a bot to do that?
- **Licensing**
  - Decision: For extensions that were taken from the existing Salt codebase, we will use Apache 2.0. We will encourage any new extensions to use the Apache 2.0 license.
  - Action: We'll add the Apache 2.0 license to the repository and see if the Salt Extensions builder can default to Apache 2.0.


## Notable links

- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/