# Travis Workflow Sugar

The following repository contains bash scripts that you can use to replicate
certain [delivery-sugar](https://github.com/chef-cookbooks/delivery-sugar) helpers
in your Travis CI tests.

## Installation

The following command will install all the Travis Workflow Sugar binaries into `/usr/local/bin`.

```yaml
before_install:
  - curl -L https://raw.githubusercontent.com/chef/travis-sugar/master/install.sh | bash
```

## Usage

### run_if_changed

Only run a command if files in the specified `WORKDIR` changed since the last merged commit
(`<DIRECTORY>` should be the path relative to `$TRAVIS_BUILD_DIR`). If files _did_
change, then the specified `<COMMAND>` will be executed within the context of the
`WORKDIR`. If no files were modified, then `run_if_changed` will `exit 0`.

```yaml
script: WORKDIR=<DIRECTORY> run_if_changed <COMMAND>
```
