# Infernet Services Registry

This is a collection of [recipes](#what-is-a-recipe) for running [Infernet](https://docs.ritual.net/infernet/about)-compatible services. This repo aims to:
  1. Standardize service IDs across the Infernet network.
  2. Document service descriptions, configurations, and data schemas.
  3. Make it trivial to configure and run services on an [Infernet Node](https://docs.ritual.net/infernet/node/introduction) via [recipes](#what-is-a-recipe).

To ensure consistent identification and configuration of official Infernet-compatible services across the network, Infernet Nodes **enforce** the use of recipes for official services. As such, you cannot run custom containers with an ID matching any of the official services under the `services/` directory; and you can ONLY run an official service using a [recipe](#what-is-a-recipe).

### Structure

- Services are represented by directories under `services/`, and are versioned using subdirectories. 
- Service IDs:
  - **Consist of** a `name` and a `version`, in the format `<name>_<version>`, corresponding to the directory `services/<name>/<version>` within this repo.
  - **Are reserved**, i.e. they uniquely describe a service across the [Infernet](https://docs.ritual.net/infernet/about) network.
- Each `<name>/<version>/` is a directory that contains:
    - A `README.md` with the service description, configuration details, and input data structure.
    - A `recipe.json`, i.e. the recipe for running the Infernet-compatible service.

### What is a Recipe?

Recipes are `json` files used to [configure containers](https://docs.ritual.net/infernet/node/configuration#containers-arraycontainer_spec) (i.e. _services_) on an [Infernet Node](https://docs.ritual.net/infernet/node/introduction). They are identified by a `service` and a `version`.

#### Rules

- Recipes **must** contain:
  - `id` (`string`): Service ID.
  - `image` (`string`): [Dockerhub](https://hub.docker.com) image ID.
- Recipes **may** contain:
  - `command` (`string`): Command to run the container with.
  - `env` (`object`): Environment variables to pass into the container.
  - `description` (`string`): A brief description of the service.
- The above _may_ contain __templated__ variables that must be specified by the node operator, in the form of `${TEMPLATED_VARIABLE}` (see `recipe_vars` below).
  - Some templated variables are _required_, others may be optional and defaulted.

#### Usage

To use a recipe, you must specify:
- `recipe_id` (`string`): The Service ID of the desired service, i.e. `<name>_<version>`.
- `recipe_vars` (`object`, optional): The variables to substitute for any templated recipe variables.

See Infernet's [container configuration](https://docs.ritual.net/infernet/node/configuration#container_spec-object) docs for complete configuration instructions.