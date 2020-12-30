Replicated - Here Comes Trouble(shoot.sh)

## Environment setup

Before you can dive into `troubleshoot.sh`, let's first complete setup of our `kubernetes` environment by running `launch.sh`{{execute}}. This script will need a few minutes to connect the `controlplane` to the k8s `nodes`. 

While that's going, let's chat a bit about who I am & why I'm here!

## Krew Setup

Welcome back, now that kubernetes is up & running we're ready to install `krew`, the plugin manager for `kubectl`. Use this handy script to do the heavy lifting for you:

First, download `krew-installer.sh` to the `controller` node:

`curl -O krew-installer.sh https://raw.githubusercontent.com/OGtrilliams/katacoda-scenarios/main/replicated-demo/krew-installer.sh`{{execute}}

Now, execute the script using `BaSH`:

`chmod +x krew-installer.sh`{{execute}}
`bash krew-installer.sh`{{execute}}

Once the script finishes running, let's verify that it is working correctly by running a simple command:

`kubectl krew -h`{{execute}}

If you receive an error message stating that the plugin isn't found, run `source ~/.bashrc`{{execute}} to refresh the terminal window.

Now that the `krew` plugin is installed, we're ready to move on with configuring `preflight` & `support-bundle`. 

Let's go!
