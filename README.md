# Unit Test Examples

## Purpose

This repo serves to demonstrate writing unit test for a PHP library using PHP Unit.
These tests are in no way perfect, but I tried to get good coverage while still
providing meaningful test. After all you can have 100% coverage and still not really
test the full functionality of your application.

The project is composed of two *"service"* classes that make up the functionality
of this mock library. One is the `LastModified` service and the other is the `StatusService`.

The `LastModified` service provides a way to register `LastModifiedTimeProvider` classes
that can return an `int` time value that represents the time that whatever the provider is
representing (i.e. Users, files, Products, etc) was last modified. The service can take
1 to many providers, and return the most recent modified time. If you could imagine, this
could be used as part of a blog website were the providers could be one to iterate over
the webserver files to get the last modified time, and another provider to check for the
most recent blog post in the database. The service also facilitates getting the last modified
time for a single provider or an array of registered providers.

The `StatusService` functions in a similar way with `StatusServiceProviders` that can
return an array containing the "status" of whatever the provider is representing (i.e.
web service, database, cache service, etc). The service facilitates getting the status of
a single provider, many, or all providers much like the `LastModified` service. As you
could imagine, this could be useful in many ways. If you had a website that hit a database,
you could use this service to provide an API to get the status of the database.

With both services, I provided a couple simple providers to provide an example on how
to implement the providers. Also as stated above, the test serve to show how to write
PHP Unit tests and have examples of mocking the filesystem, and through clean architecture
you can have classes that need external service such as databases and cache services and
be able to write unit tests without breaking outside the boundary of the application
using mock objects.


## Standards

This project adheres to PSR standards where applicable. Also I tried to design this example
project using a clean architecture that promotes SOLID principles and seeks to help
others in writing cleaner code. I am no expert by any means, but I feel although the
example services may be a bit contrived, the implementation of them follow at least good
practices for the most part.

## Contributing

Got something you wanna add? Find a bug or otherwise bad code? Feel free to submit pull
requests to add in new features, fix bugs, or clean things up. Just be sure to follow the
[Code of Conduct](https://github.com/brandon14/unit-test-examples/blob/master/.github/CODE_OF_CONDUCT.md)
and [Contributing Guide](https://github.com/brandon14/brandonclothier.me/blob/master/.github/CONTRIBUTING.md),
and I encourage creating clean and well described pull request if possible.
