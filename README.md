Easyart developer handbook (draft)
===========

####General principles:
* __Clarity over cleverness__. Your code is only good if someone else undertands it.
* __Never make changes unilaterally__. Great benefit comes from oversharing and overcommunication. Accept the benefit of your teammates' feedback comes at the expense of some chatter/noise. [Increase bus factor](http://en.wikipedia.org/wiki/Bus_factor).

###Language style guides
  
####Javascript
* [Airbnb's style guide](https://github.com/airbnb/javascript) as a starting point. Perhaps with some exceptions:
  * Prefer `function test () {` to `function test() {`. Because, Crockford.
  * Prefer double quotes for strings
  * Note: what documentation style?
  
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
* __Tasks must be clear and actionable__ if they are going to stand any chance of getting completed. If a task is assigned to you that is unclear, send it back to the assigner for clarification. If it's too big, request that it be split up. Don't be shy about challenging. Goals and tasks should not be mixed.
* __Each project should have a backog__. These are tasks that need doing, but are unlikely to get done in the next 30 days. The project owners should regularly prioritise the backlog.
* __Ruthlessly remove tasks__ that are unclear, or low priority. Care should be taken to inform everyone it's being removed and why. If they are important they will come back.
* __Indicate callbacks__. Tasks that are done but need to be reported back on (or need to be reverted in the case of a time-sensitive content change) should have a due date and `:watch:` appended. Example: **Lazy load related images :watch: (Jan 1)** would indicate the success of the task will be reported back into the ticket on January 1st.
* __Tasks must be assigned__. Tasks that are not assigned are extremely unlikely to be actioned.
* __Always append notes__. We will always have distractions, forget what we agreed etc. Where possible, use Basecamp for meeting notes
* __Always prefer pasted text to attached files__. Google Docs are also preferable to attachments. Opening files is annoying.

####Git
* __Simple git branching__. Master, and your feature branches. Master is always deployable. No exceptions.
* __Always open a pull request__ for any functional changes (or anything significant). This is for knowledge sharing. For minor changes and FYIs, [add comments to the lines in Github](https://help.github.com/articles/adding-commit-comments).
* __Never merge your own pull request__. This means you are in charge of chasing someone to give their stamp of approval with a :shipit: message. 
* __Reviewing your teammates' code needs to be an equal priotity to writing new code__. Momentum is lost when changes await review too long.
* __Deployment via CI__. CircleCI will always deploy `master -> master` and `staging -> staging` if the tests pass. Never deploy directy.
* __Anything can go into staging__. Changes should be pushed one-way from your feature branch. e.g. `git push --force origin feature-branch:staging`. Never run a staging branch locally.

####Monitoring and alerting
* Pingdom
* New Relic
* Logentries

####Things we agree with
* http://12factor.net/
