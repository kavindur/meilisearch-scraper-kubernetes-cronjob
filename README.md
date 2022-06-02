# meilisearch-scraper-kubernetes-cronjob

- Use following command to convert meilisearch config to a config map
```
kubectl create configmap docs-search-config --from-file=config.json --dry-run=client -o yaml > configmap.yaml
```

- Use following command to convert basic auth information to a secret
```
kubectl create secret generic docs-basic-auth-secret --from-literal=username=USERNAME --from-literal=password=PASSWORD --dry-run=client -o yaml > docs-basic-auth-secret.yaml
```

## Notes
- `MEILISEARCH_API_KEY` is to connect to meilisearch service
- `DOCS_SCRAPER_BASICAUTH_USERNAME`, `DOCS_SCRAPER_BASICAUTH_PASSWORD` is to connect to the site that we perform scraping
- ***Please make sure that we are using a scraper image version that is compatible with your meiliearch instance image version***. Otherwise you will get issues in scraping (mostly as if Bad Requests from scraper side)
  - e.g. `getmeili/docs-scraper:v0.10.4` is compatible with `getmeili/meilisearch:v0.19.0`
