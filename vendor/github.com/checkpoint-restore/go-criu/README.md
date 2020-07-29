[![master](https://travis-ci.org/checkpoint-restore/go-criu.svg?branch=master)](https://travis-ci.org/checkpoint-restore/go-criu)

## go-criu -- Go bindings for [CRIU](https://criu.org/)

This repository provides Go bindings for CRIU. The code is based on the Go based PHaul
implementation from the CRIU repository. For easier inclusion into other Go projects the
CRIU Go bindings have been moved to this repository.

The Go bindings provide an easy way to use the CRIU RPC calls from Go without the need
to set up all the infrastructure to make the actual RPC connection to CRIU.

The following example would print the version of CRIU:
```
	c := criu.MakeCriu()
	version, err := c.GetCriuVersion()
	fmt.Println(version)
```
or to just check if at least a certain CRIU version is installed:
```
	c := criu.MakeCriu()
	result, err := c.IsCriuAtLeast(31100)
```

## Releases

go-criu will carry the same version number as CRIU. This implies that each
go-criu release will pull in the necessary changes from CRIU before making a
release.

The first go-criu release was 3.11 based on CRIU 3.11.

## How to contribute

While bug fixes can first be identified via an "issue", that is not required.
It's ok to just open up a PR with the fix, but make sure you include the same
information you would have included in an issue - like how to reproduce it.

PRs for new features should include some background on what use cases the
new code is trying to address. When possible and when it makes sense, try to
break-up larger PRs into smaller ones - it's easier to review smaller
code changes. But only if those smaller ones make sense as stand-alone PRs.

Regardless of the type of PR, all PRs should include:
* well documented code changes
* additional testcases. Ideally, they should fail w/o your code change applied
* documentation changes

Squash your commits into logical pieces of work that might want to be reviewed
separate from the rest of the PRs. Ideally, each commit should implement a
single idea, and the PR branch should pass the tests at every commit. GitHub
makes it easy to review the cumulative effect of many commits; so, when in
doubt, use smaller commits.

PRs that fix issues should include a reference like `Closes #XXXX` in the
commit message so that github will automatically close the referenced issue
when the PR is merged.

Contributors must assert that they are in compliance with the [Developer
Certificate of Origin 1.1](http://developercertificate.org/). This is achieved
by adding a "Signed-off-by" line containing the contributor's name and e-mail
to every commit message. Your signature certifies that you wrote the patch or
otherwise have the right to pass it on as an open-source patch.

### License

The license of go-criu is the Apache 2.0 license.