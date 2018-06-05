## Overview

fluent-plugin-raygun is a fluentd output plugin that sends aggregated errors/exception events to Raygun. Raygun is a event logging and aggregation platform (and more!).<br>

This plugin extends the fluent buffered output and reports the events as crash reports to your Raygun dashboard. Currently we support limited information in the reports sent by our plugin. The reports include the following information:

```OccuredOn``` - The date & time in which the event was sent by the raygun plugin.

```MachineName``` - The hostname provided through the plugin configuration.

```ErrorMessage``` - The event's record message.

```Tags``` - The tag used to seperate the event in the fluentd logging.

## Requirements
This plugin requires:

- Ruby v1.9.3 or higher
- FluentD v0.12 or v0.10

## Setup Instructions
Once FluentD has been installed following the instructions detailed here.

Install the Raygun plugin using ```gem```:

```gem install fluent-plugin-raygun```

Update your FluentD config to include a matching rule to output to Raygun:

```
<match>
   @type raygun
   api_key YOUR_API_KEY
</match>
```

## Options

```api_key``` - The key used to validate the reports sent to Raygun. Found in the Raygun dashboard under application settings.

```default_level``` - The logging level at which to send events (options: fatal, error, warning, info or debug). The default is set to error.

```default_logger``` - If a logger is not provided the default logger is used. The default is set to fluentd. 

```endpoint_url``` - The URL used by the raygun plugin to post reports to. The default is set to https://api.raygun.com.

```flush_interval``` - The time between data flushes. The default is set to zero (0) seconds.

```hostname_command``` - The name of the server reporting the error. The default is set to hostname.

```record_already_formatted``` - If set to false we transform the event's record into the format required by raygun's API. The default is set to false.

## Copyright

Copyright © 2018 - Raygun ([@raygunio](https://twitter.com/raygunio))

## License

MIT License
