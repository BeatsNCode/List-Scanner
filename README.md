# List Scanner 
##### Klaviyo SA Tech Assessment

In this challenge, the goal is to create a integration using Twilio's Lookup API and Kickbox's Email Verification API, to periodically validate any list's Email and Phone Number data. While Double Opt-in is a best practice in the List Collection domain, it is not always an option customers are looking to consider as part of their subscriber collection strategy. For this reason, I see some benefits in this potential fallback, as it allows a user to validate profile data on the back-end, with little impact to the user experience.

#### Visual Representation of this solution
https://imgur.com/a/H0T4uEe

#### This solution will:
- Pull Profile data from a specific Klaviyo List
- Pull Email and Phone Number from Profile
- Run Email Address through the Kickbox Email Verification API
- If Email is not marked as `deliverable` by Kickbox, add to Klaviyo's Suppression List
- Else, do nothing
- Run Phone Number through Twilio's Lookup API
- If Phone Number type is not `mobile`, according to Twilio, suppress number for SMS
- Else, do nothing
- Add Email and Phone Number results to database of previously scanned profiles
- Track event in Klaviyo, based on lookup results

###### Klaviyo Account ID Used for Testing: `Qg3FLb`
###### List ID Used for Testing: `UwaMMy`

To test functionality of this solution, first import CSV file located in `csv_file` folder into `SA Tech Assessment List`, and assign both Email and SMS consent, if consent is not already present.
