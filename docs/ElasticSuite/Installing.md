---
title: Installing
has_children: true
parent: ElasticSuite
nav_order: 1
---
{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

## Requirements
Elasticsuite Open Source is required for any premium module.

Each module's composer requirements should install the correct version of Elasticsuite if that's not already done.

For now, the following versions of ElasticSuite Open Source are supported:

- 2.10.x (Magento 2.4.x >= 2.4.1 && 2.4.x < 2.4.6)
- 2.11.x (Magento 2.4.x >= 2.4.6 && 2.4.x < 2.4.9)
- 2.12.x (Magento 2.4.x >= 2.4.9)

## Composer configuration
Elasticsuite Premium is made of several private packages accessible only through authentication on the privately available Smile packagist. To do so, you need to configure your composer to provide your credentials. 
That’s exactly the same process as done by Magento with their Commerce version which is available only through a private repository.
Your credentials are unique and confidential, they will be sent to you once you purchased a license.

Declare the private repository in composer.json
Add the https://elasticsuite.repo.packagist.com/yourcustomername/ composer repository to composer's config.json (usually ~/.composer/config.json):

```json
{
    [...]
    "repositories": [
        [...],
        {
            "type": "composer",
            "url": "https://elasticsuite.repo.packagist.com/yourcustomername/" 
        }
    ],
    [...]
}
```

Declare the credentials in auth.json

Add the elasticsuite.repo.packagist.com credentials to your composer's auth.json (usually ~/.composer/auth.json) as an http-basic authentication

```json
{
    "http-basic": {
        [...],
        "repo.magento.com": {
            [...]
        },
        "elasticsuite.repo.packagist.com": {
            "username": "<your unique username provided with the license>",
            "password": "<your associated password>" 
        }
    }
}
```

## Installation
On Magento 2.4.5, the Elasticsuite composer requirement is: `composer require smile/elasticsuite ~2.10.0` .

The Elasticsuite premium modules follow the same syntax. For instance `composer require smile/module-elasticsuite-facet-recommender ~2.10.0` for the facet recommender module.

You just need to require the same version that you already have for the Elasticsuite Open Source version.

<details markdown="block">
  <summary>
    List of modules and their compatibility
  </summary>

| Package / Module | Magento Open Source | Adobe Commerce | Notes |
|---|:---:|:---:|---|
| `smile/magento2-react`<br>`Smile_React` | ✅ | ✅ | Installed automatically as a dependency of `smile/module-elasticsuite-instant-search` |
| `smile/module-elasticsuite-ab-campaign`<br>`Smile_ElasticsuiteAbCampaign` | ✅ | ✅ |  |
| `smile/module-elasticsuite-ab-campaign-customer-segment`<br>`Smile_ElasticsuiteAbCampaignCustomerSegment` | ❌ | ✅ | Requires `magento/module-customer-segment` |
| `smile/module-elasticsuite-advanced-analysis`<br>`Smile_ElasticsuiteAdvancedAnalysis` | ✅ | ✅ |  |
| `smile/module-elasticsuite-amasty-compatibility`<br>`Smile_ElasticsuiteAmastyCompatibility` | ✅ | ✅ |  |
| `smile/module-elasticsuite-beacon`<br>`Smile_ElasticsuiteBeacon` | ✅ | ✅ | Installed automatically as a dependency of every premium module |
| `smile/module-elasticsuite-behavioral-autocomplete`<br>`Smile_ElasticsuiteBehavioralAutocomplete` | ✅ | ✅ |  |
| `smile/module-elasticsuite-behavioral-data`<br>`Smile_ElasticsuiteBehavioralData` | ✅ | ✅ | Installed automatically as a dependency of `smile/module-elasticsuite-behavioral-optimizer` |
| `smile/module-elasticsuite-behavioral-optimizer`<br>`Smile_ElasticsuiteBehavioralOptimizer` | ✅ | ✅ |  |
| `smile/module-elasticsuite-cascade-search`<br>`Smile_ElasticsuiteCascadeSearch` | ✅ | ✅ |  |
| `smile/module-elasticsuite-catalog-optimizer-customer-group`<br>`Smile_ElasticsuiteCatalogOptimizerCustomerGroup` | ✅ | ✅ |  |
| `smile/module-elasticsuite-catalog-optimizer-customer-segment`<br>`Smile_ElasticsuiteCatalogOptimizerCustomerSegment` | ❌ | ✅ | Requires `magento/module-customer-segment` |
| `smile/module-elasticsuite-category-monitoring`<br>`Smile_ElasticsuiteCategoryMonitoring` | ✅ | ✅ |  |
| `smile/module-elasticsuite-cms-instant-search`<br>`Smile_ElasticsuiteCmsInstantSearch` | ✅ | ✅ | [Extra module](#extra-modules) |
| `smile/module-elasticsuite-configurable-product`<br>`Smile_ElasticsuiteConfigurableProduct` | ✅ | ✅ |  |
| `smile/module-elasticsuite-explain`<br>`Smile_ElasticsuiteExplain` | ✅ | ✅ |  |
| `smile/module-elasticsuite-facet-recommender`<br>`Smile_ElasticsuiteFacetRecommender` | ✅ | ✅ |  |
| `smile/module-elasticsuite-global-behavioral-data`<br>`Smile_ElasticsuiteGlobalBehavioralData` | ✅ | ✅ | [Extra module](#extra-modules) |
| `smile/module-elasticsuite-global-optimizer`<br>`Smile_ElasticsuiteGlobalOptimizer` | ✅ | ✅ |  |
| `smile/module-elasticsuite-google-analytics`<br>`Smile_ElasticsuiteGoogleAnalytics` | ❌ | ✅ | Relies on `Magento_GoogleTagManager` |
| `smile/module-elasticsuite-hyva-compatibility`<br>`Smile_ElasticsuiteHyvaCompatibility` | ✅ | ✅ | [Extra module](#extra-modules), Hyvä theme only |
| `smile/module-elasticsuite-instant-search`<br>`Smile_ElasticsuiteInstantSearch` | ✅ | ✅ |  |
| `smile/module-elasticsuite-layered-navigation`<br>`Smile_ElasticsuiteLayeredNavigation` | ✅ | ✅ |  |
| `smile/module-elasticsuite-neural-search`<br>`Smile_ElasticsuiteNeuralSearch` | ✅ | ✅ | [Extra module](#extra-modules), from `~2.11.0`, OpenSearch >= 2.13 |
| `smile/module-elasticsuite-recommender`<br>`Smile_ElasticsuiteRecommender` | ✅ | ✅ |  |
| `smile/module-elasticsuite-recommender-explain`<br>`Smile_ElasticsuiteRecommenderExplain` | ✅ | ✅ |  |
| `smile/module-elasticsuite-recommender-graph-ql`<br>`Smile_ElasticsuiteRecommenderGraphQl` | ✅ | ✅ |  |
| `smile/module-elasticsuite-recommender-target-rule-proxy`<br>`Smile_ElasticsuiteRecommenderTargetRuleProxy` | ❌ | ✅ | Requires `magento/module-target-rule` |
| `smile/module-elasticsuite-term-recommender`<br>`Smile_ElasticsuiteTermRecommender` | ✅ | ✅ |  |
| `smile/module-elasticsuite-virtual-attribute`<br>`Smile_ElasticsuiteVirtualAttribute` | ✅ | ✅ |  |

</details>

### 1a. Install the modules : On Magento Open Source

For Magento Open Source edition, you would not be able to install the modules `smile/module-elasticsuite-catalog-optimizer-customer-segment` and `smile/module-elasticsuite-ab-campaign-customer-segment` because they require the `magento/module-customer-segment` which is only included in Adobe Commerce.

The simplest way to install all the modules compatible with Magento Open Source is to require our composer **metapackage**:

```
composer --ignore-platform-reqs require smile/elasticsuite-premium-magento [version-requirement]
```

Where `[version-requirement]` must match the Elasticsuite Open Source branch compatible with your Magento version:

| `[version-requirement]` | Magento version            |
|-------------------------|----------------------------|
| `~2.10.0`               | 2.4.1 <= Magento < 2.4.6   |
| `~2.11.0`               | 2.4.6 <= Magento < 2.4.9   |
| `~2.12.0`               | Magento >= 2.4.9           |
{: #version-requirement }

See the [Elasticsuite compatibility matrix](https://github.com/Smile-SA/elasticsuite#which-version-should-i-use).

For instance, on Magento 2.4.7: `composer --ignore-platform-reqs require smile/elasticsuite-premium-magento ~2.11.0`

### 1b. Install the modules : On Adobe Commerce

The simplest way to install all the modules compatible with Adobe Commerce is to require our composer **metapackage**:

```
composer --ignore-platform-reqs require smile/elasticsuite-premium-commerce [version-requirement]
```

See the [`[version-requirement]` / Magento version table](#version-requirement) above.

### 2a. Enable all modules if needed : On Magento Open Source

```
php bin/magento module:enable Smile_ElasticsuiteAbCampaign \
Smile_ElasticsuiteAdvancedAnalysis \
Smile_ElasticsuiteAmastyCompatibility \
Smile_ElasticsuiteBeacon \
Smile_ElasticsuiteBehavioralAutocomplete \
Smile_ElasticsuiteBehavioralData \
Smile_ElasticsuiteBehavioralOptimizer \
Smile_ElasticsuiteCascadeSearch \
Smile_ElasticsuiteCatalogOptimizerCustomerGroup \
Smile_ElasticsuiteCategoryMonitoring \
Smile_ElasticsuiteConfigurableProduct \
Smile_ElasticsuiteExplain \
Smile_ElasticsuiteFacetRecommender \
Smile_ElasticsuiteGlobalOptimizer \
Smile_ElasticsuiteInstantSearch \
Smile_ElasticsuiteLayeredNavigation \
Smile_ElasticsuiteRecommender \
Smile_ElasticsuiteRecommenderExplain \
Smile_ElasticsuiteRecommenderGraphQl \
Smile_ElasticsuiteTermRecommender \
Smile_ElasticsuiteVirtualAttribute \
Smile_React
```

### 2b. Enable all modules if needed : On Adobe Commerce

```
php bin/magento module:enable Smile_ElasticsuiteAbCampaign \
Smile_ElasticsuiteAbCampaignCustomerSegment \
Smile_ElasticsuiteAdvancedAnalysis \
Smile_ElasticsuiteAmastyCompatibility \
Smile_ElasticsuiteBeacon \
Smile_ElasticsuiteBehavioralAutocomplete \
Smile_ElasticsuiteBehavioralData \
Smile_ElasticsuiteBehavioralOptimizer \
Smile_ElasticsuiteCascadeSearch \
Smile_ElasticsuiteCatalogOptimizerCustomerGroup \
Smile_ElasticsuiteCatalogOptimizerCustomerSegment \
Smile_ElasticsuiteCategoryMonitoring \
Smile_ElasticsuiteConfigurableProduct \
Smile_ElasticsuiteExplain \
Smile_ElasticsuiteFacetRecommender \
Smile_ElasticsuiteGlobalOptimizer \
Smile_ElasticsuiteGoogleAnalytics \
Smile_ElasticsuiteInstantSearch \
Smile_ElasticsuiteLayeredNavigation \
Smile_ElasticsuiteRecommender \
Smile_ElasticsuiteRecommenderExplain \
Smile_ElasticsuiteRecommenderGraphQl \
Smile_ElasticsuiteRecommenderTargetRuleProxy \
Smile_ElasticsuiteTermRecommender \
Smile_ElasticsuiteVirtualAttribute \
Smile_React
```

### 3. Run setup and reindex.
{: #run-setup-and-reindex }

As usual after installing a Magento2 module, clean the cache and run `setup:upgrade` (if in production mode, also run `setup:di:compile` and `setup:static-content:deploy`).

You will also need to reindex the catalog with either:

```
bin/magento indexer:reindex (reindexing everything)
bin/magento indexer:reindex catalogsearch_fulltext (just to reindex catalog products)
```

### 4. Register your client id
Elasticsuite premium packages are embedded with a “beacon” feature that will periodically trigger pings to the Smile information system. This is mandatory to configure it properly by putting the correct client id into it, so that Smile remains able to identify which website is using the solution.

To configure this, you have to go to **Stores > Configuration > Elasticsuite > Elasticsuite Premium Beacon** and fill the Client ID field with the value that has been provided to you.

If we provided environment specific client ids, you will have to configure each environment with the proper client Id.

## Extra modules

The following premium modules are not part of the `smile/elasticsuite-premium-magento` and `smile/elasticsuite-premium-commerce` metapackages and must be required and enabled separately, if needed.
They follow the same `[version-requirement]` as the metapackages (see the [`[version-requirement]` / Magento version table](#version-requirement)).

| Package | Module | Notes |
|---|---|---|
| `smile/module-elasticsuite-global-behavioral-data` | `Smile_ElasticsuiteGlobalBehavioralData` | For multi-store installations, allows Elasticsuite to "share" the behavioral data between stores, so a newly launched or low traffic store can benefit from your main store products related behavioral metrics. |
| `smile/module-elasticsuite-cms-instant-search` | `Smile_ElasticsuiteCmsInstantSearch` | Adds CMS pages to the Instant Search. Also installs the Open Source `smile/module-elasticsuite-cms-search` module, which must be enabled too (`Smile_ElasticsuiteCms`). |
| `smile/module-elasticsuite-hyva-compatibility` | `Smile_ElasticsuiteHyvaCompatibility` | Makes Premium features compatible with the Hyvä theme (requires `hyva-themes/magento2-smile-elasticsuite` which does the same for Elasticsuite Open Source). |
| `smile/module-elasticsuite-neural-search` | `Smile_ElasticsuiteNeuralSearch` | Starting from `~2.11.0` only. Requires OpenSearch >= 2.13, see the "Installing and configuring Neural Search module" page. |

For instance:

```
composer --ignore-platform-reqs require smile/module-elasticsuite-global-behavioral-data [version-requirement]
php bin/magento module:enable Smile_ElasticsuiteGlobalBehavioralData
```

Then run setup and reindex as described in [step 3](#run-setup-and-reindex).

## Instant Search

The `smile/module-elasticsuite-instant-search` requires `smile/magento2-react` to provide a React based autocomplete search feature: it will be automatically required and installed when requiring `smile/module-elasticsuite-instant-search`.

`smile/magento2-react` will add `package-magento-react.json` in your project repository. You will need to merge the content of this file with your `package.json` file. If you don't have any pre-existing `package.json` at the project root, you can rename the `package-magento-react.json` to `package.json`

`smile/magento2-react` requires yarn to be installed on the deployment frontend servers, in order to build and package the React JavaScript sources.

See the instructions below for "Installing yarn".

### Installing Yarn
The latest yarn version must be installed by following https://classic.yarnpkg.com/en/docs/install
E.g. on a debian based environment, the following steps are

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update && sudo apt install yarn
```

### Building React sources
In your development environment, you should have a package.json and webpack.config.js files that are copied to the Magento root directory when installing the smile/magento2-react module.
If that’s not the case, copy the vendor/smile/magento2-react/package.json and vendor/smile/magento2-react/webpack.config.js to your magento root directory.
On your dev environment, we recommend adding webpack.config.js (and package.json if not already versioned) to your  .gitgnore.

To build the React sources, run the following commands  in your magento directory with the appropriate user (the same that owns the Magento sources, usually www-data):

```
sudo -u www-data yarn install
sudo -u www-data mkdir -p var/tmp && sudo -u www-data yarn build
```

In your development environment, you can also replace the yarn build by yarn dev .
Please note that the user must have write permissions on his home directory.

### Embed the React sources in delivery packages
Depending on how you are building packages to be delivered on staging, pre-production and production environments, you will need to tailor your strategy to either build the React sources locally before packaging, or delegate this task to the target environment at the end of the delivery process.

We recommend doing it locally (or through a CI/CD pipeline) before packaging the application (like Magento does with the di:compile and static-content:deploy step) rather than letting the target servers to proceed.

#### [OPTIONAL] Building React sources with Magento Cloud
If your project is hosted on magento cloud, you need some specific configuration in order to make the instant search working.
In your project directory, you should have a .magento.app.yaml file with the definition of the hook "build" in it :

```yaml
hoks:
   build: |
    	set -e
    	composer install
    	php ./vendor/bin/ece-tools run scenario/build/generate.xml
    	php ./vendor/bin/ece-tools run scenario/build/transfer.xml
 ```

You need to add the installation of yarn and the building of the react app in this step:

```yaml
hooks:
   build: |
        set -e
        npm install --global yarn
        composer install
        php ./vendor/bin/ece-tools run scenario/build/generate.xml
        mkdir -p var/tmp
        yarn install
        yarn build
        php ./vendor/bin/ece-tools run scenario/build/transfer.xml
```

Then you need to indicate to Magento not to update the package.json file during the composer install process of the deployment. In the composer.json file of your project, add these lines :

```json
{
    ...
    "extra": {
        ...
        "magento-deploy-ignore": {
            "smile/magento2-react": [
                "/package.json"
            ]
        },
        ...
    }
    ....
}
```

#### [OPTIONAL] Building React sources in isolation when you already have a package.json

When you already have a package.json at the root of your Magento project, for instance per your own theme building requirements, it is possible to isolate the building of the Instant Search's React sources.

In that case, you will want first to prevent the `composer install` step to copy at the root of your Magento project the smile/magento2-react's `package.json` and `webpack.config.js` by adding this in your composer.json :
```json
{
    ...
    "extra": {
        ...
        "magento-deploy-ignore": {
            "smile/magento2-react": [
                "/package.json",
                "/webpack.config.js"
            ]
        },
        ...
    }
    ....
}
```

Then, when building React sources, you will be able to use
* the ability of `yarn` to work elsewhere than in the current directory (your Magento project's root) using the yarn option `--cwd [directory]`
* the fact that the `webpack.config.js` can use a `MAGENTO_ROOT` environment variable to locate your Magento project's root

For instance, on Magento Cloud, this would be the sequence to build the React sources inside the `smile/magento2-react` package directory in vendor 
```yaml
hooks:
   build: |
        set -e
        npm install --global yarn
        composer install
        php ./vendor/bin/ece-tools run scenario/build/generate.xml
        mkdir -p var/tmp
        yarn --cwd vendor/smile/magento2-react install
        MAGENTO_ROOT=$(pwd) yarn --cwd vendor/smile/magento2-react build
        php ./vendor/bin/ece-tools run scenario/build/transfer.xml
```

The first command `yarn --cwd vendor/smile/magento2-react install` will make it so that the `node_modules` and `yarn.lock` specific to dependencies of the Instant Search component are located in the `vendor/smile/magento2-react` directory and do not pollute/conflict any `node_modules` or `yarn.lock` located in the root of your Magento project.

The second command `MAGENTO_ROOT=$(pwd) yarn --cwd vendor/smile/magento2-react build` 
* makes sure to build the Instant Search React component in that same contained `vendor/smile/magento2-react` space
* while letting the `vendor/smile/magento2-react/webpack.config.js` file correctly locate all possible React sources in your project (including those of the Instant Search component, of course)  

## Tracking
### Integration with Magento Cloud
You will need to ask magento to add the following configuration to elasticsearch (or opensearch) :
in  /etc/opensearch/opensearch.yml add :

```
script.allowed_types: inline
script.allowed_contexts: search,update,aggs
```

### Integration with Magento Cloud and/or Fastly

If you are using Magento Cloud. or simply using Fastly, it's likely that it will block the tracker request.

To fix this you can either add a custom VCL or set the Tracker to use the REST Api.

#### The custom VCL

You should reach the Fastly configuration : 

<img alt="Fastly 1" src="static/fastly1.PNG" />

And then add this VCL in the "recv" section : 

```
if (req.url ~ "/elasticsuite/tracker/hit/image(/.*)?$") {
	set req.http.X-Fastly-Imageopto-Api = "none";
	return (pass);
}
```

<img alt="Fastly 2" src="static/fastly2.PNG" />

#### Use the REST Api

You can go to **Stores > Configuration > Elasticsuite > Tracking** and set **Use the API to collect data** to **Yes**

## Headless

If you're running an headless website, please check the two following pages : 
