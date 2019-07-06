# Patch for Magento 2.3.2 and ElasticSuite 2.8.0 implementation 
ElasticSuite - https://github.com/Smile-SA/elasticsuite

## Install

For apply composer patches place follow this documentation:
https://support.magento.com/hc/en-us/articles/360005484154-Create-a-patch-for-a-Magento-2-Composer-installation-from-a-GitHub-commit

* Copy patched into directory within your Magento root: "/patches/composer"

* Add this into your composer json: 

```
"extra": {
        "magento-force": "override",
        "composer-exit-on-patch-failure": true,
        "patches": {
            "magento/module-catalog-inventory": {
                "Elasticsearch fix for 2.3.2": "patches/composer/elastic-inventory-2-3-2.diff"
            },
            "smile/elasticsuite": {
                "Elasticsearch fix for 2.3.2": "patches/composer/elastic-elasticsuite-2-3-2.diff"
            }
        }
}
```

* And run composer update
