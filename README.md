# Algolia Docsearch Action

This action runs the docsearch scraper and updates an index.

## Inputs

### `algolia_application_id`

**Required** Algolia docsearch `APPLICATION_ID`

### `algolia_api_key`

**Required** Algolia docsearch `API_KEY`

### `algolia_config_file`

**Required** config file able to be accessed from $GITHUB_WORKSPACE, used in tandem with `actions/checkout@master`

## Secrets

Create new ones separately `ALGOLIA_APP_ID` 和 `ALGOLIA_API_KEY` 存放 `Application ID`和 `Admin API Key`
> path: Settings -> Secrets and variables -> Actions

## Example usage

```yaml
- uses: actions/checkout@v3

- name: Push indices to Algolia
  uses: peiyanlu/algolia-docsearch-action@master
  with:
    algolia_application_id: ${{ secrets.ALGOLIA_APP_ID }}
    algolia_api_key: ${{ secrets.ALGOLIA_API_KEY }}
    # file needs to be inside $GITHUB_WORKSPACE from actions/checkout step
    algolia_config_file: algolia.config.json
```
