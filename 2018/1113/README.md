# Ark Q&A Session, Nov 13, 2018

Notes for the Nov 13, 2018 [YouTube video/live stream](https://www.youtube.com/watch?v=nVoEJv_ZIiM)

Add your request, question or suggestion to [our issue list](https://github.com/heptio/velero-community/issues)

# Attendees

 - Jorge Castro, Steve Kriss, Nolan Brubaker, Carlisia Pinto, Marissa Bosche, Ross Kukulinksi, Jennifer Rondeau. Jorge Alarcon from University of Texas @ Austin, 

# Agenda

## Introductions

## Announcements

* VMware acquired Heptio! Heptio’s teams and technologies will be integrated into VMware after close -- estimated to complete sometime in early December. VMware has already publicly committed to continue to invest in all of Heptio’s open source projects, including Ark.
* v0.10.0-beta.1 is out. Plans are to release v0.10.0 towards the end of the week.
    * skriss has started a [v0.10.0 punchlist](https://github.com/heptio/ark/issues/1052) for release.
    * Resumable plugins available
    * Multiple snapshot storage provider support
    * Multiple backup locations
* v0.9.11 is out with some critical bug fixes. This is the current stable release. Please upgrade!
    * Once v0.10.0 is out, our semi-weekly bug fix updates will be for v0.10.x, and the v0.9 releases will stop.
* No Q&A next month due to KubeCon.
    * Find Ross, Andy, Carlisia, Jennifer, and Jorge there
* The Heptio Ark team is revisiting plans for v1.0. 
    * Community has been asking why it's not 1.0, people want stability when upgrading up through Ark versions and Kubernetes versions. Therefore we feel it's best to concentrate on getting a 1.0 out sooner rather than later.
    * We've taken a first pass of priority issues, and will send a summary for comment to the Google Group.
        * At this point we'd love feedback on these issues so that we're working on things that are important to you.
    * API stability until 2.0
    * We'll have an open session on 27 November to discuss 1.0 plans, you are encouraged to attend if you have any feedback for us
    * Priority for 1.0 will be focused on stability, correctness, and forward compatability.
    * We still want to work on encryption-at-rest and replication and we will get to it post-1.0, we just want to make sure that we have a solid base before we start to build in more features.
    * Of course if you're interested in helping us accelerate these plans and want to work on features, we'd be happy to mentor and facilitate this. 

## Shoutouts

* Brian Leppez & Jordan Taylor (@captjt) for finding and fixing a bug in the schedule creation command ([#941](https://github.com/heptio/ark/issues/941))
* Lukasz Jakimczuk (@ljakimczuk) for fixing ownership of AWS volumes ([#801](https://github.com/heptio/ark/pull/801))
* James Powis for fixing service account token restores ([#910](#https://github.com/heptio/ark/pull/910))
* Shubheksha for restoring storage classes before PVs/PVCs ([#594](https://github.com/heptio/ark/issues/594)) (and probably more PRs that we missed!)
* AWS: Ensure that the order returned by ListObjects is consistent (bashofmann)
* Add CRDs to list of prioritized resources (domenicrosati)
* Update README.md - Grammar mistake corrected (midhunbiju)

## Live Questions

* Michal: "hi, I won't be able to join online but for sure I'll watch the video. What features are planned for the v0.11? (I guess you'll be talking about it even without my question :wink: )"

## Last Month's Questions

Some topics that have come up in the last month or so on Slack and the mailing list.

* My Restic restores are failing after about an hour, what's happening?
  - Restic restores are currently slow with large data sets. They have a [PR](https://github.com/restic/restic/pull/1719) merged to `master` that should help with this, but it's not yet been released.
  - For Heptio Ark v0.9.x, you can extend the timeout by editing the `podVolumeOperationTimeout` value on the `Config` object. In Heptio Ark v0.10.x, use the `--restic-timeout` server flag.  See [this issue](https://github.com/heptio/ark/issues/916) for more information.
* What's needed for Prometheus to scrape my Ark deployment for metrics?
  - There are 3 annotations that need to be on the Deployment template, and the port needs to be exposed on the container spec.
      - prometheus.io/scrape
      - prometheus.io/port
      - prometheus.io/path
  - See https://github.com/heptio/ark/blob/master/examples/aws/10-deployment-kube2iam.yaml (or any other deployment YAML file) for a full example. 
* The Ark server can't start up; it says there's a missing `Config`.
    -  Changed default branch to release-0.9. As of v0.10.0, the release tarballs will contain the example YAML for the relevant release.
 
## Schedule for the rest of 2018

* Next design discussion will be November 27. Discussion around v1.0 priorities. [YouTube live stream](https://www.youtube.com/watch?v=Ml5lN4cV1Yk)
* No streams in December. KubeCon's on December 11 and December 25 is Christmas. See you in January.
