# Tachikoma

[![Gem Version](https://badge.fury.io/rb/tachikoma.png)](http://badge.fury.io/rb/tachikoma)
[![Build Status](https://api.travis-ci.org/sanemat/tachikoma.png?branch=master)](https://travis-ci.org/sanemat/tachikoma)
[![Code Climate](https://codeclimate.com/github/sanemat/tachikoma.png)](https://codeclimate.com/github/sanemat/tachikoma)

Daily Pull Requester with bundle/carton update. [Actual pull request](https://github.com/mrtaddy/fenix-knight/pull/25)

![tachikoma](https://gist.github.com/sanemat/6605029/raw/ztachikoma-demo5.gif 'tachikoma')
![tachikoma](https://gist.github.com/sanemat/6605029/raw/ztachikoma-demo6.gif 'tachikoma')

## Usage as gem

see: https://github.com/sanemat/bot-motoko-tachikoma

```
$ mkdir -p my-tachikoma
$ cd my-tachikoma
$ bundle init
$ echo "gem 'tachikoma'" >> Gemfile
$ bundle
$ bundle exec tachikoma init
```
### Write repository information

1. Get GitHub OAuth2 token: See [Creating an OAuth token for command-line use](https://help.github.com/articles/creating-an-oauth-token-for-command-line-use)
2. Add YAML of repository you want to build by Tachikoma: Copy `data/bot-motoko-tachikoma.yaml` then edit `url` and `type`. to clone URL of your repository. Change `type` to `shared`, if you use shared repository model.
3. Run below command in your shell:

```
$ export BUILD_FOR=<your-repository-name-that-is-same-to-yaml-filename>
$ export TOKEN_YOUR_REPOSITORY_NAME_THAT_IS_SAME_TO_YAML_FILENAME=xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
$ bundle exec rake tachikoma:load tachikoma:fetch tachikoma:bundle tachikoma:pull_request
```

If you use carton, then you use `tachikoma:carton` instead of `tachikoma:bundle`.

### Build script example

- [cloudbees.com dev@cloud](https://gist.github.com/sanemat/5859031)

## Versioning

Tachikoma will be maintained under the Semantic Versioning guidelines as much as possible. Releases will be numbered with the following format:

`<major>.<minor>.<patch>`

And constructed with the following guidelines:

* Breaking backward compatibility bumps the major (and resets the minor and patch)
* New additions without breaking backward compatibility bumps the minor (and resets the patch)
* Bug fixes and misc changes bumps the patch

For more information on SemVer, please visit http://semver.org.

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
