[![](https://www.drupal.org/files/styles/grid-3/public/project-images/Medium-Logo%20Color%20with%20padding.png)](https://www.drupal.org/project/varbase)

[![Build Status](https://travis-ci.org/Vardot/varbase.svg?branch=8.x-4.08)](https://travis-ci.org/Vardot/varbase/builds/273184767) Varbase 8.4.08

# Varbase Project

Project template for [Varbase distribution](http://www.drupal.org/project/varbase).


## Create a Varbase project with [Composer](https://getcomposer.org/download/):

To install the most recent stable release of Varbase 8.4.x run this command:
```
composer create-project Vardot/varbase-project:^8.4.08 PROJECT_DIR_NAME --no-dev --no-interaction
```

To install the dev version of Varbase 8.4.x run this command:
```
composer create-project vardot/varbase-project:8.4.x-dev PROJECT_DIR_NAME --stability dev --no-interaction
```


## [Create new Vartheme sub theme for a project](https://github.com/Vardot/varbase/tree/8.x-4.x/scripts/README.md)

## [Automated Functional Testing](https://github.com/Vardot/varbase/blob/8.x-4.x/tests/README.md)

## [Varbase Gherkin features](https://github.com/Vardot/varbase/blob/8.x-4.x/tests/features/varbase/README.md)

## [Varbase 8.4.x Developer Guide](https://docs.varbase.vardot.com)




# Notices

### Requiring Drupal Modules with Dev Version in varbase-project/composer.json
You will notice that we're requiring some Drupal modules in dev state with its commit hash. This is because of a bug in Composer. And it was discussed in https://github.com/composer/composer/issues/6366 and is highlighted in Composer documentation as follows:

> Note: This feature has severe technical limitations, as the composer.json metadata will still be read from the branch name you specify before the hash. You should therefore only use this as a temporary solution during development to remediate transient issues, until you can switch to tagged releases. The Composer team does not actively support this feature and will not accept bug reports related to it.

Therefore, our workaround, is to explicitly tag the commit hash we want in `varbase-project/composer.json`. This means that ALL Drupal modules dependencies which are in dev stage, are duplicated as a requirement for composer in both `varbase-project/composer.json` and `varbase/composer.json`.

This workaround will remain, until either a module has a tag (that we can tag without the commit hash) or a fix is provided from composer - hopefully in the near future!

Read more at: https://www.drupal.org/node/2903606#comment-12230769
=======
# Pantheon Empty Upstream

This is an empty repository that is, save for this explanatory text, devoid of all content. This upstream is appropriate to use in situations where a Pantheon site will be created through a build step (see the [Terminus Build Tools Plugin](https://github.com/pantheon-systems/terminus-build-tools-plugin) and managed completely by Composer. Typically, the build step should completely replace the content provided by the upstream. If this README persists after the build step, it will do no harm; however, it would be advisable to replace this text with a description of the project.

If this upstream is used to install a site that does not have a build step, then you will not be able to install or use your site. In that event, the best thing to do would be to delete it and start over, either by selecting a different upstream, or by using the [Terminus Build Tools Plugin](https://github.com/pantheon-systems/terminus-build-tools-plugin) `terminus build-env:create-project` command to set up a build server.
