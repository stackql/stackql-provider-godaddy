--- 
title: suggest
hide_title: false
hide_table_of_contents: false
keywords:
  - suggest
  - domains
  - godaddy
  - infrastructure-as-code
  - configuration-as-data
  - cloud inventory
description: Query, deploy and manage godaddy resources using SQL
custom_edit_url: null
image: /img/stackql-godaddy-provider-featured-image.png
---

import CopyableCode from '@site/src/components/CopyableCode/CopyableCode';
import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

Creates, updates, deletes, gets or lists a <code>suggest</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>suggest</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.suggest" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="suggest"
    values={[
        { label: 'suggest', value: 'suggest' }
    ]}
>
<TabItem value="suggest">

Request was successful

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Datatype</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
<tr>
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>Suggested domain name</td>
</tr>
</tbody>
</table>
</TabItem>
</Tabs>

## Methods

The following methods are available for this resource:

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Accessible by</th>
    <th>Required Params</th>
    <th>Optional Params</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
<tr>
    <td><a href="#suggest"><CopyableCode code="suggest" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-query"><code>query</code></a>, <a href="#parameter-country"><code>country</code></a>, <a href="#parameter-city"><code>city</code></a>, <a href="#parameter-sources"><code>sources</code></a>, <a href="#parameter-tlds"><code>tlds</code></a>, <a href="#parameter-lengthMax"><code>lengthMax</code></a>, <a href="#parameter-lengthMin"><code>lengthMin</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-waitMs"><code>waitMs</code></a></td>
    <td>Suggest alternate Domain names based on a seed Domain, a set of keywords, or the shopper's purchase history</td>
</tr>
</tbody>
</table>

## Parameters

Parameters can be passed in the `WHERE` clause of a query. Check the [Methods](#methods) section to see which parameters are required or optional for each operation.

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Datatype</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
<tr id="parameter-X-Shopper-Id">
    <td><CopyableCode code="X-Shopper-Id" /></td>
    <td><code>string</code></td>
    <td>Shopper ID for which the suggestions are being generated</td>
</tr>
<tr id="parameter-city">
    <td><CopyableCode code="city" /></td>
    <td><code>string (city-name)</code></td>
    <td>Name of city to be used as a hint for target region</td>
</tr>
<tr id="parameter-country">
    <td><CopyableCode code="country" /></td>
    <td><code>string (iso-country-code)</code></td>
    <td>Two-letter ISO country code to be used as a hint for target region NOTE: These are sample values, there are many more</td>
</tr>
<tr id="parameter-lengthMax">
    <td><CopyableCode code="lengthMax" /></td>
    <td><code>integer</code></td>
    <td>Maximum length of second-level domain</td>
</tr>
<tr id="parameter-lengthMin">
    <td><CopyableCode code="lengthMin" /></td>
    <td><code>integer</code></td>
    <td>Minimum length of second-level domain</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>integer</code></td>
    <td>Maximum number of suggestions to return</td>
</tr>
<tr id="parameter-query">
    <td><CopyableCode code="query" /></td>
    <td><code>string</code></td>
    <td>Domain name or set of keywords for which alternative domain names will be suggested</td>
</tr>
<tr id="parameter-sources">
    <td><CopyableCode code="sources" /></td>
    <td><code>array</code></td>
    <td>Sources to be queried CC_TLD - Varies the TLD using Country Codes EXTENSION - Varies the TLD KEYWORD_SPIN - Identifies keywords and then rotates each one PREMIUM - Includes variations with premium prices</td>
</tr>
<tr id="parameter-tlds">
    <td><CopyableCode code="tlds" /></td>
    <td><code>array</code></td>
    <td>Top-level domains to be included in suggestions NOTE: These are sample values, there are many more</td>
</tr>
<tr id="parameter-waitMs">
    <td><CopyableCode code="waitMs" /></td>
    <td><code>integer (integer-positive)</code></td>
    <td>Maximum amount of time, in milliseconds, to wait for responses If elapses, return the results compiled up to that point</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="suggest"
    values={[
        { label: 'suggest', value: 'suggest' }
    ]}
>
<TabItem value="suggest">

Suggest alternate Domain names based on a seed Domain, a set of keywords, or the shopper's purchase history

```sql
SELECT
domain
FROM godaddy.domains.suggest
WHERE X-Shopper-Id = '{{ X-Shopper-Id }}'
AND query = '{{ query }}'
AND country = '{{ country }}'
AND city = '{{ city }}'
AND sources = '{{ sources }}'
AND tlds = '{{ tlds }}'
AND lengthMax = '{{ lengthMax }}'
AND lengthMin = '{{ lengthMin }}'
AND limit = '{{ limit }}'
AND waitMs = '{{ waitMs }}'
;
```
</TabItem>
</Tabs>
