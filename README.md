Repo for testing workflows using prerelease and release options

From github documentation > https://help.github.com/pt/actions/reference/workflow-syntax-for-github-actions

`on.<event_name>.types`

Selects the types of activity that will trigger a workflow run. Most GitHub events are triggered by more than one type of activity. For example, the event for the release resource is triggered when a release is published, unpublished, created, edited, deleted, or prereleased. The types keyword enables you to narrow down activity that causes the workflow to run. When only one activity type triggers a webhook event, the types keyword is unnecessary.

## Github Support Orientation

Every time you modify something in the web interface, more than one event are triggered. You can configure your repository to send webhooks for every release event and see which events are triggered in every particular case. For the explanation below when I refer to an event as release:prereleased it means the release event with activity type prereleased

Looking at your use cases it seems that you need to focus on the release:prereleased event and the release:released event.

Let me go into more detail:

When you go to the web interface, create a new release, don’t check the this is a prerelease button and then click on Publish release, the following webhook events are triggered:

release:released
release:published
release:created
create
push
If then for that same release you go to Edit release, check This is a prerelease and click Update release, the following webhook events are triggered:

release:prereleased
When you go to the web interface, create a new release, check the this is a prerelease button and then click on Publish release, the following webhook events are triggered:
```
release:prereleased
release:published
release:created
create
push
```
If then for that same release you go to Edit release, uncheck This is a prerelease and click Update release, the following webhook events are triggered:
```
release:released
````
Having this in mind and looking at the use cases you mentioned, could you please modify release.yml to listen for the release event with type released, like this:

```
on:
  release:
    types: [released]
```
