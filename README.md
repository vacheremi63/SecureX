# Automated Remediation with SecureX for Stealthwatch Cloud and AMP4E 

This is a SecureX playbook to automate quarantine through AMP4E upon receiving a Stealthwatch Cloud alerts. In this playbook, we use an e-mail trigger to start the workflow. When Stealthwatch Cloud gets an alert, it will send an e-mail to a mailbox. 
SecureX is configured with an IMAP listener on this mailbox to collect the alert e-mail. 
When the e-mail is retrieved, the workflow will parse the information to only keep the private IP address. 
Later, it will query AMP for GUID using the IP address from the e-mail. Once the the workflow has AMP GUID (which is the identifier of the endpoint in AMP) it will check the isolation status of the endpoint to make sure it is not isolated already. 
If not, it will isolate it and notify through Webex Team

[https://youtu.be/nY9nWVrgO4I](https://youtu.be/nY9nWVrgO4I)


## Configure 

* Configure e-mail in Stealthwatch Cloud : 








* Minor update from version v4.0 that creates 4 group objects in instead of 2. 
* It now creates 2 URL group objects for Optimize+Allow and for Default category, and does the same for the IP group objects.
* [WARNING] It adds a dummy IP range (240.0.0.0/4) or dummy URL (example.com), if Microsoft does not return any addresses. Microsoft does not always return full lists. Sometimes they only return the Default URL’s for example, since they don’t own those IP ranges. This can cause a Policy Deploy failure, hence the dummy addresses.
