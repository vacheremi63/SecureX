# Automated Remediation with SecureX for Stealthwatch Cloud and AMP4E 

This is a SecureX playbook to automate quarantine through AMP4E upon receiving a Stealthwatch Cloud alerts. In this playbook, we use an e-mail trigger to start the workflow. When Stealthwatch Cloud gets an alert, it will send an e-mail to a mailbox. 
SecureX is configured with an IMAP listener on this mailbox to collect the alert e-mail. 
When the e-mail is retrieved, the workflow will parse the information to only keep the private IP address. 
Later, it will query AMP for GUID using the IP address from the e-mail. Once the the workflow has AMP GUID (which is the identifier of the endpoint in AMP) it will check the isolation status of the endpoint to make sure it is not isolated already. 
If not, it will isolate it and notify through Webex Team

[https://youtu.be/3dW6_CYSGR4](https://youtu.be/3dW6_CYSGR4)


## Configure 

* Configure e-mail in Stealthwatch Cloud : 
In Stealthwatch Cloud --> Top Right wheel --> Services/Webhooks --> E-mail 

* Import the JSON file in SecureX : 
In SecureX --> Orchestration --> Workflows --> Import --> Browse --> SWC/AMP Remediation JSON File

* Target to Configure 
    --> AMP for Endpoint Account 
    
* Account Keys to Configure : 
    --> Mailbox used 
    --> AMP Credentials 
    
* Variables 
   --> Webex Team key 
   
   

