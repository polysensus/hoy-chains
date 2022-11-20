# hoy-chains
fluxcd chain configurations and automation for the hoy-dev-1 google cloud project

# Basic workflow for updating a chain

Assuming the chain is `caimst'. Replace `caimst' with the chain name otherwise

* **Be sure it is ok to destroy it**
* Suspend the CD & teardown the currently configured resources: `task caimst-destroy`
* edit some manfiests experimentally
* Suspend the CD & teardown the currently configured resources: `task caimst-apply`
* IF they applied ok consider updating benchblock so generation works cleanly next time
* Destroy again to clean up: `task caimst-destroy`
* Restart CD automation: `task resume-cd`
* To imediately recreate the chain: `task reconcile`
* Otherwise fluxcd will do it in a minute or two
