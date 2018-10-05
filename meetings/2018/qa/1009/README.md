# Ark Q&A Session, Oct 10, 2018

# Agenda

## Announcements

* We have the Foqal bot to respond to questions!
  - This bot will monitor Slack for questions that have been answered and will try to respond when they come up again.
  - It will also scrape our documentation and try to provide answers from them.
* Thanks to Kubedex for the mention https://kubedex.com/top-10/
* We're using the https://github.com/heptio/ark-community repo to track notes for meetings and other community management things.

## Last Month's Questions

Some topics that have come up in the last month or so on Slack and the mailing list.

* When will the next Ark release be? (announce 2 week bug fix cadence)
  - Bug fix releases every 2 weeks, if there are fixes to be merged.
  - We'll tag things that are potential backport candidates with `Backport Candidate` label in github.
* How can I get Prometheus metrics for Ark?
  - We have annotations on the Ark pod to allow prometheus to find it, but several open issues to provide more/better dashboards.
* What's the procedure for using Azure?
  - https://docs.google.com/document/d/1Qyq59RkZZSh6aopiUGGQZSsQA9fTX4OXAA_XM9ZTPPE/edit#
* I get a timeout when restoring a persistent volume, how do I fix it?
  - That's a bug that will be resolved in v0.10. (See https://github.com/heptio/ark/pull/715)
* Will Ark support Kubernetes volume snapshots?
  - We need to do an evaluation on it, but it is also still alpha. Hoping to test once v0.10 is released.
* Is the Ark Helm chart maintained by the Ark team?
   - Not currently; it was contributed by the community. We will help as we are able.
   - We're happy to help others contribute to it.
 * Can my users manage Ark for their own namespaces?
   - This isn't well tested; we need to investigate RBAC/ACL integration in a secure manner.
   - See https://github.com/heptio/ark/issues/350 and https://github.com/heptio/ark/issues/18
   
  ## Shoutouts
