# Dropwizard RabbitMQ Actors Bundle
Provides actor abstraction on RabbitMQ for dropwizard based projects.

## Dependency

```
<dependency>
    <groupId>io.appform.dropwizard.actors</groupId>
    <artifactId>dropwizard-rabbitmq-actors</artifactId>
    <version>2.0.28-4</version>
</dependency>
```

## Changelog

All notable changes to this project will be documented here.

## [2.0.28-4] - 2023-01-18

When you upgrade, consider implementing `handleExpiredMessage` to handle the expired messages differently in case needed.

### Major changes

- `publishWithExpiry` has been released which takes the message expiryTTL and handles it differently
- In case of message being expired during retries, it is handled the same way and it would be handled in `handle` method 
- Exposes `delayInMs` in consumption of the messages in the `MessageMetaData` but would be only approximate due to clock skew
- The `delayInMs` is w.r.t to the first consumption and not subsequent retries

### Changed features

- No Client Library Upgrades

## License
Apache-2.0

# NOTE
Package and group id has changed from `io.dropwizard.actors` to `io.appfrom.dropwizard.actors` from 1.3.12-1.
