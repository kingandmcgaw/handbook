Styleguides
===========

###Language style guides

####General principles:
  * Clarity over cleverness
  
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
* __Your _me_ page is your list of _accepted_ tasks__. If a task is assigned to you that is unclear, send it back to the assigner for clarification. If it's too big, request that it be split up. Don't be shy about challenging.
* __Each project should have a backog__. These are tasks that need doing, but are unlikely to get done in the next 30 days.
* Tasks that are done but need to be reported back on (or need to be reverted in the case of a time-sensitive content change) should have a due date and :watch: appended. Example: **Lazy load related images :watch: (Jan 1)** would indicate the success of the task will be reported back into the ticket on January 1st.
* __Always append notes__. We will always have distractions, forget what we agreed etc. Where possible, use Basecamp for meeting notes
* Always prefer pasted text to attached files.

####Development workflow
* Simple git branching. Master, and your feature branches.
* Master always deployable. No exceptions.
* CircleCI will always deploy ``master -> master`` and ``staging -> staging``. Never deploy directly to Heroku on production branches.
* Staging is a bucket (you can force any change into it)
* Pull requests for any functional changes (or anything significant)

####Monitoring and alerting
* Pingdom
* New Relic
* Logentries

####Things we agree with
* http://12factor.net/
