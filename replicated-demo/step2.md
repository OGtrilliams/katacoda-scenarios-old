## Installing Preflight

Now that `krew` plugin has been added to `kubectl`, we're ready to install `preflight`. 

What's `preflight`?

`Preflight` is a powerful little tool that can be used to verify that client environments are properly configured to support your application(s).

Installation of `preflight` can be done in one step with help from the `krew` installer:

`kubectl krew install preflight`{{execute}}

Once installation completes, we can verify that `preflight` is running using the example check available at `https://preflight.replicated.com`{{open}}

This check has `analyzers` configured to verify k8s cluster version & minimum nodes, Docker container runtime, storage class, as well system resources such as RAM, CPUs for a typical Kubernetes environment.

`kubectl preflight https://preflight.replicated.com`{{execute}}

Use the `^` & `˅` keys to navigate through the results. When you're done, press `q` to exit back to the terminal.

Now that we've verified `preflight` functionality, let's go a little further by creating our first custom `preflight` check.
