# Workflow Tests

Repo for testing workflows when using releases

From github documentation > https://help.github.com/pt/actions/reference/workflow-syntax-for-github-actions

`on.<event_name>.types`

Selects the types of activity that will trigger a workflow run. Most GitHub events are triggered by more than one type of activity. For example, the event for the release resource is triggered when a release is **published**, **unpublished**, **created**, **edited**, **deleted**, **released** or **prereleased**. The types keyword enables you to narrow down activity that causes the workflow to run. When only one activity type triggers a webhook event, the types keyword is unnecessary.

## How to use to emulate CD to different environments

### Using Trunk Based Development (TBD)

- Each check-in on the master branch will deploy to development environment
- Create a release checking the checkbox **This is a pre-release** will deploy to qa/homologation environment
- Edit that release uncheck **This is a pre-release** and publish will deploy to production environment

### Using Git Flow

Here it could exists some variations, but you don`t need to use the Release because the trigger of the workflow will be the merge/pull request to the branch

- Branch Develop will be deploy to development environment
- Merge to Release, or create a  will deploy to qa/homologation environment
- Merge to Master will deploy to production

## Downsides

- If you need approval between environments using TBD the best approach is to use release branch with a Pull Request approval
- If you are using releases to deploy you need to be sure which commit should be on that package before creating a release