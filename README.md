## Sagan: the spring.io site and reference application

#### Latest production deployment [![Build Status](https://travis-ci.org/spring-io/sagan.svg?branch=master)](https://travis-ci.org/spring-io/sagan)

Welcome! The code in the master branch of this repository is deployed and running right now at [spring.io](http://spring.io). The [blog][], the collection of [guides][], and everything else you see there is implemented right here.

In addition to the practical purpose of powering Spring's home on the web, this project is designed to serve as a *reference application*--a resource that developers can use to see how the [Spring team][] have used Spring to implement a real-world app with a few interesting requirements. We hope you'll find it useful!

## Getting started

You'll find everything you need to get started in the [project wiki][], but you can also begin by simply browsing through the repository and finding what's of interest to you. You'll find README files in key directories, and Javadoc throughout the code. The app and all of its documentation are designed with the idea of a 'self-guided tour' in mind.

## Package Structure

Generally, the unqualified 'feature' packages, e.g. 'sagan.blog', or 'sagan.guides' contain types representing domain concepts, e.g. Post, Guide, and so forth.

The 'support' packages, on the other hand, are generally "supporting infrastructure", i.e. the services, repositories, controllers, required to make the feature in question actually work. Types here are generally package-private, reflecting the fact the supporting infrastructure for any given feature shouldn't be needed by any other feature (one exception here being the relationship between 'sagan.team.support' and 'sagan.blog.support', wherein the former's TeamController needs to talk to the latter's BlogService (we may refactor that away in the future).

It could have been reasonable to collapse everything for a given feature into a single package, and to do away with the 'support' notion altogether, but we wanted to help draw a distinction between domain concepts and supporting infrastructure. One place this reads nicely is in the sagan-site module, where you can see that there are no types in the unqualified 'domain' packages—only entries in the '.support' packages. This communicates pretty clearly that sagan-site doesn't introduce any new domain concepts, but rather adds controllers, views, and other 'site'-level components.

## Q&A and issue tracking

If you have any questions, feedback, or feature requests, don't hesitate to [add an issue][].

## Contributing

[Pull requests](http://help.github.com/send-pull-requests) are welcome; see the [contributor guidelines](CONTRIBUTING.md) for details.

## License

Sagan is released under the [BSD-3 license](LICENSE.md).


[blog]: http://spring.io/blog
[guides]: http://spring.io/guides
[Spring team]: http://spring.io/team
[project wiki]: https://github.com/spring-io/sagan/wiki
[add an issue]: https://github.com/spring-io/sagan/issues
