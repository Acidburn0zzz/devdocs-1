---
layout: default
group:  migration
subgroup: Migrate using the data migration tool
title: Migrate using the data migration tool
menu_title: Migrate using data migration tool
menu_node: parent
menu_order: 4
github_link: migration/migration-migrate.md
redirect_from: /guides/v1.0/migration/migration-migrate.html
---

  
<h2 id="migration-command">Migrating settings, data, and changes</h2>

###General rules for successful migration

During the time you're migrating:

*	Do not make any changes in the Magento 1 Admin except for order management (shipping, creating invoice, credit memos etc.)
*	Stop all Magento 1 cron jobs
*	Do not alter any code
*	Do not make changes in the Magento 2 Admin and storefront

All operations in Magento 1 storefront are allowed at this time.

###Run Data Migration Tool

Run the Data Migration Tool from `<your Magento 2 install dir>/vendor/magento/data-migration-tool/bin`

Command syntax:

	php migrate <mode> --config=path/to/config.xml [options]

where `<mode>` can be:

*	`data` to migrate database data
*	`delta` to migrate data that is added to the database since you last ran the tool with the `data` option
*	`settings` to migrate Magento Admin settings

where `[options]` can be:

*	`--reset` to start the migration from the beginning
*	`--config <value>` path to `config.xml`
*	`--verbose <level>` DEBUG, INFO, NONE (default is INFO)
*	`--help` Displays help for the command

<div class="bs-callout bs-callout-info" id="info">
<span class="glyphicon-class">
  <p>Logs are written to the <code>&lt;your Magento install dir>/vendor/magento/migration-tool/var</code></p></span>
</div>

The following sections should be performed in a specific order:

1.	<a href="{{ site.gdeurl }}migration/migration-migrate-settings.html">Migrate settings</a>
3.	<a href="{{ site.gdeurl }}migration/migration-migrate-data.html">Migrate data</a>
4.	<a href="{{ site.gdeurl }}migration/migration-migrate-delta.html">Migrate changes</a>

