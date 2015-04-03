# Contributing to Selenium

The Selenium project welcomes contributions from everyone. There are a
number of ways you can help:

## Table of Contents
- [Contributing to Selenium](#contributing-to-selenium)
  - [Issue Contributions](#issue-contributions)
  - [Documentation Contributions](#documentation-contributions)
  - [Code Contributions](#code-contributions)
    - [Step 1: Fork](#step-1-fork)
      - [Dependencies](#dependencies)
      - [License Headers](#license-headers)
    - [Step 2: Branch](#step-2-branch)
    - [Step 3: Commit](#step-3-commit)
    - [Step 4: Rebase](#step-4-rebase)
    - [Step 5: Test](#step-5-test)
    - [Step 6: Sign the CLA](#step-6-sign-the-cla)
    - [Step 7: Push](#step-7-push)
    - [Step 8: Integration](#step-8-integration)
  - [Stages of an Issue or PR](#stages-of-an-issue-or-pr)
  - [Communication](#communication)

## Issue Contributions

When opening new issues or commenting on existing issues on this
repository please make sure discussions are related to concrete
technical issues with the Selenium software.

It's imperative that issue reports outline the steps to reproduce
the defect. If the issue can't be reproduced it will be closed.
Please provide [concise reproducible test cases](http://sscce.org/)
and describe what results you are seeing and what results you expect.

Issues shouldn't be used for support. Please address questions to the
[`selenium-users@` mailing list](https://groups.google.com/forum/#!forum/selenium-users).
Discussion of high level project ideas or non-technical topics should
move to the
[`selenium-developers@` mailing list](https://groups.google.com/forum/#!forum/selenium-developers)
instead.

## Documentation Contributions

Selenium is a big software project and documentation is key to
understanding how things work and learning effective ways to exploit
its potential.

The official documentation of Selenium is still served from our
[**www.seleniumhq.org** repository](https://github.com/SeleniumHQ/www.seleniumhq.org).
We are however phasing out this documentation which focuses too much
on Selenium RC and other antiquated pieces, in favour of a rewrite.

The new documentation is a project started to rewrite Selenium's
documentation from scratch. This is an ongoing effort (not targetted
at any specific release) to provide an updated handbook on how to use
Selenium effectively. We hope to bring over the pieces of the old
documentation that makes sense.

Contributions toward the new docs follow the same process described in
the next section about code contributions. You should spend some time
familiarising yourself with the documentation by reading
[more about it](https://seleniumhq.github.io/docs/intro.html#about_this_documentation).

## Code Contributions

The Selenium project welcomes new contributors. Individuals making
significant and valuable contributions over time are made _Committers_
and given commit-access to the project.

If you're looking for easy bugs, have a look at
[issues labelled E-easy](https://github.com/SeleniumHQ/selenium/issues?q=is%3Aopen+is%3Aissue+label%3AE-easy)
on Github.

This document will guide you through the contribution process.

### Step 1: Fork

Fork the project [on Github](https://github.com/seleniumhq/selenium)
and check out your copy locally.

```text
% git clone git@github.com:username/selenium.git
% cd selenium
% git remote add upstream git://github.com/seleniumhq/selenium.git
```

#### Dependencies

We bundle dependencies in the _third-party/_ directory that is not
part of the project proper. Any changes to files in this directory or
its subdirectories should be sent upstream to the respective projects.
Please don't send your patch to us as we cannot accept it.

We do accept help in upgrading our existing dependencies or removing
superfluous dependencies. If you need to add a new dependency it's
often a good idea to reach out to the committers on the IRC channel or
the mailing list to check that your approach aligns with the project's
ideas. Nothing is more frustrating that seeing your hard work go to
waste because your vision doesn't align with the project's.

#### License Headers

Every file in the Selenium project must carry the following license
header boilerplate:

```text
Licensed to the Software Freedom Conservancy (SFC) under one
or more contributor license agreements.  See the NOTICE file
distributed with this work for additional information
regarding copyright ownership.  The SFC licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License.  You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied.  See the License for the
specific language governing permissions and limitations
under the License.
```

There's no need to include a copyright statement in the file's header.
The copyright attributions can be reviewed in the
[NOTICE](https://github.com/SeleniumHQ/selenium/blob/master/NOTICE)
file found in the top-level directory.

### Step 2: Branch

Create a feature branch and start hacking:

```text
% git checkout -b my-feature-branch
```

We practice HEAD-based development, which means all changes are aplied
directly on top of master.

### Step 3: Commit

FIrst make sure git knows your name and email address:

```text
% git config --global user.name 'Santa Claus'
% git config --global user.email 'santa@example.com'
```

**Writing good commit messages is important.** A commit message
should describe what changed, why, and reference issues fixed (if
any).  Follow these guidelines when writing one:

1. The first line should be around 50 characters or less and contain a
   short description of the change.
2. Keep the second line blank.
3. Wrap all other lines at 72 columns.
4. Include `Fixes #N`, where _N_ is the issue number the commit
   fixes, if any.

A good commit message can look like this:

```text
explain commit normatively in one line

Body of commit message is a few lines of text, explaining things
in more detail, possibly giving some background about the issue
being fixed, etc.

The body of the commit message can be several paragraphs, and
please do proper word-wrap and keep columns shorter than about
72 characters or so. That way `git log` will show things
nicely even when it is indented.

Fixes #141
```

The first line must be meaningful as it's what people see when they
run `git shortlog` or `git log --online`.

### Step 4: Rebase

Use `git rebase` (not `git merge`) to sync your work from time to time.

```text
% git fetch upstream
% git rebase upstream/master
```

### Step 5: Test

Bug fixes and features **should have tests**. Look at other tests to
see how they should be structured.

Before you submit your pull request make sure you pass all the tests:

```text
% ./go clean test
```

### Step 6: Sign the CLA

Before we can accept , we first ask people to sign a
[Contributor License Agreement](https://spreadsheets.google.com/spreadsheet/viewform?hl=en_US&formkey=dFFjXzBzM1VwekFlOWFWMjFFRjJMRFE6MQ#gid=0)
(or CLA). We ask this so that we know that contributors have the right
to donate the code.

When you open your pull request we ask that you indicate that you've
signed the CLA. This will reduce the time it takes for us to integrate
it.

### Step 7: Push

```text
% git push origin my-feature-branch
```

Go to https://github.com/yourusername/selenium.git and press the _Pull
Request_ and fill out the form. **Please indicate that you've signed
the CLA** (see step 6).

Pull requests are usually reviewed within a few days. If there are
comments to address, apply your changes in new commits (preferably
[fixups](http://git-scm.com/docs/git-commit)) and push to the same
branch.

### Step 8: Integration

When code review is complete, a committer will take your PR and
integrate it on Selenium's master branch. Because we like to keep a
linear history on th master branch, we will normally squash and rebase
your branch history.

## Stages of an Issue or PR

From your create your issue or pull request, through code review and
towards integration, it will be assigned different Github labels. The
labels serve for the committers to more easily keep track of work
that's pending or awaiting action.

Component labels are yellow and carry the **C** prefix. They highlight
the subsystem or component your PR makes changes in.

The driver labels (**D**) indicate if the changes are related to a
WebDriver implementation or the Selenium atoms.

The review labels (**R**) are:

* **awaiting answer**: awaits an answer from you
* **awaiting merge**: waits for a committer to integrate the PR
* **awaiting reviewer**: pending code review
* **blocked on external**: a change in an upstream repo is required
* **needs code changes**: waiting for you to fix a review issue
* **needs rebase**: the branch isn't in sync with master and needs to
   be rebased

Issues are labelled to make them easier to categorise and find by:

* which **component** they relate to (java, cpp, dotnet, py, rb)
* which **driver** is affected
* their presumed **difficulty** (easy, less easy, hard)
* what **type** of issue they are (defect, race condition, cleanup)

## Communication

Selenium contributors frequent the `#selenium` channel on
[`irc.freenode.org`](https://webchat.freenode.net/). You can also join
the [`selenium-developers@` mailing list](https://groups.google.com/forum/#!forum/selenium-developers).