
This is a fork https://github.com/opentelemetry-php/contrib-auto-slim with legacy attributes support.

- `http.status_code` used as copy of `http.response.status_code`.

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
