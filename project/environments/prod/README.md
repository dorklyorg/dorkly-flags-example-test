# Dorkly Flags for project: example-test environment: prod
### This file is managed by terraform. Do not edit manually.

## Description for prod environment
Production environment

## Quick Start
### Configuring SDKs
We defer to the [LaunchDarkly Relay Proxy Documentation](https://docs.launchdarkly.com/sdk/features/relay-proxy-configuration/proxy-mode) for configuring SDKs.
You'll need 2 strings:
1. Relay Proxy endpoint is: `https://dorkly-example-test.mbe39aim2pgh2.us-west-2.cs.amazonlightsail.com/`
2. For server-side SDKs: SDK Key: `sdk-prod-KCq8Idf9GYyvrcwq` or for client-side SDKs: client-side id: `prod`

- <details>
  <summary>Example: Configuring a server-side SDK</summary>
  Check out the LaunchDarkly [hello-go example](https://github.com/launchdarkly/hello-go) and modify the config as follows:

  ```golang
      dorklyConfig := ld.Config{
          ServiceEndpoints: ldcomponents.RelayProxyEndpoints("https://dorkly-example-test.mbe39aim2pgh2.us-west-2.cs.amazonlightsail.com/"),
      }

      ldClient, err := ld.MakeCustomClient("sdk-prod-KCq8Idf9GYyvrcwq", dorklyConfig, 10*time.Second)
  ```
  </details>

- <details>
  <summary>Example: Configuring a client-side SDK</summary>
  Check out the LaunchDarkly [hello-js example](https://github.com/launchdarkly/hello-js) and modify the config as follows:
  ```javascript
        // Set clientSideID to your environment name
        const clientSideID = 'prod';

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
* client-side id: `prod`

### SDK Key
* SDK Key value: `sdk-prod-KCq8Idf9GYyvrcwq`
* AWS secret arn: `arn:aws:secretsmanager:us-west-2:310766071441:secret:dorkly-example-test-prod-sdk-key-qxo5s2`
* AWS secret name: `dorkly-example-test-prod-sdk-key`
* AWS: Get secret via cli: `aws secretsmanager get-secret-value --secret-id dorkly-example-test-prod-sdk-key  | jq -r .SecretString`

### Mobile Key
* Mobile Key value: `mob-prod-BLkuom8D5YFCpAyR`
* Aws secret arn: `arn:aws:secretsmanager:us-west-2:310766071441:secret:dorkly-example-test-prod-mob-key-GzC9g3`
* Aws secret name: `dorkly-example-test-prod-mob-key`
* Get secret using aws cli: `aws secretsmanager get-secret-value --secret-id dorkly-example-test-prod-mob-key  | jq -r .SecretString`

