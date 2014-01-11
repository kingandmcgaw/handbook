Easyart developer handbook/manifesto (draft)
===========

This is an outline of the London tech team's working methodologies, rather than a company-wide policy. It's intended to be a living document, so please make changes via pull request.

####General principles:
* __Clarity over cleverness__. Your code is only good if someone else undertands it.
* __Collaboration over unilateral decisions__. Prefer oversharing and overcommunication (at the expense of some chatter/noise) to implicit understanding and agreement. Goal is to [increase bus factor](http://en.wikipedia.org/wiki/Bus_factor). Pair program when appropriate.
* __Be asynchronous and location-agnostic__. With a workforce across multiple locations it's important that we behave as if we're _all_ remote. Always acknowledge communication. Also helps scale the workforce.
* __Clearly define success metrics__. Ideas and requests are just unproven hypotheses. Test early and often against success criteria. Your job is not programming, [it's delivering value using programming](http://blog.bahadir.io/posts/failed-entrepreneur.html), so always ensure you're delivering value.
* __Transparency by default__. All information should be as public as possible. Use blog posts, Twitter, Basecamp, meetings or whatever is most suitable to disseminate information.
* __With the exception of team standups, meetings are optional when possible__. But if you attend you must participate.
* Project naming conventions. Directors!
* __Agile methodologies, not tools__. Backlogs, standups, QA etc.
* __Continuous delivery backed up by tests__

###Language style guides
  
####Javascript
* [Airbnb's style guide](https://github.com/airbnb/javascript) as a starting point. Perhaps with some exceptions:
  * Prefer `function test () {` to `function test() {`. Because, Crockford.
  * Prefer double quotes for strings
  * Note: what documentation style?
  * Note: or is are we using [Google's styleguide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)?
  
####Ruby
* [Github's style guide](https://github.com/styleguide/ruby) as a starting point, with some exceptions:
  * Not strict on `Keep lines fewer than 80 characters`. Just use common sense.
  * Note: what documentation style?
  
####CSS
* Sass style guide
* [Craven gem](https://github.com/easyart/craven)

###Task workflow

####Basecamp
* __Your _me_ page is your list of _accepted_ tasks__ that can be achieved within a 30 day period. It is your responsibility to make sure these tasks are completed and should be checked daily.
* __Tasks must be clear and actionable__ if they are going to stand any chance of getting completed. If a task is assigned to you that is unclear, send it back to the assigner for clarification. If it's too big, request that it be split up. Don't be shy about challenging. Goals and tasks should not be mixed. Be ruthless about destroying confusion. Confusion is the enemy of productivity.
* __Each project should have a backog__. These are tasks that need doing, but are unlikely to get done in the next 30 days. By default, new ideas should go into the backlog for prioritisation by project owners.
* __Ruthlessly remove tasks__ that are unclear, or low priority. Care should be taken to inform everyone it's being removed and why. If they are important they will come back.
* __Indicate callbacks__. Tasks that are done but need to be reported back on (or need to be reverted in the case of a time-sensitive content change) should have a due date and `:watch:` appended. Example: _Lazy load related images :watch: (Jan 1)_ might indicate the success of the task will be reported back into the ticket on January 1st.
* __Indicate blockers with question mark icon__. If someone or something is blocking the task from being completed, indicate it with the `:question:` icon. Example: _Decide on lead image for categories page :question:_ might the assignee is waiting for a third party before the image can be chosen.
* __Tasks must be assigned__. Tasks that are not assigned are extremely unlikely to be actioned.
* __Always add notes to tasks when decisions are made verbally__. Use Basecamp for meeting notes and documenting agreed sub-actions, no matter how trivial. We will always have distractions, forget what we agreed etc, so these notes are invaluable. Also, some of us will be working remotely, and will need to be kept in the loop. Prefer Basecamp to verbal communication where appropriate. *When things are only said on the phone, in person, in emails that don't include the whole group, or in one-on-one chats, information gets lost, forgotten, or misinterpreted. The problems expand when someone joins or leaves the project.*
* __Always prefer pasted text to attached files__. Google Docs are also preferable to attachments. Opening files is annoying.
* __Name your tasks sensibly__. Ideally prepend the task with the site (if appropriate) and page. e.g. `WG: Product page: change lead time copy`

####Git
* __Simple git branching__. Master, and your feature branches. Master is always deployable. No exceptions.
* __Pull requests for QA__. This is for knowledge sharing and sanity checking rather than "approval". Do so as early as possible. For minor changes and FYIs, [add comments to the lines in Github](https://help.github.com/articles/adding-commit-comments). Comments in the pull request are preferable to Basecamp if the change is in code. Never merge your own pull request. This means you are in charge of chasing someone to give their stamp of approval with a :shipit: message. 
* __Reviewing your teammates' code needs to be an equal priotity to writing new code__. Momentum is lost when changes await review too long. Kick up a fuss if anyone is blocking the feature from being completed.
* __Deployment via CI rather than direct deployment__. CircleCI will always deploy `master -> master` and `staging -> staging` if the tests pass. 
* __Anything can go into staging__. Changes should be pushed one-way from your feature branch. e.g. `git push --force origin feature-branch:staging`. Never run a staging branch locally.

####Code reviews (borrowed from [Thoughtbot's guidelines](http://playbook.thoughtbot.com/#code-reviews))
0. Create a local feature branch based off master.
0. When feature is complete and tests pass, stage the changes.
0. When you've staged the changes, commit them.
0. Write a good commit message.
0. Share your branch.
0. Submit a GitHub pull request.
0. Ask for a code review on the request or in Flowdock.
0. A team member other than the author reviews the pull request. They follow Code Review guidelines to avoid miscommunication.
0. They make comments and ask questions directly on lines of code in GitHub.
0. When satisfied, they comment on the pull request with the `:shipit:` (:shipit:) emoji.
0. Rebase interactively. Squash commits like "Fix whitespace" into one or a small number of valuable commit(s). Edit commit messages to reveal intent.
0. View a list of new commits. View changed files. Merge branch into master.
0. Delete your remote feature branch.
0. Delete your local feature branch.

####Design and UX
* Sketching
* Split testing
* Optimizely

####Monitoring and alerting
* Pingdom
* New Relic
* Logentries
* Cloudflare (TBC)
* Airbrake

####Payment processing
* Datacash

####References
* [The Twelve-Factor app](http://12factor.net/)
* [Thoughtbot Playbook](http://playbook.thoughtbot.com/)
