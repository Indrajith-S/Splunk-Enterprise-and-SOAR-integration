
### Configuration of Splunk App for SOAR Export

- Go to the Splunk App for SOAR Export App and click on the configurations tab in the nav bar
- Before Clicking on New Server, you need to understand some concepts - 
	- This will help your SE understand which phantom server you wish to connect to and forward the logs to.
	- Hence we require an Authorization Token from phantom which can be considered as an API Key of sorts that will facilitate our connection to phantom.
	- Now like any other app, the data being transferred to phantom needs to be encrypted and protected, hence a certificate authority verified SSL certificate needs to be present so that SOAR and SE can communicate safely.
	- Now as this is a testing environment, we will be disabling SSL.

	##### Disabling SSL Certificate
	- Navigate to the splunk/etc/apps/phantom/local and open the phantom.conf file (create phantom.conf if it doesn't exist).
	- Now, here, type in the following - 
		``[verify_certs]
		value = false``
	- Now restart your SE instance.
	- Upon restarting, you can see that HTTPS certification verification is disabled.


	##### Authorization Token
	- To do so, login to phantom and go to administration from the nav bar on the left hand side
	- Then click on Users under the User Management section
		![[Captureuser 1.PNG]]
	- Click on the blue **+ User** button 
	- Under User type in the first section, select automation.
	- Enter an username and leave the allowed IPs as any.
	- Change the default label to events and leave the rest as is and click on save.
		![[user2.PNG]]
		
	- Once you've created an user you can see the new user in the list of other users.
	- Now on your particular user, click on the three horizontal dots and select edit.
		![[user3.PNG]]
		
	- You can see a field with the name Authorization Configuration for REST API.
	- click on show token and then click on copy on clipboard to copy it.

- Now navigate back to SOAR app for export in Splunk Enterprise and click on Create Server.
- Paste the copied token in the Authorization Configuration field and leave the rest as is and click on save.
	![[user4.PNG]]

- Once the server has been successfully created click on the manage drop down under actions menu select Test Connectivity to test if your connection is successful.
- Please Note: If u haven't configured a static ip address for your phantom (if in a test environment then it is okay), then you will have to edit your server settings in SE and change the ip to the current ip of phantom.
