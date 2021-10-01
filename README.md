# Everplans Data Engineer Code Test

Instructions for the Everplans mobile developer code test.

Congrats! You've been invited to complete a take-home code test. We're very excited to see your work!

This test is an opportunity for the Everplans developer panel to see a reasonably non-trivial sample of how you write code, and think about data. Over the years we have found this is a great context for evaluating how you can be an effective member of the team. We prefer this over asking you to solve code problems live, in front of other people--as though it may be an impressive skill in and of itself, it has little bearing on how you'll peform on the job, with our team.

This is an aribrary dataset and analysis by design. Please don't feel compelled to complete anything more than the minimum requirements for this test, as we want to be respectful of your time. (If you do want to embelish, go for it! But it's really not necessary!)

## The Test
* Using the provided raw dataset, create a script in the language/framework of your choice (all things being equal, Python, or better yet Jupyter Notebooks would be our preference, but anthing reasonably modern is acceptable) that synthesis two datasets. Context for the dataset and requirements for the two datasets are provided below.  

* It's easiest to submit a github repo/link of an your script and any supporting assets. All instructions to run, necessary dependencies, etc. should be adequately documented in a README. A zip file of the repo is also perfectly fine. 

* DO NOT SUBMIT the synthesized datasets, we'll run your script and look at the synthesized datasets locally. 

## Things to keep in mind:

* Time commitment: This should take an experienced developer only a few hours to complete. If you find it's taking longer and is disruptive to your schedule, please communicate and manage your recruiter's expectations. We can figure something out and work with you. (Your communication skills are part of this test!)

* Communicate, communicate, communicate! Ask clarifying questions, keep your recruiter updated on your timing, and expectations of when we can expect to see your work. If things come up (no problem!) just keep us in the loop! 

* Give some context to your submission. A README file is a great way to let us know anything that might be useful. Show us how you think! 

## Dataset context
The [dataset](raw_event_log.csv) provided is an eventlog of a small subset of activities done by new users on the everplans platform. (Don't worry this was randomly generated. No real user data can be found here. We take user privacy very seriously!) The eventlog covers events representing the following use cases: 

* Users will create their accounts, and then get a confirmation email. (Some users never come back, others will click the activation link in the email). Users who have activated will get the activation event. 

* After that users will login, and put things in their vaults. Sometimes users remember to logout, othertimes, their sessions just timeout. Ever user in the system has a unique 

* Sometimes users comeback a bunch of times, sometimes they only come once or twice (or never). 

The fields in the dataset should be self explanatory, but just to be clear: 
* user_id -- A unique hex based ID that represents each user. Everytime the same user does something, that same user_id will be used to log the event. 
* timestamp -- The Date and Time that the event occured. 
* event -- a string representig the event that occured. All possible events are: [
    'create, 
    'activate',
    'login',
    'logout',
    'add_to_vault']



## Acceptance Criteria:
Using your preferred language or platform (Python, Jupyter Notebook, SQL, etc.) parse the dataset, clean up any noise or missing/partial data, and  ensure datatypes are correctly parsed. Create two these two synthesized datasets, and have your script save them as csv files.  

* create a dataset that has 1 record for each unique user ID, with the following dimensions and measures: 

  * Date of activation. (user may or may not have activated). 
  * total_logins: The total number of times the user has logged in.  
  * total_vault_events: The total number of times a user has done the add_to_vault event. 
  * time_to_activate: The number of seconds it took for teh user to go from create to activate. 

* create a dataset that aggreates by month (use activation month) based on the previous dataset, which provides the following dimensions and measures: 
  * activation_month (can be any reasonable format, string or date)
  * average_days_to_activate: Mean of time_to_activate stated in days(use of decimal places is fine) 
  * average_logins: Mean of total_logins 

Thanks so much! We appreciate your time, and can't wait to see your work!