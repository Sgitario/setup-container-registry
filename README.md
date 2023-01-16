# @Sgitario/setup-container-registry

Setup [Docker Registry](https://docs.docker.com/registry/) with a single GitHub Action!

```yml
on: [push]
jobs:
  simple:
    name: Simple Workflow
    runs-on: ubuntu-latest
    steps:
      - id: registry
        uses: Sgitario/setup-container-registry@v1
      - name: Usage
        run: |
          # You can access the container registry via:
          # - Environment Variable: $CONTAINER_REGISTRY_URL
          # - Output: ${{ steps.registry.outputs.container-registry-url }}       
```

The following optional arguments can be configured on the job using the `with` keyword:

- `host`: the host name you want to expose. Default: `container-registry.org`
- `port`: the port you want to expose. Default: `5000`

Example:

```yml
on: [push]
jobs:
  simple:
    name: Simple Workflow
    runs-on: ubuntu-latest
    steps:
      - id: registry
        uses: Sgitario/setup-container-registry@v1
        with: 
          host: my-registry.com
          port: 3000
```