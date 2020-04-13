Repo for testing workflows using prerelease and release options

From github documentation > https://help.github.com/pt/actions/reference/workflow-syntax-for-github-actions

`on.<event_name>.types`

Selects the types of activity that will trigger a workflow run. Most GitHub events are triggered by more than one type of activity. For example, the event for the release resource is triggered when a release is published, unpublished, created, edited, deleted, or prereleased. The types keyword enables you to narrow down activity that causes the workflow to run. When only one activity type triggers a webhook event, the types keyword is unnecessary.