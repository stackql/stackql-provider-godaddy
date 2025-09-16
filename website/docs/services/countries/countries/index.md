--- 
title: countries
hide_title: false
hide_table_of_contents: false
keywords:
  - countries
  - countries
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

Creates, updates, deletes, gets or lists a <code>countries</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>countries</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.countries.countries" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_country"
    values={[
        { label: 'get_country', value: 'get_country' },
        { label: 'get_countries', value: 'get_countries' }
    ]}
>
<TabItem value="get_country">

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
    <td><CopyableCode code="callingCode" /></td>
    <td><code>string</code></td>
    <td>The calling code prefix used for phone numbers in this country</td>
</tr>
<tr>
    <td><CopyableCode code="countryKey" /></td>
    <td><code>string (iso-country-code)</code></td>
    <td>The ISO country-code</td>
</tr>
<tr>
    <td><CopyableCode code="label" /></td>
    <td><code>string</code></td>
    <td>The localized name of the country</td>
</tr>
<tr>
    <td><CopyableCode code="states" /></td>
    <td><code>array</code></td>
    <td>List of states/provinces in this country</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_countries">

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
    <td><CopyableCode code="callingCode" /></td>
    <td><code>string</code></td>
    <td>The calling code prefix used for phone numbers in this country</td>
</tr>
<tr>
    <td><CopyableCode code="countryKey" /></td>
    <td><code>string (iso-country-code)</code></td>
    <td>The ISO country-code</td>
</tr>
<tr>
    <td><CopyableCode code="label" /></td>
    <td><code>string</code></td>
    <td>The localized name of the country</td>
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
    <td><a href="#get_country"><CopyableCode code="get_country" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-country_key"><code>country_key</code></a>, <a href="#parameter-marketId"><code>marketId</code></a></td>
    <td><a href="#parameter-sort"><code>sort</code></a>, <a href="#parameter-order"><code>order</code></a></td>
    <td>Retrieves country and summary state information for provided countryKey. Authorization is not required.</td>
</tr>
<tr>
    <td><a href="#get_countries"><CopyableCode code="get_countries" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-marketId"><code>marketId</code></a></td>
    <td><a href="#parameter-regionTypeId"><code>regionTypeId</code></a>, <a href="#parameter-regionName"><code>regionName</code></a>, <a href="#parameter-sort"><code>sort</code></a>, <a href="#parameter-order"><code>order</code></a></td>
    <td>Retrieves summary country information for the provided marketId and filters.  Authorization is not required.</td>
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
<tr id="parameter-country_key">
    <td><CopyableCode code="country_key" /></td>
    <td><code>string (iso-country-code)</code></td>
    <td>The country key</td>
</tr>
<tr id="parameter-marketId">
    <td><CopyableCode code="marketId" /></td>
    <td><code>string (bcp-47)</code></td>
    <td>MarketId in which the request is being made, and for which responses should be localized</td>
</tr>
<tr id="parameter-order">
    <td><CopyableCode code="order" /></td>
    <td><code>string</code></td>
    <td>The direction to sort the result countries by.</td>
</tr>
<tr id="parameter-regionName">
    <td><CopyableCode code="regionName" /></td>
    <td><code>string</code></td>
    <td>Restrict countries to this region name; required if regionTypeId is supplied</td>
</tr>
<tr id="parameter-regionTypeId">
    <td><CopyableCode code="regionTypeId" /></td>
    <td><code>integer</code></td>
    <td>Restrict countries to this region type; required if regionName is supplied</td>
</tr>
<tr id="parameter-sort">
    <td><CopyableCode code="sort" /></td>
    <td><code>string</code></td>
    <td>The term to sort the result countries by.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_country"
    values={[
        { label: 'get_country', value: 'get_country' },
        { label: 'get_countries', value: 'get_countries' }
    ]}
>
<TabItem value="get_country">

Retrieves country and summary state information for provided countryKey. Authorization is not required.

```sql
SELECT
callingCode,
countryKey,
label,
states
FROM godaddy.countries.countries
WHERE country_key = '{{ country_key }}' -- required
AND marketId = '{{ marketId }}' -- required
AND sort = '{{ sort }}'
AND order = '{{ order }}'
;
```
</TabItem>
<TabItem value="get_countries">

Retrieves summary country information for the provided marketId and filters.  Authorization is not required.

```sql
SELECT
callingCode,
countryKey,
label
FROM godaddy.countries.countries
WHERE marketId = '{{ marketId }}' -- required
AND regionTypeId = '{{ regionTypeId }}'
AND regionName = '{{ regionName }}'
AND sort = '{{ sort }}'
AND order = '{{ order }}'
;
```
</TabItem>
</Tabs>
