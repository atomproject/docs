# Component & Application Development Workflow

This document lays out general guidelines regarding the development of polymer
components and applications based on it in the atom ecosystem.

The objective is to allow for parallel development of applications and the components used by it.

The package manager used is `bower` since all the development in polymer and atom ecosystem is centered around it.
Tags in a git repo are used by bower to represent versions, hence the two terms will be used interchangeably throughout this document.
The versions must follow the semver [spec](http://semver.org/),
the spec is very informative please ensure that you have read it before continuing with this document.

## General Git Workflow

Development of either component or application should adhere to following guidelines.

The guidelines presented here are a simplified version of [gitflow](http://nvie.com/posts/a-successful-git-branching-model/).

1. Master must always contain stable code.
2. As a result of above requirement __every__ commit on master must be tagged.
3. Any merges being made into master must be __explicit merges__ even if they are fast forward changes.
4. A branch named develop should be used to make merges, it contain the latest code which will be released.
5. There are other branches like _release-*_ or _hotfix-*_ which are used to make releases and bugfixes for that release.

It must be noted that in some cases following such an elaborate workflow may not
be effecient, in those cases following rules must be adhered to while making changes.

1. Master must always contain stable code.
2. As a result of above requirement __every__ commit on master must be tagged.
3. Any merges being made into master must be __explicit merges__ even if they are fast forward changes.

## Component Dependency Specification

As of now all the components can be categorized into two sets from the perspective of
depenedency management.

1. General components
2. Specific components

### General Components

A lot of elements in the organization `atomelements` should fall under this category.

Their characteristics can be listed as following.

1. Independent development and testing.
2. Don't contain any domain specific logic

Any application using these components is should make use of [tilde ranges][2] or
[caret ranges][1] to specify the dependencies. This method of specification ensures
that you can easily update your dependencies.

### Specific Components

Almost all the components in the organization `travelnxtelements` fall under this category.

Their characteristics can be listed as following.

1. Partly interdependent development and testing.
2. Contain domain specific logic.

As a result of above characteristics application development may entail changes
in these components, also these changes may be best tested along with other components
in the application itself.

There is also scope for inter-component tight coupling, which means
changes in one component may require changes to be made in another component.

Following rules should be applied while specifying the dependencies in either an application or a component.


1. By default only mention [tilde][2] or [caret][1] ranges.
2. If a non-stable component needs to be tested or consumed while development specify branches instead of ranges.
3. Once testing is complete update the versions of consumed components and revert back to using [tilde][2] or [caret][1] ranges.

[1]: https://docs.npmjs.com/misc/semver#caret-ranges-1-2-3-0-2-5-0-0-4
[2]: https://docs.npmjs.com/misc/semver#tilde-ranges-1-2-3-1-2-1


## Miscellaneous Tools and Links

1. Enforce the gitflow workflow with a [tool](https://github.com/nvie/gitflow)
2. A [tool](https://www.npmjs.com/package/gitwalk) for managing multiple git repositories
3. A [video](https://docs.npmjs.com/getting-started/semantic-versioning) explaining semver.
