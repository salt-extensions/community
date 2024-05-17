# 2024 April 16 - Meeting notes

## Attendees

- Alyssa
- Pedro
- Melissa
- Dafydd
- Shane
- David

## Meeting recording

Watch the YouTube recording of the meeting on the Salt Extensions playlist:
https://www.youtube.com/playlist?list=PL9svBjLDUl_-gyXj2lDYomI8keXtbMqUl

## Agenda and notes

- **Welcome any newcomers**
- Today's agenda is: Questions and answers about unit testing with Pedro. Come prepared to ask Pedro questions about unit testing. Pedro does not intend for this to be a training session or a general run-down, but is happy to answer any specific questions you might have.
- **Q: Any examples of how an orchestration (sls file) can be tested?**
  - A: Maybe. I haven't touched orchestration tests for a long time, but we should be testing them in Salt. I'm sure there's some test coverage in Salt itself, but I'm afraid I don't have any guides to offer. I recommend looking at the orchestration tests in Salt to start. They're probably not as comprehensive as they could be. So after looking at those, try to pinpoint some more direct questions from there that you can ask the core Salt team.
  - Q: Would they be similar to cloud tests?
  - A: No, they'd be more like state tests. They would likely be integration tests (and not something similar like functional tests or unit tests) because those might be easier to test. For example, functional testing came out of a need for faster and more lightweight tests with less moving parts. We started using functional tests because they were more direct testing against the module.
- **Q: Bonus question: how to test an orchestration that runs something on a Windows minion?**
  - A: I would run the orchestration on Windows. The follow up question is more likely that there is no official support for a Salt master on Windows, so I get where that question is coming from. I recommend running it how we run it in our testing suite: it gets triggered on the master which is run on Windows and then we run the orchestration on Windows. Even though there is no official support, we do run the master on Windows. So, set up a Windows VM and then follow the integration tests by calling the orchestration functions and then asserting against the output. You would need to use the full setup with a master, a minion, and going through the CLI.
  - Q: Would this be more like testing in general with Test Kitchen?
  - A: It could depend on what you're trying to orchestrate. We've been moving away from things like Test Kitchen, mainly because we don't have enough maintainers to support or maintain that. And after awhile, there wasn't really a need. So what we usually do is set up a VM like we used to do with the golden images. If I were you, I would follow that same procedure. That being said, if it is a more complex orchestration, then you should probably add something else to the equation. But just testing the orchestration functionality probably doesn't require much.
- **Q: Same question for reactors.**
  - A: Same approach. I do get why these questions come up because there's not enough examples in the test suite. It's the same approach: look at what we are doing because we should be testing something. So, you would want to use an integration test. There is no simpler way to test that unless you obviously go through a unit test and patch it a lot. Sometimes that approach is good and sometimes it is not. You patch a lot and then basically you're testing your patches instead of the actual approach. So, for the safest route, go with an integration test. And I'm sure we have them for reactors, probably at least one or two.
  - So basically, use a Salt master and minion. The reactors are usually are an SLS file that you have to tag. So lay those down in the file system and then call them through the CLI. Then provoke the reactions.
- **General guidelines (scenarios) on when it is best to use each kind of test (unit, functional, integration) in regards to Salt Extension development and different kinds of modules (and also to test state files)?**
  - A: Sometimes it's a matter of preference, other times it's a matter of resources (time or money), depending on how you test Salt itself. I've always tried to do functional testing because that's how you run against the functions and test the code that was written without patching too much. You still have patching available, but you usually don't need to. Obviously, this kind of functional testing means you're actually interacting with a system or a service, which might not always be possible.
  - Therefore, to drill down on the choices, for speed the best choice is unit tests. However, there are times where we have to patch too much and we might have to fall into the problem of testing our patches instead of the code. When you are testing your patches, that means you're not testing anything because the code changes, but the patch didn't change and so the tests don't fail. So you don't see the actual failure in the code. But if you keep your patches minimal purely to get the infrastructure to work, then unit testing is the fastest one. Then to be on the safe side, I'd actually run functional tests against the actual code.
  - Then, if you really have to, run an integration test. An integration test is almost like an end-to-end test, which tests all of the things including the CLI, the salt minion, the salt master, the protocol. But in most cases, I don't think you'd need integration tests. It might not hurt to have a few of them, but I would focus on unit tests first and then some functional tests.
- **Q: How to test a custom module function that calls `state.show_lowstate` without mocking it (so I can make asserts against it being run with an actual state tree)? It seems to require a lot of mocks/opts to be run successfully?**
  - A: For that one, I would go the functional route because you have to lay down the custom module and that runs almost separately from the test suite. But you could build a queue system and then add data to the queue. Then the test could add data to the queue and test against that.
  - For example, the way we pass logs to the daemons is using ZeroMQ and then add data to the queue that can be pulled from the test. So if I needed to go that deep to test the custom modules, I would do something like that. That would reduce the amount of patching you'd need to do.
- **Q: Can I confirm that the testing portion of the [Contributing Guide](https://docs.saltproject.io/en/master/topics/contributing-guide.html#test-first-test-last-test-meaningfully) is accurate and applicable to the extensions? Is this doc up to date? For example, I think you're using pytest now and I'm not sure it's up to date in the guide.**
  - A: So, we've been using pytest for awhile now and whenever we do see something that is using the old test suite, we try to update that. I can't say that it's fully migrated to the new approach. We should check and make sure that's the way we're still testing because that has evolved over time and it's likely the docs haven't kept up. There's always a place for more documentation, especially around contributing. I'm fairly confident it's out of date for extensions.
  - Shane: This also looks outdated: <https://docs.saltproject.io/en/master/topics/tutorials/writing_tests.html>
- **Q: It's been awhile since I contributed anything. I think it was pre-pytests. Would you recommend using the existing tests and use those as examples to walk myself through setting one up?**
  - A: Yes, and if you go through the trouble of doing that, you'd be helping us because you'd be able to find the parts where we're lacking or where we're wrong. So, if you have the chance to do something like that, it would be most welcome.
  - Consider keeping a friction log where you capture your goal, what you tried, where you failed, and how you succeeded (or not).
- **Q: I've heard the team is moving away from test kitchen and the plugin kitchen Salt toward pytest. Is pytest appropriate for testing formulas. So, for applying the test to the minions and then test the result that the minion applied the right change?**
  - A: To answer your question, the team has definitely moved away. We are not using test kitchen at all and David is currently pulling it out of the bootstrap script. Any mention of that should be removed. Over time, it stopped making sense. So, we didn't want to maintain that project any more. Yes, pytest is perfectly fine for testing formulas. Either on the 3007.x branch or the master branch, there are examples for testing formulas. Just this week I removed some tests and fixed some other tests that were broken. You can also use salt factories. If it were me, I would do something like that.
  - Formulas haven't really been tested until recently, so I'm sure there are a lot of improvements that could be made, even to the way things got tested. Your experience here would be beneficial, either in terms of giving advice about the tooling required or even if you find a better approach, suggest that. The Salt test suite should also be testing formulas so that we don't break support for them.
- **Q: So, the whole point of test kitchen is that you create a temporary machine with a minion that you apply things to and then test. So, instead you're moving towards test runners and GitHub actions?**
  - A: It made sense prior to GitHub actions, but now it makes more sense to use GitHub actions instead.
  - With kitchen, you could spin up the container and be done with it, but what we are suggesting now is to use pytest to do something like that. And we can bring containers into pytest. With a container set up, there are some commands you can run to set it up, which is exactly what kitchen salt would do. Then, you can test against that. So that's why we stopped using test kitchen: so that we no longer have to prepare the system up front by using some big binaries. If we need to do something else during run time while the test suite is running, we either use containers or run against the operating system itself. Use the pytest fixtures, which is how you can set up the environment to test your OS.
  - If you look at the Salt test suite, I believe the method is called start_container or get_container. If you grep through that, you'll see a lot of examples. What we did to save time in our test suite was to actually have pre-baked containers. For example, if we need to test against Postgres, MongoDB, or another service like that, we prepared those images to save time. If what you're testing is a formula that sets all of that up, then there's no point in preparing an image beforehand.


## Next steps

- Next meeting is June 6.

## Notable links

- https://github.com/orgs/salt-extensions/projects/5
- https://github.com/saltstack/community
- https://extensions.saltproject.io/
- https://github.com/saltstack/salt/pull/65971
- https://github.com/saltstack/great-module-migration
- https://github.com/orgs/salt-extensions/repositories
- https://github.com/saltstack/community/tree/master/working_groups
- https://salt.tips/whats-new-in-salt-chlorine/
