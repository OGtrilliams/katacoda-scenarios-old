Now that we're familiar with `preflight`, let's move on to the 2nd component in `troubleshoot.sh` - `support-bundle`. 

## What's a `support-bundle`?

A support bundle is an archive that's created in-cluster, by collecting logs and cluster information, and executing specified commands (including redaction of sensitive information). After creating a support bundle, the cluster operator will normally deliver it to the 3rd-party application vendor for analysis and disconnected debugging. 

The `support-bundle` plugin collects data from the cluster, automatically redacting sensitive cluster info, then *optionally* analyzes the data to provide remediation steps.

The collected data is then stashed on the client host in a `.tar.gz` archive ready to be be shared with support teams - saving precious time on walking customers through the data collection phase & streamlining the troubleshooting process. 

Let's start by installing `support-bundle` using the `kubectl` `krew` plugin. 

`kubectl krew install preflight`{{execute}}

Now that the `support-bundle` plugin is installed, we can verify functionality by running an example check from `https://support-bundle.replicated.com`{{open}}:

`kubectl support-bundle https://support-bundle.replicated.com`{{execute}}

This will create a `.tar.gz` archive on our host with a filename like `support-bundle-$(date)` containing default cluster info along with results of a few `analyzers` we saw earlier in the exercise.

Or, we can skip to building our own custom `support-bundle` collectors.
