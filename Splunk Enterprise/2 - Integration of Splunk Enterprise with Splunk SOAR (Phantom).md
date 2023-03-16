
### Downloads to get started with Integration of SOAR

- Install the **Splunk App for SOAR Export** on Splunk Enterprise.
	- To do so click on **+ Find more Apps** on the panel on the left hand side
	- Then search for Splunk app for SOAR export
	- Click on install and provide your Splunk login ID and Password (Not Splunk Enterprise's)

- Install Splunk Common Information model.
	- To do so click on **+ Find more Apps** on the panel on the left hand side
	- Then search for Splunk Common Information Model (CIM)
	- Click on install and provide your Splunk login ID and Password (Not Splunk Enterprise's)

### Configure Roles

- Once Splunk App for SOAR Export is installed, a new role namely phantom needs to be added and assigned to the particular user forwarding the data onto phantom. Here we've assigned the role to admin.
- Go to the Settings tab on the nav bar and click on roles under **Users and Authentication**
- In the Admin section, click on the edit option in the actions section
![[rules 1.PNG]]

- Click the checkbox to the left of the phantom role to assign it to admin and then click save
![[rule 2.PNG]]


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
		`[verify_certs]
		value = false`
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
