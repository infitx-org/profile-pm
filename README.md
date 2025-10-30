# Payment Managers Profile

This profile enables the deployment of a Payment Managers and onboarding
them to a single currency Mojaloop switch.

## Usage

1. Add it to `submodules.yaml`:

    ```yaml
    profiles/switch:
        url: https://github.com/infitx-org/profile-pm.git
        ref: main # replace this with a tag for production use
    ```

2. Configure `custom-config/cluster-config.yaml`:

    ```yaml
    currency: GHS # the currency code for the switch deployment
    switch: gisp # the switch name
    ```

3. Enable the needed test payment managers in `custom-config/pm4ml-vars.yaml`:

   ```yaml
   pm4mls:
       test-${switch}-dfsp1:
           pm4ml_enabled: true # set to true to deploy the payment manager
       test-${switch}-dfsp2:
           pm4ml_enabled: true # set to true to deploy the payment manager
       perf-${switch}-dfsp1:
           pm4ml_enabled: true # set to true to deploy the payment manager
       perf-${switch}-dfsp2:
           pm4ml_enabled: true # set to true to deploy the payment manager
   ```
