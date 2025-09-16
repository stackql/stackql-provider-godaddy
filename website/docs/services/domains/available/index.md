--- 
title: available
hide_title: false
hide_table_of_contents: false
keywords:
  - available
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

Creates, updates, deletes, gets or lists an <code>available</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>available</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.available" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="available"
    values={[
        { label: 'available', value: 'available' }
    ]}
>
<TabItem value="available">

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
    <td><CopyableCode code="available" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain name is available</td>
</tr>
<tr>
    <td><CopyableCode code="currency" /></td>
    <td><code>string (iso-currency-code)</code></td>
    <td>Currency in which the `price` is listed. Only returned if tld is offered (default: USD)</td>
</tr>
<tr>
    <td><CopyableCode code="definitive" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the `available` answer has been definitively verified with the registry</td>
</tr>
<tr>
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>Domain name</td>
</tr>
<tr>
    <td><CopyableCode code="period" /></td>
    <td><code>integer (integer-positive)</code></td>
    <td>Number of years included in the price. Only returned if tld is offered</td>
</tr>
<tr>
    <td><CopyableCode code="price" /></td>
    <td><code>integer (currency-micro-unit)</code></td>
    <td>Price of the domain excluding taxes or fees. Only returned if tld is offered</td>
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
    <td><a href="#available"><CopyableCode code="available" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-checkType"><code>checkType</code></a>, <a href="#parameter-forTransfer"><code>forTransfer</code></a></td>
    <td>Determine whether or not the specified domain is available for purchase</td>
</tr>
<tr>
    <td><a href="#available_bulk"><CopyableCode code="available_bulk" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td><a href="#parameter-checkType"><code>checkType</code></a></td>
    <td>Determine whether or not the specified domains are available for purchase</td>
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
<tr id="parameter-domain">
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>Domain name whose availability is to be checked</td>
</tr>
<tr id="parameter-checkType">
    <td><CopyableCode code="checkType" /></td>
    <td><code>string</code></td>
    <td>Optimize for time ('FAST') or accuracy ('FULL')</td>
</tr>
<tr id="parameter-forTransfer">
    <td><CopyableCode code="forTransfer" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not to include domains available for transfer. If set to True, checkType is ignored</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="available"
    values={[
        { label: 'available', value: 'available' }
    ]}
>
<TabItem value="available">

Determine whether or not the specified domain is available for purchase

```sql
SELECT
available,
currency,
definitive,
domain,
period,
price
FROM godaddy.domains.available
WHERE domain = '{{ domain }}' -- required
AND checkType = '{{ checkType }}'
AND forTransfer = '{{ forTransfer }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="available_bulk"
    values={[
        { label: 'available_bulk', value: 'available_bulk' }
    ]}
>
<TabItem value="available_bulk">

Determine whether or not the specified domains are available for purchase

```sql
EXEC godaddy.domains.available.available_bulk 
@checkType='{{ checkType }}'
;
```
</TabItem>
</Tabs>
