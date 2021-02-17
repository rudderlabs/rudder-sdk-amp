# What is RudderStack?

[RudderStack](https://rudderstack.com/) is a **customer data pipeline** tool for collecting, routing and processing data from your websites, apps, cloud tools, and data warehouse.

More information on RudderStack can be found [here](https://github.com/rudderlabs/rudder-server).

## Analytics for AMP

You can use RudderStack's `amp-analytics` component to send event data from your AMP page, directly to Rudderstack and eventually to your configured destinations.

Only Cloud mode destinations are supported as AMP directly sends data to our server-side APIs, we then send this data to your configured destinations.

## How to use RudderStack with `amp-analytics`?

This Quick Start Guide will help you get up and running with using RudderStack's `amp-analytics` component in no time. You just need to follow the steps below:
1. Include the `amp-analytics` component, before the closing `</head>` tag :
	```
	<script async custom-element="amp-analytics" src="https://cdn.ampproject.org/v0/amp-analytics-0.1.js"></script>
	```
2. Copy the following RudderStack analytics snippet within your `<body>` tags:
	```
    <amp-analytics config="https://cdn.rudderlabs.com/amp/rudderstack.json">
      <script type="application/json">
        {
          "vars": {
              "writeKey": "WRITE_KEY",
              "dataPlaneUrl": "DATA_PLANE_URL",
              "pageName": "Your Page Name"
          }
        }
      </script>
    </amp-analytics>
   ```
	A page call is automatically sent when you include this snippet in your AMP page.
	
	Make sure you replace `WRITE_KEY` and `DATA_PLANE_URL` with your own values.Refer to the [documentation](https://docs.rudderstack.com/sdk-integration-guide/getting-started-with-javascript-sdk/amp-analytics) for instructions on how to get these values.

## Hosting RudderStack's `amp-analytics` configuration JSON

If you want to modify RudderStack's `amp-analytics` configuration JSON, follow the steps below :
1. Fetch the JSON from [RudderStack's CDN](https://cdn.rudderlabs.com/amp/rudderstack.json)
2. Modify the JSON as per your preferences
3. Host the modified JSON
4. Add the path to your hosted JSON, as the value of the `config` attribute of the `<amp-analytics>` tag
Suppose you hosted your modified JSON at "https://example.com/modifiedConfig.json", then your RudderStack analytics snippet would be:
```
  <amp-analytics config="https://example.com/modifiedConfig.json">
    <script type="application/json">
      ...
    </script>
  </amp-analytics>
```
If you just want to host the original configuration JSON yourself, just skip Step 2 in the above sequence.

## Contact Us

If you come across any issues while configuring or using RudderStack with AMP Analytics, please feel free to start a conversation on our [Slack](https://resources.rudderstack.com/join-rudderstack-slack) channel. We will be happy to help you.
