## Parses the main, debug, and startup logs of Icinga.

When you run this module, it performs a few tasks under the hood:

- Sets the default paths to the log files (but don’t worry, you can override the defaults)
- Makes sure each multiline log event gets sent as a single event
- Uses ingest node to parse and process the log lines, shaping the data into a structure suitable for visualizing in Kibana
- Deploys dashboards for visualizing the log data

### Compatibility

The icinga module was tested with Icinga >= 2.x on various Linux and Windows systems.

This module is not available for macOS.

### Installation

### Linux:

<i>If you haven't already installed filebeat...</i>

1. Enter the following script into the console using elevated privileges

```
curl https://github.com/themarcusaurelius/vizion.ai/blob/master/beat-install-scripts/install-config-nginx.sh > install-config-nginx.sh; chmod a+x  install-config-nginx.sh; ./install-config-nginx.sh _PLACEHOLDER_API_ENDPOINT_
```

2. When prompted, select the proper environment to complete the installation.

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<i>If you have already installed filebeat...</i>

1. Enable the module.

```
filebeat modules enable nginx
```

2. Restart Filebeat.

```
service filebeat restart
```

**Data should now be shipping to your Vizion Elastic app. Check the ```Discover``` tab in Kibana for the incoming logs**

<hr>

## Example Dashboard

This module comes with a sample dashboard. For example:

![Imgur](https://imgur.com/191aqAV.png)
