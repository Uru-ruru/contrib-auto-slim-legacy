
This is a fork https://github.com/opentelemetry-php/contrib-auto-slim with legacy attributes support.

- `http.status_code` used as copy of `http.response.status_code`;
- `http.url` used as copy of `url.full`;
- `http.method` used as copy of `http.request.method`;
- `http.user_agent` used as copy of `user_agent.original`;
- `http.scheme` used as copy of `url.scheme`;
- `http.request_content_length_uncompressed` used as copy of `http.request.body.size`;
- `http.response_content_length_uncompressed` used as copy of `http.response.body.size`;
- `http.target` added to attributes;
- `http.host` added to attributes;

# Installation
Run `composer require uru/opentelemetry-auto-slim-legacy`.

# OpenTelemetry Slim Framework auto-instrumentation
Please read https://opentelemetry.io/docs/instrumentation/php/automatic/ for instructions on how to
install and configure the extension and SDK.

## Overview
Auto-instrumentation hooks are registered via composer, and spans will automatically be created for:
- `App::handle()` - root span
- `InvocationStrategyInterface` - controller/action
- `RoutingMiddleware::performRouting` - update root span's name with either route name or pattern

## Configuration

The extension can be disabled via [runtime configuration](https://opentelemetry.io/docs/instrumentation/php/sdk/#configuration):

```shell
OTEL_PHP_DISABLED_INSTRUMENTATIONS=slim
```
