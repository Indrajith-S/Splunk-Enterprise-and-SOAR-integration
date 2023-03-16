Splunk Phantom now know as splunk SOAR is a security orechestration, automation and response tool that involves the use of machine learning and artificial intelligence to programically detect, investigate and remediate threats.

### Data Sources

- Ingesting data to splunk is pretty much easy using softwares like Splunk Enterprise, or Splunk ITSI or even using Custom Security solutions and your common firewall devices.
- Virus and malware scanners also are a source of data ingestion.

### Common Event Format (CEF)

- CEF is an open log management standard.
- In a nutshell CEF is a format in which data needs to be ingested into Splunk Phantom.

### Containers

- Containers are basically security events in Splunk Phantom.
- It generally contains one or more events.
- When a data source or "event" is ingested in CEF format into phantom, it is then termed as container.

	##### Container Schema
	
	- Containers are nothing but JSON objects in phantom containing key value pairs pertaining events or said container.

	##### Container Label
	- A container or event or its contents can be indentified easily based on the container label.
	- Phantom UI's integration of said label provides us with ease of navigation.
	- We can also run playbooks on containers which match a specific label.
	- Ex: "label": "incident"

	##### Artifacts
	- Pieces of information in a container.
	- Artifacts have their own schema, which hold information such as label, container ID (so that they can be matched back to the container they belong to), CEF(normalized field), data (holds raw data)

### Case
- Case in layman's terms is container of containers.
- Sometimes to analyze a particular situation, we might face the need of analyzing details from multiple containers.
- In this situation we promote a container to a case and can add all other related containers to it too.
![[Screenshot (30).png]]


### Playbooks

- Playbooks are basically any automated action or analysis performed on containers.
- Playbooks are used hand in hand by calling splunk apps to perform actions on these containers.

### Apps and Assets

- Assets - Intances of the app managed by an owner.
- Apps are entities used to perform actions and as above-mentioned are used by playbooks.

### Workbooks

- Workbook is a defined set of tasks that can be automated and run in interdependent phases.
- For every phase a particular task can be executed or even a playbook can be executed as part of a task.

![[Screenshot (31).png]]

