# Using this study add-on template

(Remove this file after you have cloned/merged the template to your own study add-on repo.)

## Important notice

We just started [supporting a pure Web Extension Experiment workflow in this template](https://github.com/mozilla/shield-studies-addon-template/issues/53) with a new version, v5, of the [Shield utilities](https://github.com/mozilla/shield-studies-addon-utils/).
Even though support for these workflows are yet to pass official QA review, **we do not recommend using the old template (for creating legacy boostrapped add-ons using Shield Utils v4) of this template**. Creating a legacy boostrapped add-on with the outdated master branch will likely result in a broken Shield study add-on in recent versions of Firefox.

Instead, we recommend that you:

* build your study as a WEE ([Web Extension Experiment](https://firefox-source-docs.mozilla.org/toolkit/components/extensions/webextensions/index.html))
* help us test the requisite [new Shield Web Extension API(s)](https://github.com/mozilla/shield-studies-addon-utils/)

Example Shield add-ons using the experimental Shield API(s):

* This template
* <https://github.com/mozilla/shield-studies-addon-utils/tree/master/examples/small-study>
* <https://github.com/motin/taar-experiment-v3-shield-study>
* <https://github.com/motin/dataleak-pioneer-shield-study>
* <https://github.com/mozilla/shield-cloudstorage>

Chat with us: #shield on Slack about the latest progress and how to help us move faster away from legacy add-ons.

## Aims

The aim is to bring together tools and services we've used on other Shield Study add-ons into a template/example repository, so that new projects can come
along and get infrastructure together, and be up and running with code, test suites, coverage etc quickly.

Using this template will get you these things:

* [Shield Utils](https://github.com/mozilla/shield-studies-addon-utils/) integration and example usage
* Functional tests
* Unit tests
* Continuous integration testing against Release, Beta, Dev Edition and Nightly (via Circle CI)
* [Example web extension experiment implementing custom ui using privileged code](./src/privileged/introductionNotificationBar/)
* Linting
* Partial code coverage (specific files)

Bonus:

* Consistent package.json (fixpack) and package-lock.json
* Addon-linter
* Runs nsp during lint

## Documentation

It is intended that all parts of this repository have at least outline
documentation. If you find any parts that are missing, please file an issue or
create a PR.

## Using this template

1. Fork this repository, rename it to reflect your study. Make the repo end with `-shield-study`
2. Make this README reflect your study (including removing all of this `About This Repository` section whilst keeping `Seeing the add-on in action` and below)
3. Remove irrelevant example code
4. Build your study add-on and make the docs reflect your study
5. File issues/PRs against https://github.com/mozilla/shield-studies-addon-template/ when you come across things to improve in the template

### Retrofitting an existing study add-on to use the template

First, move all existing files in your study add-on repository into a new folder and commit those changes. Then:

    git clone https://github.com/mozilla/shield-studies-addon-template /tmp/shield-studies-addon-template
    git remote add shield-studies-addon-template /tmp/shield-studies-addon-template
    git fetch shield-studies-addon-template
    git merge --allow-unrelated-histories shield-studies-addon-template/master
    git remote remove shield-studies-addon-template

After this, move back the files into the template structure as necessary. For an example of this, see [this](https://github.com/mozilla/federated-learning-v2-study-addon/commit/7367aa8d3f6d29f675ff3f36a1136c6b09476ace).
