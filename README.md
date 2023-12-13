# AsciiDoc to Confluence

This is an example showcase project that shows how to generate confluence pages from ASCIIDoc code. It is supposed to generate or update confluence pages in one or more specific confluence instances on every push to the git repository. 

It feels kind of weird to rewrite how it works to this README as everything is documented in the project itself. 

However, important files for your reference may be the following:

1. [pom.xml](pom.xml) describes the build process
2. [.mvn/ci-settings.xml](.mvn/ci-settings.xml) contains settings and credentials to enable the CI to publish to confluence 
3. [asciidoc/index.adoc](asciidoc/index.adoc) contains the actual documentation
4. [confluence/index.adoc](confluence/index.adoc) contains the confluence page structure as desired, for every file in the confluence directory a single confluence page is generated. Subpages must be placed in sub folders. See [confluence-publisher-plugin documentation](https://confluence-publisher.atlassian.net/wiki/spaces/CPD/overview) for details.

## Hints
- You might want to put a file `.envrc` into the project root directory and use `direnv` to load the `env.` prefixed variables that are stated in the `pom.xml`.
- We usually do not use `github actions` to implement CI/CD which is why this project does not contain any. You would have to add those yourself in case you want/have to use them. However, there is an example `.gitlab-ci.yml` to describe a Gitlab CI/CD job that publishes to `confluence` on every push if there are changes in relevant directories.
