Easyart developer handbook (draft)
===========

####General principles:
* Clarity over cleverness. Your code is only good if someone else undertands it.
* Never work in isolation. Great benefit comes from oversharing and overcommunication. Accept the benefit of your teammates' feedback comes at the expense of some chatter/noise. [Increase bus factor](http://en.wikipedia.org/wiki/Bus_factor).

###Language style guides
  
####Javascript
* [Airbnb's style guide](https://github.com/airbnb/javascript) as a starting point. Perhaps with some exceptions:
  * Prefer ``function test () {`` to ``function test() {``
  * Prefer double quotes for strings
  * Note: what documentation style?
  
####Ruby
* [Github's style guide](https://github.com/styleguide/ruby) as a starting point, with some exceptions:
  * Not strict on ``Keep lines fewer than 80 characters``. Just use common sense.
  * Note: what documentation style?
  
####CSS
* Sass style guide
* [Craven gem](https://github.com/easyart/craven)

###Task workflow

####Basecamp
* __Your _me_ page is your list of _accepted_ tasks__ that can be achieved within a 30 day period. It is your responsibility to make sure these tasks are completed.
* __Tasks must be clear and actionable__ if they are going to stand any chance of getting completed. If a task is assigned to you that is unclear, send it back to the assigner for clarification. If it's too big, request that it be split up. Don't be shy about challenging. Goals and tasks should not be mixed.
* __Each project should have a backog__. These are tasks that need doing, but are unlikely to get done in the next 30 days. The project owners should regularly prioritise the backlog.
* __Ruthlessly remove tasks__ that are unclear, or low priority. Care should be taken to inform everyone it's being removed and why. If they are importany they will come back.
* Tasks that are done but need to be reported back on (or need to be reverted in the case of a time-sensitive content change) should have a due date and :watch: appended. Example: **Lazy load related images :watch: (Jan 1)** would indicate the success of the task will be reported back into the ticket on January 1st.
* __Tasks must be assigned__. Tasks that are not assigned are extremely unlikely to be actioned.
* __Always append notes__. We will always have distractions, forget what we agreed etc. Where possible, use Basecamp for meeting notes
* __Always prefer pasted text to attached files__. Google Docs are also preferable to attachments. Opening files is annoying.

####Development workflow
* __Simple git branching__. Master, and your feature branches.
* __Always open a pull request__ for any functional changes (or anything significant). This is for knowledge sharing. For minor changes
* __Never merge your own pull request__. This means you are in 
* __Master is always deployable__. No exceptions.
* CircleCI will always deploy ``master -> master`` and ``staging -> staging``. Never deploy directly to Heroku on production branches.
* Staging is a bucket (you can ``--force`` any change into it). Changes should be pushed one-way from your feature branch. e.g. ``git push --force origin feature-branch:staging``

####Monitoring and alerting
* Pingdom
* New Relic
* Logentries

####Things we agree with
* http://12factor.net/
