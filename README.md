This project does not build currently. It is in progress.

# Shipkit bootstrap

Below is work in progress

## Shipkit workflow test drive in 4 simple steps

1. **Fork & clone**: fork this repo and clone it to your computer
2. **Dummy change**:  check out new branch, make some dummy change, commit and push to remote repo.
You can just copy paste below to your terminal:

```
git checkout -b shipkit-testing
echo "Shipkit testing" >> README.md
git commit README.md -m "Shipkit testing"
git push --set-upstream origin shipkit-testing
```

3. **Pull request**: in GitHub, open PR with the dummy change pushed in the previous step.
**Important**: set the "base fork" to your own fork because GitHub by default suggests upstream repo.
Upstream repo is no good because you don't have permissions and you cannot merge immediately.
When the PR is created, hit the green button to merge it!

4. **Ship it**: perform release from master branch: pull the dummy change and then ship it.

```
git checkout master
git pull
./gradlew performRelease
```

Congratulations, you shipped with Shipkit.
See the build output to inspect what happened.
You should see something like that:

TODO: screen shot from terminal

----

Below is less than work in progress

## Let's ship binaries!

1. Fork and clone this repository to your computer
2. Run "./gradlew bintrayUpload -Pshipkit.dryRun=false"
   TODO: remove '-Pshipkit.dryRun=false' when https://github.com/mockito/shipkit/issues/236 is implemented
3. See the binaries published to https://dl.bintray.com/shipkit/shipkit-bootstrap

## Let's get release notes!

1. Generate GitHub personal access tokens
2. Export "GH_WRITE_TOKEN" env variable
3. Run "./gradlew performRelease"
4. Go to your repository on GitHub, see "docs/release-notes.md"

## Let's ship binaries on every change!

1. Sign up for Travis CI
2. Configure "GH_WRITE_TOKEN" env variable in Travis Web UI
3. Create and merge pull request
4. See the release notes in GitHub

## Let's ship binaries to your own repo!

1. Sign up for Bintray account and create new Maven repository
2. Generate Bintray Api key and export the value as "BINTRAY_API_KEY" env variable
3. Run: "./gradlew bootstrapBintray -Puser=<bintray user name> -Prepo=<bintray repo>
4. Run: "./gradlew performRelease"

## Let's automatically ship to your own repo!

1. Push local changes to "releasing.gradle" file
2. Configure "BINTRAY_API_KEY" env variable in Travis Web UI
3. Create and merge pull request
4. See the release notes in GitHub

# True North Vision

Shipkit wants to make a dent in the how software is released.

Imagine the world where you call pull in a new version of some Open Source library and not worry if it breaks compatibility.
Imagine that you can submit a pull request to some project, have it reviewed timely, and have the new version with your fix available to you in minutes after your PR is merged.
Imagine that for any dependency you consider upgrading, you can view its neatly and consistently maintained release notes.
Imagine that you can set up practical Continuous Delivery automation in your project in minutes, by using a well behaving and documented Gradle plugin.
Imagine that you can focus on code and features while the release management, versioning, publishing, release notes generation is taken care for you automagically.

This is the goal of [Shipkit](https://github.com/mockito/shipkit) project. The project started in November 2016 and is currently in progress.Shipkit testing
