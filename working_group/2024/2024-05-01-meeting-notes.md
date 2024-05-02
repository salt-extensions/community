# 2024 April 18 - Meeting notes

## Attendees

- Nick
- Alyssa
- Melissa
- David
- Justin
- Meghann
- Keisha
- Max
- Dafydd
- Derek

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist:
https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- **AMA about unit testing with Pedro**
  - It turns out that Pedro wasn't able to make it today, so we'll reschedule this session, most likely for next time.
- **Recap from last week**
  - In our last meeting, we talked about Max Arnold's proposal for adding metadata structure files to the extensions. See https://github.com/max-arnold/salt-extensions-metadata/
  - The main debate was over whether to keep centralized metadata or distributed metadata (or a combo of both). Did that resolve? Any additional thoughts?
  - Nick and Max were not able to follow up on their action items because they were busy. But Max did discover that PyPi data is very messy and difficult to work with.
- **Module documentation quality project**
  - Alyssa worked for awhile on a module documentation quality project. This initiative originally came out of the [Salt docs roadmap](https://saltdocs.prodcamp.com/). She often polls people for docs initiatives she should work on and notes when people vote on key initiatives. She consults with stakeholders to choose what the next project should be.
  - The first initiative she was originally tasked with from the roadmap was the module documentation quality project: https://saltdocs.prodcamp.com/2
  - In terms of the progress she made on this project, she met with stakeholders and developed a template for what should be part of all module documentation. See https://saltstack.gitlab.io/open/docs/docs-hub/topics/module-doc-standards/index.html
  - She got pre-empted away from this project, but briefly gave it to a Salt docs working group member to work on. He was going to create a "golden module" that followed the template (the `file` execution module), but that project also stalled.
  - In the meeting, she talked through the template and then got feedback about whether it would have any relevance to the Salt extensions working group.
  - Nick: After creating one golden example, is there going to be any initiative to go back and clean up and change the existing documentation en masse or will it only apply to new modules/functions going forward?
    - Alyssa: Originally my plan was:
      1. Create the standards.
      2. Get one module into a state where it was compliant with the standards.
      3. Require it for net new modules.
      4. Organize a Salt docs community event where we divide the documentation improvement work into batches and improve the module documentation like that.
  - Max: I recommend adding these fields to the module template:
    1. Salt version compatibility
    2. Version added/changed tag for new module functions
  - Nick: The main thing my head goes to is how do we enforce these things? It would be really difficult to enforce a programmatic or technical check. Because there isn't an easy technical check, the onus will be on the maintainers to enforce it. We'll need to socialize it.
  - Alyssa: What about adding metadata that shows that something is validated? Nick felt this wasn't sustainable.
  - Max: To clarify, in my metadata proposal, it wasn't about a human validation method, but instead it assigns trust based on the source of the extension (such as whether it's from the core team or not). The closest we could get to what you're talking about is perhaps some sort of badging system that verifies it is using the template or not.
  - Alyssa: What about including the guidelines in the copier template to nudge them or guide them to include this template? Nick felt that this could work, but the problem is that most of the extensions aren't net new. It's old code being moved out into extensions. The copier template won't apply to those extensions.
  - Nick: How do we attack this going forward? There is no standard currently, not even as far as the rST indents and whether they use params or not. It's all over the place. So, when I make a contribution, I tend to follow the standard that is closest to wherever I am at the time.
  - FYI, the copier template includes a broken link checker.
- **Feedback on having a forum channel on Discord**
  - Derek was wondering if it would be helpful to add a forums channel on Discord for answering support questions?
  - Nick was against this idea because it duplicates what we're trying to do with GitHub discussions, which is a better place to have those discussions.
  - Max: Can we get an RSS feed for pull requests and issues? Derek will explore adding that.


## Next steps

- Next meeting is May 16. Pedro confirmed he will attend next time!

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
