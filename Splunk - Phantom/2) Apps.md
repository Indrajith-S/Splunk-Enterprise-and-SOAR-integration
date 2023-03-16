#### Unconfigured Apps

- Once you're in apps, for demo purposes search for **Cisco asa**.
- Click on Unconfigured Apps if it isn't configured already in your app.
- Donwload the .tgz file or tarball.
- Once that is done, we see an install app option on the dashboard in blue.
- Click on it and select the .tgz file you just downloaded to install it.

![[download.png]]

![[download2.png]]

![[install.png]]

- And by clicking on supported actions we find the functionalities of the application.
- for example, here, cisco asa supports 7 actions:
	- terminate session - Terminates all VPN sessions of a user
	- list sessions - List the current VPN sessions
	- unblock ip - Unblock an IP
	- block ip - Block an IP
	- get version - Gets the software version information of the device
	- get config - Gets the current running config of the device
	- test connectivity - Validate the asset configuration for connectivity. This action runs a few commands on the device to check the connection and credentials
- Under **Assest Configuration** we got **Asset Info**, **Asset Settings**, **approval Settings**, and **Access control**.
- **Asset Info** contains the name and description of the asset you give.
- **Asset Settings** includes the ip address, username and a password for (not of) the particular asset.
- **Approval Settings** are your administrative roles that take care of approval of actions like block, unblock, etc. If any personnel doesn't respond on time, the action is delegated on to any subordinate.
- **Access Control** inlcudes the access controls of particular personnels, dictating who can initiate that action or not. For example, we don't want a particular personnel to have access to take action for a particular device when it comes to writing a playbook.


#### Configured Apps

- Let's take a look at configured apps for example, particulary, **Maxmind**, and navigate towards Ingest Settings, we find something called labels.
- Now this label is used to identify this particular data source that is feeding data into phantom and playbooks act on these labels.

