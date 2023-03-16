- A playbook is a program designed to perform actions in SOAR
- Playbooks folow a process flow, taking the outcome of one action into account when performing the next.
- One can edit playbooks using VPE (Visual playbook editor)
- Phantom comes with community playbook installed
- When we visit the playbook section in the nav drop down, we see multiple playbooks from both community repo and local repo.
- On the top right corner we have the option of creating a new playbook.
- This will open a new window, upon which Automation should be selected.

#### Creating your own playbook

- Each box here is a method or function of python
- Now as these playbooks play hand in hand with apps, we must have an idea of the event requirements for every app and its output actions, Hence reading the documentation is very important.
- So here we go with the example of cisco asa, with our events being - username.
- In a nutshell, if it wants to terminate a session it requires an event containing an username field and then it tells us what the output of that action is going to be.

- Coming to our VPE, we click and drag the semicircle under the start tab, which lists a couple of options here which corresponds to the tab on the left hand side with the label "ADD".
![[test playbook.PNG]]