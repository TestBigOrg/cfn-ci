cfn-ci
------
CF template for an EC2 that reports back to GitHub statuses API.

1. Create a CF stack with GitHub info + contents of a bash (UserData) script to run,
2. An EC2 is created that runs the script and reports back success/failure to GitHub,
3. If you need to debug a log of the script run is posted as an anonymous secret gist.

### Parameters

Param      | Description
---------- | -----------
OS         | OS to test on (currently: centos7 or ubuntu1404)
Label      | Label for CI job when posted back to GitHub
UserData   | Test script to run
GitSha     | Git commit sha to post status to
GithubRepo | GitHub repo to post status to
GithubAccessToken | GitHub access token with repo:status scope

