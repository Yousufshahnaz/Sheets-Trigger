## Usage: 
**To run:** Select Run --> createTrigger

This will automatically start the trigger that runs this script every hour or otherwise specified time increment in createTrigger() (currently set to every hour).
      
**To change the time frame** from which contacts are moved to the "Needs follow-up email sheet", change the number specified in the variable timeFrame.
   
***Note:** selecting Run --> createTrigger multiple times will result in multiple triggers. To manage triggers, go to Edit --> Current project triggers to delete triggers. Or, run the function deleteTriggers() to delete all current triggers.*
      
### What the code does:
* Each time the script is run, it loops through each row in the "Leads" sheet. For each row, it checks to see if the contact has responded to an email as indicated by column M.
* If the contact has responded, the script will automatically copy the contact info to the "Has responded" sheet and mark 'Y' in column N to indicate that this information has already been processed.
* If the contact has not responded, the script will begin a counter that is incremented each time the script is executed. In this fashion, the script will be able to keep a record of how long the contact has not responded to previously sent emails.
* If the contact responds before the specified time frame (72 hours) has passed, the contact information will be copied over to the "Has responded" sheet and the script will stop incrementing the counter.
* However, if the contact never responds within the specified time frame, the script will mark in the Log column that it is adding the contact to the "Needs follow-up email" sheet.
* It will then be added to that sheet. Again, if the contact at any point responds, the scriptwill copy that information over to the "Has responded" sheet and make a note that the contact has responded back. 
