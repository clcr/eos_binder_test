# eos_binder_test
This is an experimental repositroy trialling Binder for teaching and collaboration.
Binder is a service that provides web-hosted Jupyter (and possibly R) notebooks; the users do *not* need to install anything aside from a web browser and only have to click on the button below:

[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/clcr/eos_binder_test/master)

To make a notebook available online, simply;
1. Push it to this repositorie's master branch
2. Add any dependencies (conda or pip installs, ect) to the environment.yml file. Please keep these to a minimum, as each dependency increases the start-up time of the binder.
See https://conda.io/docs/user-guide/tasks/manage-environments.html#create-env-file-manually

A few limitations;
-It's limited to no more than 2gb of memory (so nothing above the most basic image processing)
-Any work you do, you'll have to save externally; you **cannot save changes** to the Binder image of the notebook. If you want to modify a notebook permanently, you will have to edit it on your local machine and push it to this repository.
-A notebook can have no more than 100 concurrent users; please bear this in mind if you are planning on using this to run seminars

## Technical details
When you click the button above, binder.org will create a Docker image for this repository. A Docker image is a kind of lightweight virtual machine with the systems (defined by the environment.yml file). Once this is done, binder.org will creade and host a copy of this Docker image for each user; it is this hosting that imposes the resource limits above. Whenever the repository is changed, binder.org will create a new Docker image to replace the old one.

https://mybinder.org/
