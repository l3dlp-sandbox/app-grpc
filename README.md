# Spiral GRPC Application Skeleton [![Latest Stable Version](https://poser.pugx.org/spiral/app/version)](https://packagist.org/packages/spiral/app)

<img src="https://raw.githubusercontent.com/spiral/guide/master/resources/logo.png" height="120px" alt="Spiral Framework" align="left"/>

Spiral is an open-source (MIT) micro-framework core that uses a set of open-source components and [an application server](https://github.com/spiral/roadrunner) which is designed to rapidly develop (RAD) high-performance PHP-applications that come with native support for HTTP/2, [GRPC](https://grpc.io/), distributed computations ([Queue](https://github.com/spiral/jobs)) and Golang extensions. 

[Website](https://spiral-framework.com) | <b>[App Skeleton](https://github.com/spiral/app)</b> ([cli](https://github.com/spiral/app-cli), [grpc](https://github.com/spiral/app-grpc)) | [Documentation (v1.0.0)](https://github.com/spiral/guide) | [Twitter](https://twitter.com/spiralphp) | [CHANGELOG](/CHANGELOG.md) | [Contributing](https://github.com/spiral/guide/blob/master/contributing.md)

<br/>

Server Requirements
--------
Make sure that your server is configured with following PHP version and extensions:
* PHP 7.1+
* MbString Extension
* PDO Extension with desired database drivers

> [Install](https://github.com/protocolbuffers/protobuf/tree/master/php) `protobuf-ext` to gain higher performance. 

Application Bundle
--------
Application bundle includes following components:
* High-Performance HTTP, HTTP/2 server based on [RoadRunner](https://roadrunner.dev)
* GRPC Server
* Console commands via symfony/console
* Queue support for AMQP, Beanstalk, Amazon SQS, in-Memory
* queue support for AMQP, Beanstalk, Amazon SQS
* DBAL and migrations support
* [Cycle DataMapper ORM](https://github.com/cycle)

Installation
--------
```
composer create-project spiral/app-grpc
```

> Application server will be downloaded automatically.

Once application is installed you can ensure that it was configured properly by executing:

```
$ php ./app.php configure
```

To start application server execute:

```
$ ./spiral serve -v -d
```

On Windows:

```$xslt
$ spiral.exe serve -v -d
```

TODO: write how to start grpc and test it

> Read more about application server configuration [here](https://roadrunner.dev/docs).

Generating services
--------
To update or generate service code for your application run:

```
$ php ./app.php grpc:generate proto/service.proto
```

Generated code will be available in `app/src/Service`. Implement generated service interface
and application will register it automatically.

License:
--------
MIT License (MIT). Please see [`LICENSE`](./LICENSE) for more information. Maintained by [Spiral Scout](https://spiralscout.com).
