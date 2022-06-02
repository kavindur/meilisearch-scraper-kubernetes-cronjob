# meilisearch-scraper-kubernetes-cronjob

Use following command to convert meilisearch config to a config map and create it using kubectl apply
`kubectl create configmap docs-search-config --from-file=config.json --dry-run=client -o yaml > configmap.yaml`

## Notes
MEILISEARCH_API_KEY is to connect to meilisearch service
DOCS_SCRAPER_BASICAUTH_USERNAME, DOCS_SCRAPER_BASICAUTH_PASSWORD is to connect to the site that we perform scraping


