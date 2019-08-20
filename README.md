
# GoReleaser sample project

## Check configuration

```
goreleaser --snapshot --skip-publish --rm-dist
# OR
goreleaser check
```

---

## Release

You’ll need to export either a GITHUB_TOKEN or GITLAB_TOKEN environment variable, which should contain a valid GitHub token with the repo scope or GitLab token with api scope.
It will be used to deploy releases to your GitHub/GitLab repository. You can create a token here for GitHub or here for GitLab.

```
export GITHUB_TOKEN=`YOUR_GH_TOKEN`
# OR
export GITLAB_TOKEN=`YOUR_GL_TOKEN`
```

GoReleaser will use the latest Git tag of your repository. Create a tag and push it to GitHub:

```
git tag -a v0.1.0 -m "First release"
git push origin v0.1.0
```

Now you can run GoReleaser at the root of your repository:

```
goreleaser
```

That’s all! Check your GitHub/GitLab project’s release page.

---

## Snapshot

`Note: ony GitHub supports snapshots`

If you don’t want to create a tag yet, you can also create a release based on the latest commit by using the `--snapshot` flag.

---

## Dry run

If you want to test everything before doing a release “for real”, you can use the `--skip-publish` flag, which will only build and package things:

```
goreleaser release --skip-publish
```

---

## Semantic Versioning

GoReleaser enforces semantic versioning and will error on non compliant tags.

Your tag should be a valid semantic version. If it is not, GoReleaser will error.

### Summary

Given a version number **MAJOR.MINOR.PATCH**, increment the:
* **MAJOR** version when you make incompatible API changes,
* **MINOR** version when you add functionality in a backwards compatible manner, and
* **PATCH** version when you make backwards compatible bug fixes.

Additional labels for pre-release and build metadata are available as extensions to the **MAJOR.MINOR.PATCH** format.

---

## Links

* https://goreleaser.com/quick-start/
* https://goreleaser.com/templates/
* https://semver.org/
