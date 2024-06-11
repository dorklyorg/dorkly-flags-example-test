# Dorkly Flags for project: example-test environment: dev
### This file is managed by terraform. Do not edit manually.

## Description for dev environment
Development environment

## Quick Start
### Configuring SDKs
We defer to the [LaunchDarkly Relay Proxy Documentation](https://docs.launchdarkly.com/sdk/features/relay-proxy-configuration/proxy-mode) for configuring SDKs.
You'll need 2 strings:
1. Relay Proxy endpoint is: `https://dorkly-example-test.mbe39aim2pgh2.us-west-2.cs.amazonlightsail.com/`
2. For server-side SDKs: SDK Key: `sdk-dev-cv0XMIgbwOceSRjg` or for client-side SDKs: client-side id: `dev`

<details>
  <summary>Example: Configuring a server-side SDK</summary>
Check out the LaunchDarkly [hello-go example](https://github.com/launchdarkly/hello-go) and modify the config as follows:

```golang
    dorklyConfig := ld.Config{
		ServiceEndpoints: ldcomponents.RelayProxyEndpoints("https://dorkly-example-test.mbe39aim2pgh2.us-west-2.cs.amazonlightsail.com/"),
	}

	ldClient, err := ld.MakeCustomClient("sdk-dev-cv0XMIgbwOceSRjg", dorklyConfig, 10*time.Second)
```
</details>
<details>
  <summary>Example: Configuring a client-side SDK</summary>
Check out the LaunchDarkly [hello-js example](https://github.com/launchdarkly/hello-js) and modify the config as follows:
```javascript
      // Set clientSideID to your environment name
      const clientSideID = 'dev';

      // Set up the evaluation context.
      const context = {
        kind: 'user',
        key: 'example-user-key',
      };

      const options = {
        baseUrl: 'https://dorkly-example-test.mbe39aim2pgh2.us-west-2.cs.amazonlightsail.com/'
        streamUrl: 'https://dorkly-example-test.mbe39aim2pgh2.us-west-2.cs.amazonlightsail.com/',
        sendEvents: false, };

      const ldclient = LDClient.initialize(clientSideID, context, options);
```
</details>

## Other handy bits
All values below and others are available as terraform outputs for easy wiring into your app.

* Endpoint for this environment: `https://dorkly-example-test.mbe39aim2pgh2.us-west-2.cs.amazonlightsail.com/`
* client-side id: `dev`

### SDK Key
* SDK Key value: `sdk-dev-cv0XMIgbwOceSRjg`
* AWS secret arn: `arn:aws:secretsmanager:us-west-2:310766071441:secret:dorkly-example-test-dev-sdk-key-fxsRT3`
* AWS secret name: `dorkly-example-test-dev-sdk-key`
* AWS: Get secret via cli: `aws secretsmanager get-secret-value --secret-id dorkly-example-test-dev-sdk-key  | jq -r .SecretString`

### Mobile Key
* Mobile Key value: `mob-dev-mmcKPPd3nwQSZdlm`
* Aws secret arn: `arn:aws:secretsmanager:us-west-2:310766071441:secret:dorkly-example-test-dev-mob-key-KBV0w5`
* Aws secret name: `dorkly-example-test-dev-mob-key`
* Get secret using aws cli: `aws secretsmanager get-secret-value --secret-id dorkly-example-test-dev-mob-key  | jq -r .SecretString`

