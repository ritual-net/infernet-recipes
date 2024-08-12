## ONNX Inference Service

### Description

Serves inference on **ONNX** models. [ONNX](https://onnx.ai/) is an open format for representing ML models that enables interoperability between different frameworks and hardware platforms. This service allows you to deploy and run models for various tasks.

### Configurations

- `MODEL_SOURCE` (`string`, `optional`)
  - For preloading a model. The source of the model.
- `LOAD_ARGS` (`string`, `optional`)
  - For preloading a model. Arguments to load model with, as a stringified object.
- `TEST_ENV` (`boolean`, `optional`)
  - Whether this is a testing instance. Defaults to `false`.
- `NUM_WORKERS` (`number`, `optional`)
  - The number of workers to use with the server. Defaults to `2`.

For configuration and usage details, check out the [ONNX Inference Service](https://infernet-services.docs.ritual.net/reference/onnx_inference_service) documentation.

### Use it

To use this recipe, include the following in your `config.json` [containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec):

```js
{
    "recipe_id": "onnx-inference_1.0.0",
    "recipe_vars": {
        "MODEL_SOURCE": <your_value_here>, // OPTIONAL
        "LOAD_ARGS": <your_value_here>,    // OPTIONAL
        "TEST_ENV": <your_value_here>,     // OPTIONAL
        "NUM_WORKERS": <your_value_here>,  // OPTIONAL
    }
}
```

**Note** that your [configurations](#configurations) must be included in `recipe_vars`.
