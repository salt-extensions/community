# 2024 March 21 - Meeting notes

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist: https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **Announcements**
  - Reminder that our new meeting cadence is the 1st and 3rd Thursday. See the [Salt Project community calendar](https://saltproject.io/calendar/) for specific dates and the Zoom link.
  - Alyssa will be on vacation and will miss our next meeting on April 4.
- **Discussion about Max's proposal for centralized documentation**
  - See Max's proposal: [Keep the centralized module documentation at docs.saltproject.io](https://github.com/saltstack/salt/discussions/66144) on GitHub discussions. To summarize: it would be nice to keep the familiar user experience where everything is in one place and the documentation can serve as a discovery mechanism. It could have a common module namespace to avoid module namespace collisions. This can also help with issue tracking and extension statuses linked to the repository.
  - Derek: The problems with this proposal are that it's challenging to bring it into the current docs and just plug them in because you run into things like what happens if the docs are broken on that particular repo, what happens when an extension wants to list multiple versions of its documentation, what happens when you want to integrate it with a larger search mechanism? Sphinx struggles with this.
  - Derek: We had a similar problem for Idem Project since it is also plugin-based and used a lot of decentralized repositories with isolated documentation. We'd like to improve on what was done at Idem because they were all maintained by the core team. It was easier to make decisions about a shared CI/CD for docs.
- **Alternative solutions**
  - Some possible solutions from Derek:
    - We could consider using innersphinx, which might give us the ability to link out and list docs in other projects. At a minimum, we could at least have a list or jumping off point for the extensions.
    - Read the Docs has some built-in automation that tries to help with this using submodules. For example, we could create a single repo that pulls in community extensions and wants to build a single site that has them all there. Read the Docs might also support integrated search across that. The community might also be eligible for Algolia search integration for decentralized docs in one search pool.
  - Nick: Maybe we could have a tiered wishlist of things that we want to work toward. That's the core of what Max's proposal is going for. What would be other options if we can't do that?
    - Maybe a centralized documentation site for community maintained extensions as a single point of truth. If that's not possible, maybe a community only centralized documentation site.
    - If not that, then fulfilling the need of creating module documentation somewhere, such as a Read the Docs template that gets copied out or has a CI/CD process that helps people onboard their docs somewhere.
    - Bare minimum: We use a common naming structure in PyPi that makes it so that you can recognize it as a Salt extension.
  - How is it done in other Linux distros?
    - Some of them have an app, but it doesn't seem like there are enough resources to create a platform like that. Who would own it? Who would maintain it? Where would it be hosted?
- **Minimum viable solution**
  - What's the minimum workable solution we could implement just to have something working and then from there iterate on it and make it better over time as resources allow?
  - Pedro: A minimum viable product could be an "awesome list," a static site listing known extensions with links out with a description of what it is and what it does. It could have a link out to the documentation wherever the user has it hosted. We should do as much as possible to keep things on the free tier as much as possible.
  - **Decision:** At a minimum, we should at least have a stub linking out from the core Salt docs to where you can find the new code and documentation for the module.
  - **Action:** Pedro will work with the core team and ensure that these stubs are added either at the same time or shortly after dwoz's PR removing the modules is merged.
  - Meghann: I've got a working proof of concept for a possible minimum viable solution. I have been playing around with a GitHub static page and has built a template that all future extensions could also use. We could create a template repo for any future repos. I've also been playing around with a GitHub Action that installs all the dependencies and then uses Sphinx to build the documentation, then push it to a static repo. Then, using toctree you can have a link to all the other docs on that page.
  - **Action:** Meghann will clean it up and share it when the group when it's stabilized. We could also consider demoing it in this group or possibly at the community Open Hour.
  - GitHub Pages could be a solution for the awesome list. There could also be used in combination with Read the Docs. We should also consider looking into Algolia.
- **Tools for spinning up docs for new modules and documentation standards**
  - Derek: How does the community maintained copier template work in terms of documentation?
  - Nick: It creates a tree for you based on what types of modules you're using. Additionally, it manages the conf.py so that the copier template could be used to set themes or include anything else we want to standardize on. It also does a nice job of updating versions. But we'll need to put a process in place to see where some extensions are for the copier lifecycle.
  - **Decision:** The core team will be happy to deprecate the core extensions tool and defer to the community maintained copier template.
  - Derek: We might be able to use this tool to make updates to standardized GitHub workflows.
  - **Action:** Nick will take an action item to talk to lkubb (Jean-Luc) to see if he's okay with moving it to the community org.
  - Tyler has been working on an idea that may make it easier to create new modules in the future that he can share as a proof of concept. It allows you to indicate which modules you want to pull out into your new repository; it bootstraps a repo while also maintaining the Git history. He'll share it more in a future meeting.
  - Max is looking into creating an offline tool that can collectively pull in docsets.
  - Innersphinx might again be a good way to cross-link between disparate documentation sets. Pedro explained some of what he learned about working with it. It is complex, but possible.
- **Module namespace or dependency clashes**
  - A centralized poetry repo might solve this problem.
  - It's a good idea to have one big integration test, at least for the installation step.
  - You could have a cron job that could check that, but we'd need some way to expose which modules are causing the conflicts.


## Notable links

- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/