cfn-ci
------
CF template for an EC2 that reports back to GitHub statuses API.

1. Create a CF stack with GitHub info + contents of a bash (UserData) script to run,
2. An EC2 is created that runs the script and reports back success/failure to GitHub,
3. If you need to debug a log of the script run is posted as an anonymous secret gist.

Parameters | Description
---------- | -----------
OS         | OS to test on (currently: centos7 or ubuntu1404)
Label      | Label for CI job when posted back to GitHub
UserData   | Test script to run
GitSha     | Git commit sha to post status to
GithubRepo | GitHub repo to post status to
GithubAccessToken | GitHub access token with repo:status scope

### cfn-win.template

An in-progress Windows build/testing template.

Parameters | Description
---------- | -----------
OS         | AMI to test on (currently: `win2012`, `win2012-vs2014`, or `win2012-vs2015`)
UserData   | Test script to run
GithubAccessToken | *Unused*: GitHub access token with repo:status scope

To add a new AMI see the steps at https://github.com/mapbox/cfn-ci/pull/4#issue-98029857

### ami/cfn-ami-win2012-vs2014.template

A CFN template for building a Windows 2012 + Visual Studio 2014 AMI. AMI creation must
be done manually after the template has run and VS2014 is successfully installed.

### ami/cfn-ami-win2012-vs2015.template

A CFN template for building a Windows 2012 + Visual Studio 2015 AMI. AMI creation must
be done manually after the template has run and VS2015 is successfully installed.
