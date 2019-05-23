# Challenge 2
## Context

Cordant Group is using Freshservice as a ticketing system to record and process the various
tickets created by end users.
Currently the Service Desk have to use multiple different tools to find out information about a
requester and to carry out simple actions, such as password resets.

## Challenge

Your goal is to create a Freshservice App that will :
- Show the agent the requesters Manager, Brand / Department, Cost Centre and Contact
Details

- Have a button that launches a user specific URL to the Google Admin Console and Better-
cloud

- Generate a secure password and set it for the user in Google, this password will then be
shown to the agent and allow them to quickly copy it
- Update the ticket with a private note stating the password was reset using the automated
tool.

## Resources

### Password Reset API
URL : https://r2hxsz2nwg.execute-api.eu-west-1.amazonaws.com/dev/hackathon/google

Method : POST
### Payload :
```json{
agent: String - the email address of the logged in agent,
user: String - the email address of the person the request is for,
password: String - the new password - plain text or MD5 hash,
apiKey: String - we’ll provide you with these
}
```
### Output
```json{
statusCode:200,
message:’sucessfully reset password for [user]’
}
```
## Bonus
If you are done with the work above, then here are some added extras to consider:
- Only show the password option when :
- The request has an “Approved” status
- The user has a manager listed
- Automatically send the password to the users manager
- Hash the password using MD5