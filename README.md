# Infernet Recipes

This is a collection of [recipes](#what-is-a-recipe) that aims to simplify:
  1. Configuring and running an [Infernet Node](https://docs.ritual.net/infernet/node/introduction).
  2. Configuring and running [services](https://infernet-services.docs.ritual.net/) on an Infernet Node.

## Node Recipes

Node recipes reside under the `node/` directory.
- Sub-directories `node/**` represent different connected chain configurations.
- Sub-directories under each chain (e.g. `node/base/**`) represent Infernet Node versions.
- Each directory `node/<chain>/<version>/` contains a `config.json`, the node recipe file, along with auxiliary files required for node deployment.

## Service recipes

Service (container) recipes reside under `services/`.
- Sub-directories `services/**` represent different Infernet-compatible [services](https://infernet-services.docs.ritual.net/).
- Sub-directories under each service (e.g. `services/onnx-inference/**`) represent service versions.
- Each directory `services/<service>/<version>/` contains a `recipe.json`, the service recipe file, along with a README with more details.

### What is a Recipe?

Recipes are `json` files that contain:
- A `config` section, which is the (incomplete) configuration object with several required and/or optional fields pre-specified.
- An `inputs` section, which describes the user inputs necessary to transform the `config` into a complete configuration object. See [Inputs](#inputs).

#### Inputs

Recipe inputs are specified by the following fields:
- `id` (string): The ID of the variable.
- `path` (string): The path in the `config` object where the variable belongs. See [Path Rules](#path-rules).
- `type` (string): The type of the variable.
- `required` (boolean): Whether user input is required.
- `default` (any, _optional_): The default value of the variable, if applicable.
- `description` (string, _optional_): The description of the variable.

#### Path Rules

Object properties within the `config` object are specified as paths joined by `.` (dots). For example, path

```js
chain.wallet.private_key
```
refers to
```js
config["chain"]["wallet"]["private_key"]
```

**Partial substitutions** are also possible with the `#`. For example, path
```js
command#NUM_WORKERS
```

refers to the substring `${NUM_WORKERS}` within
```js
config["command"]
```
