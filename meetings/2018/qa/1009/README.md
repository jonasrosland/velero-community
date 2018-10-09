# Ark Q&A Session, Oct 10, 2018

You can find the video recording of this meeting [on YouTube](https://www.youtube.com/watch?v=l8XRmtohJBM)

# Agenda

## Introductions

Jorge Castro
Nolan Brubaker
Steve Kriss 
Andy Goldstein
Wayne Witzel III
Carlisia Pinto
Tim Carr
Megan Bruce

## Announcements

* We have the Foqal bot to respond to questions!
  - This bot will monitor Slack for questions that have been answered and will try to respond when they come up again.
  - It will also scrape our documentation and try to provide answers from them.
* Thanks to Kubedex for the mention https://kubedex.com/top-10/
* We're using the https://github.com/heptio/ark-community repo to track notes for meetings and other community management things.
  - Notes for the Q&A will go there.
* Heptio Ark [v0.9.7](https://github.com/heptio/ark/releases/tag/v0.9.7) was released Thursday, Oct. 4.
* Kubecon attendance
   - Andy Goldstein, Carlisia Pinto, and Ross Kukulinksi will be attending KubeCon in Seattle. Reach out to us if you want to meet. 

## Shoutouts

Thanks to the following GitHub users for contributing bug fixes for the v0.9.7 release!

* mwieczorek
* marctc
* shubheksha
* timoreimann

## Live Questions

* Moody Saada: Helm chart for Ark doesn't have a way to expose prometheus metrics. Is there an alternative way to trigger alerts on backup failures?
  - A: The Ark team doesn't currently maintain the Helm chart for Ark. The suggested path to getting this it to open an issue with the Helm repo, asking to add the Prometheus metrics to the Helm chart.


## Last Month's Questions

Some topics that have come up in the last month or so on Slack and the mailing list.

* When will the next Ark release be? (announce 2 week bug fix cadence)
  - Bug fix releases every 2 weeks, if there are fixes to be merged. v0.9.7 on October 4 was the first release under this schedule.
  - We'll tag things that are potential backport candidates with `Backport Candidate` label in GitHub.
  - v0.10.0 is coming along, hopefully by October/November. We will be doing beta releases and would love having help testing the new features out.
  - Historically we haven't done backports once a new release has come out. However, we'll evaluate issues and see if backports to older series will be needed.
  - We're working towards a 1.0 release, for stability. We're evaluating the breaking changes and deciding which will come in 1.0 and those which could justify a 2.0.
* How can I get Prometheus metrics for Ark?
  - We have annotations on the Ark pod to allow prometheus to find it, but several open issues to provide more/better dashboards.
  - See https://github.com/heptio/ark/issues/84 for tracking this. We'd eventually like to close this and make smaller, more specific issues for more metrics.
* What's the procedure for using Azure?
  - See https://heptio.github.io/ark/v0.9.0/azure-config
  - The main subtlety here is resource groups with AKS clusters.
* I get a timeout error when restoring a persistent volume, how do I fix it?
  - That's a bug that will be resolved in v0.10. (See https://github.com/heptio/ark/pull/715)
  - Ark used to have a 30 second wait for volumes to become ready. This was removed since Kubernetes will keep trying to attach the volume for us.
* Will Ark support Kubernetes volume snapshots introduced in 1.12?
  - We need to do an evaluation on the feature, but it is also still alpha. Hoping to test once v0.10 is released.
  - This is just a data snapshot - it doesn't include all the Kubernetes objects that Ark does.
* Is the Ark Helm chart maintained by the Ark team?
  - Not currently; it was contributed by the community. We will help as we are able.
  - We're happy to help others contribute to it.
* Can my users manage Ark for their own namespaces?
  - This isn't well tested; we need to investigate RBAC/ACL integration in a secure manner.
  - It can probably work if you have several instances of Ark running to manage individual namespaces, but there are security issues around restoring cluster scoped resources, like persistent volumes and cluster role bindings. These could possibly lead to a privilege escalation.
  - See https://github.com/heptio/ark/issues/350 and https://github.com/heptio/ark/issues/18
 
## Schedule for the rest of 2018

* We won't be having an October 23 design session.
* Next Q&A is November 13. [YouTube live stream](https://www.youtube.com/watch?v=nVoEJv_ZIiM)
* Next design discussion will be November 27. Particularly interested in user input about encryption requirements. [YouTube live stream](https://www.youtube.com/watch?v=Ml5lN4cV1Yk)
* No streams in December. KubeCon's on December 6 and December 25 is Christmas.
