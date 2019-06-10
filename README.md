# pyenv-based-tap-development
Set of scripts to set up and maintain a development workflow for Singer.io taps using pyenv

It will install all needed dependencies in siloed virtualenvs, create a project 
wide pyenv version that includes all the virtualenvs, and have scripts that make it
easier to add a new tap and to run tests. The idea is that you should work from this directory
since it will enable every necessary virtualenv at once.

There will be a local pyenv virtualenv version in each repo, so when you are editing files or 
looking inside the repo, the right pyenv virtualenv will be active.

## Getting started
First, make sure you have [pyenv](https://github.com/pyenv/pyenv) installed.

Set up the invironment by:
```
git clone https://github.com/aiguofer/pyenv-based-tap-development.git
cd pyenv-based-tap-development
./setup
```
Then edit your `env_vars` and add your credentials. This file is in `.gitignore` so you won't accidentally check it in.

## Using

To add a new tap:
```
./add-tap git@github.com:singer-io/tap-stripe.git
```

To run the entire test suite:
```
./run-test stripe
```

To run a specific test:
```
./run-test stripe tap_tester_tap_stripe_event_updates_test
```
