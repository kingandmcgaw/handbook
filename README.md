Easyart developer handbook
===========

This is a draft of Easyart's web team's working methodologies. It's a living document, so please make changes via pull request.

####General principles
* __Clarity over cleverness__. Your code is only good if someone else undertands it.
* __Collaboration over unilateral decisions__. Prefer oversharing and overcommunication (at the expense of some chatter/noise) to implicit understanding and agreement. Goal is to [increase bus factor](http://en.wikipedia.org/wiki/Bus_factor). Pair program when appropriate.
* __Be asynchronous and location-agnostic__. [Everyone works remotely, even from an office](http://blog.mongohq.com/making-remote-work-work-an-adventure-in-time-and-space/). With a workforce across multiple locations it's important that we behave as if we're _all_ remote. Always acknowledge communication. Also helps scale the workforce.
* __Focus on value over features__. Ideas and requests are just unproven hypotheses. Test early and often against success criteria. Our job is not programming, [it's delivering value using programming](http://blog.bahadir.io/posts/failed-entrepreneur.html), so we must always ensure we're delivering value.
* __Transparency by default__. All information should be as public as possible. Use blog posts, Twitter, Basecamp, meetings or whatever is most suitable to disseminate information.
* __With the exception of team standups, meetings are optional when possible__. But if you attend you must participate.
* __Agile methodologies, not tools__. Backlogs, standups, QA etc. Related: [Easyart-flavoured agile](http://easyart.github.io/2013/04/16/easyart-flavoured-agile/)
* __Continuous delivery over releases__. Backed up by tests, of course.

####Basecamp
* __Your _me_ page is your list of _accepted_ tasks__ that can be achieved within a 30 day period. It is your responsibility to make sure these tasks are completed and should be checked daily.
* __Tasks must be clear and actionable__ if they are going to stand any chance of getting completed. If a task is assigned to you that is unclear, send it back to the assigner for clarification. If it's too big, request that it be split up. Don't be shy about challenging. Goals and tasks should not be mixed. Be ruthless about destroying confusion. Confusion is the enemy of productivity.
* __Each project should have a backog__. These are tasks that need doing, but are unlikely to get done in the next 30 days. By default, new ideas should go into the backlog for prioritisation by project owners.
* __Ruthlessly remove tasks__ that are unclear, or low priority. Care should be taken to inform everyone it's being removed and why. If they are important they will come back.
* __Indicate callbacks__. Tasks that are done but need to be reported back on (or need to be reverted in the case of a time-sensitive content change) should have a due date and `:watch:` appended. Example: _Lazy load related images :watch: (Jan 1)_ might indicate the success of the task will be reported back into the ticket on January 1st.
* __Tasks must be assigned__. Tasks that are not assigned are extremely unlikely to be actioned.
* __Always add notes to tasks when decisions are made verbally__. Use Basecamp for meeting notes and documenting agreed sub-actions, no matter how trivial. We will always have distractions, forget what we agreed etc, so these notes are invaluable. Also, some of us will be working remotely, and will need to be kept in the loop. Prefer Basecamp to verbal communication where appropriate. *When things are only said on the phone, in person, in emails that don't include the whole group, or in one-on-one chats, information gets lost, forgotten, or misinterpreted. The problems expand when someone joins or leaves the project.*
* __Always prefer pasted text to attached files__. Google Docs are also preferable to attachments. Opening files is annoying.
* __Name your tasks sensibly__. Ideally prepend the task with the site (if appropriate) and page. e.g. `WG: Product page: change lead time copy`
 
####User experience and visual design
* Agree on outcomes *before* deciding on features
* Use personas to guide decisions
* Shared understanding and hypotheses over design heroes
* Use the [styleguide](http://www.easyart.com/docs/styleguide) to build pages from modules
* Start with the lowest fidelity way of describing an idea, and validate as early as possible
* Usertesting.com for user testing, and Optimizely for split testing

Covered in more detail in [this post](http://easyart.github.io/2014/02/16/lean-ux-at-easyart/).

###Language style guides
  
####Javascript
[Airbnb's style guide](https://github.com/airbnb/javascript) as a starting point. Perhaps with some exceptions:
* Prefer `function test () {` to `function test() {`. [Because, Crockford](http://www.jslint.com/).
* Prefer double quotes for strings
* Note: what documentation style?
* Note: or is are we using [Google's styleguide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)?
  
####Ruby
[Github's style guide](https://github.com/styleguide/ruby) as a starting point, with some exceptions:
* Not strict on `Keep lines fewer than 80 characters`. Just use common sense.
* Note: what documentation style?
  
####CSS
* Sass style guide
* [Craven gem](https://github.com/easyart/craven)

####File naming rules
* **Always** lowercase
* Public-facing files should use hyphens. This includes images.
* Code files should use underscores.

###Task workflow

####Code
* __Simple git branching__. Master, and your feature branches. Master is always deployable. No exceptions.
* __Branch naming__. Prefix all branches with your initials in lower case eg. *'jp-my-feature-branch'*
* __Pull requests for QA__. This is for knowledge sharing and sanity checking as much as "approval". Do so as early as possible. For minor changes and FYIs, [add comments to the lines in Github](https://help.github.com/articles/adding-commit-comments). Comments in the pull request are preferable to Basecamp if the change is in code. 
* __Reviewing your teammates' code needs to be an equal priotity to writing new code__. Momentum is lost when changes await review too long. You are in charge of chasing someone to give their stamp of approval (the `:shipit:` (:shipit:) emoji). Kick up a fuss if anyone is blocking your feature from being completed. **Don't merge to master after 3pm on a Friday unless you plan to monitor it.**
* __Deployment via CI rather than direct deployment__. CircleCI will always deploy `master -> master` and `staging -> staging` if the tests pass, and will also update our dashboard and monitoring services with the release details.
* __Anything can go into shared staging__. Changes should be pushed one-way from your feature branch. e.g. `git push --force origin feature-branch:staging`. Never run a staging branch locally. Developers also have their own staging servers.

###Monitoring and alerting
We use the following services:

* [New Relic](http://www.newrelic.com) for application monitoring and alerting (and powering our dashboards)
* [Logentries](www.logentries.com) for logging and some alerting

####In the event of a problem
Each team member will be alerted via the New Relic app when the **errors are > 5%** or the **apdex is < 0.5**, then log into chat and communicate what you're investigating before you do it ([READ-DO](http://lumbertribe.wordpress.com/2010/02/21/checklist-manifesto/)). Check the status pages on key services.

####References
* [The Twelve-Factor app](http://12factor.net/)
* [Thoughtbot Playbook](http://playbook.thoughtbot.com/)
* [North](https://github.com/Snugug/north)
* [Lean UX](http://www.amazon.co.uk/Lean-UX-Applying-Principles-Experience/dp/1449311652)
