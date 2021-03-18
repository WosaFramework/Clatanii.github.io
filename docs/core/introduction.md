# Core Introduction
The core, powering the whole framework and all its components are one of the most vital, important and complex part of the framework. Therefore we do not recommend or suggest that newbies of scripting to make changes in the core. This documentation was written for experienced developers working on the project officially or non officialy to make it better.

## Enabling Development Features
We recommend you to disable the API ghostmode which will give you more in-depht logging.
```
# Disables API ghostmode which is enabled by default, gets all api logs and events
set wosa.disable_api_ghostmode 1
```

We also recommend you to enable the global `framework.dev_mode` via [this](https://github.com/WosaFramework/Framework/blob/master/wosa_core/scripting/_framework.lua) file. With the development mode enabled you will be in a more cousy development environment.