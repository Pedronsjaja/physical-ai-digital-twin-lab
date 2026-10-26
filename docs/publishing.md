# Publish the prepared repository

The initial delivery is a local Git repository. The connected GitHub tool could edit existing repositories but did not expose repository creation; the target was not found. No Issues or labels have been created remotely.

1. Create an empty public repository named physical-ai-digital-twin-lab under Pedronsjaja, without generated README/license/gitignore.
2. From this repository root, inspect git log and git status.
3. Add the remote and publish:

```sh
git remote add origin https://github.com/Pedronsjaja/physical-ai-digital-twin-lab.git
git push -u origin main
```

If origin already exists, inspect it before changing anything. Do not overwrite an existing remote repository.
Use the description from README. The MIT license applies only to newly authored lab content.
Create the eight Issues from [their drafts](initial-issues.md), after checking for duplicates. Suggested labels: digital-twin, ros2, simulation, hardware, research, documentation; good first issue only after scope review.
Once publication succeeds, update the profile's lab status and add its link. Publication is not implementation.
