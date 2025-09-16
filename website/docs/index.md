---
title: godaddy
hide_title: false
hide_table_of_contents: false
keywords:
  - godaddy
  - stackql
  - infrastructure-as-code
  - configuration-as-data
  - cloud inventory
description: Query, deploy and manage GoDaddy resources using SQL
custom_edit_url: null
image: /img/providers/godaddy/stackql-godaddy-provider-featured-image.png
id: 'provider-intro'
---

import CopyableCode from '@site/src/components/CopyableCode/CopyableCode';

Domain registration and web hosting services.

:::info[Provider Summary] 

total services: __9__  
total resources: __29__  

:::

See also:   
[[` SHOW `]](https://stackql.io/docs/language-spec/show) [[` DESCRIBE `]](https://stackql.io/docs/language-spec/describe)  [[` REGISTRY `]](https://stackql.io/docs/language-spec/registry)
* * * 

## Installation

To pull the latest version of the `godaddy` provider, run the following command:  

```bash
REGISTRY PULL godaddy;
```
> To view previous provider versions or to pull a specific provider version, see [here](https://stackql.io/docs/language-spec/registry).  

## Authentication

The following system environment variables are used for authentication by default:  

- <CopyableCode code="GODADDY_API_KEY" /> - Godaddy API key (see <a href="https://developer.godaddy.com/keys">Creating a Godaddy API Key</a>)
  
These variables are sourced at runtime (from the local machine or as CI variables/secrets).  

<details>

<summary>Using different environment variables</summary>

To use different environment variables (instead of the defaults), use the `--auth` flag of the `stackql` program.  For example:  

```bash

AUTH='{ "godaddy": { "type": "bearer", "credentialsenvvar": "YOUR_GODADDY_API_KEY_VAR" }}'
stackql shell --auth="${AUTH}"

```
or using PowerShell:  

```powershell

$Auth = "{ 'godaddy': { 'type': 'bearer', 'credentialsenvvar': 'YOUR_GODADDY_API_KEY_VAR' }}"
stackql.exe shell --auth=$Auth

```
</details>

## Services
<div class="row">
<div class="providerDocColumn">
<a href="/services/abuse/">abuse</a><br />
<a href="/services/aftermarket/">aftermarket</a><br />
<a href="/services/agreements/">agreements</a><br />
<a href="/services/certificates/">certificates</a><br />
<a href="/services/countries/">countries</a><br />
</div>
<div class="providerDocColumn">
<a href="/services/domains/">domains</a><br />
<a href="/services/orders/">orders</a><br />
<a href="/services/shoppers/">shoppers</a><br />
<a href="/services/subscriptions/">subscriptions</a><br />
</div>
</div>
