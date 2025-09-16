--- 
title: subscriptions
hide_title: false
hide_table_of_contents: false
keywords:
  - subscriptions
  - subscriptions
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

Creates, updates, deletes, gets or lists a <code>subscriptions</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>subscriptions</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.subscriptions.subscriptions" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get"
    values={[
        { label: 'get', value: 'get' },
        { label: 'list', value: 'list' }
    ]}
>
<TabItem value="get">

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
    <td><CopyableCode code="addons" /></td>
    <td><code>array</code></td>
    <td>An array of additional products that have been purchased to augment this Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="billing" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="cancelable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is allowed to be canceled</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>When the Subscription was created</td>
</tr>
<tr>
    <td><CopyableCode code="expiresAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>When the Subscription will expire</td>
</tr>
<tr>
    <td><CopyableCode code="label" /></td>
    <td><code>string</code></td>
    <td>A human readable description of this Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="launchUrl" /></td>
    <td><code>string (url)</code></td>
    <td>The url to use or manage this Subscription's active product</td>
</tr>
<tr>
    <td><CopyableCode code="paymentProfileId" /></td>
    <td><code>integer</code></td>
    <td>Unique identifier of the payment profile that will be used to automatically renew this Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="priceLocked" /></td>
    <td><code>boolean</code></td>
    <td>Whether the renewal price will be based from the list price or a locked-in price for this shopper</td>
</tr>
<tr>
    <td><CopyableCode code="product" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="relations" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="renewAuto" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is set to be automatically renewed via the billing agent</td>
</tr>
<tr>
    <td><CopyableCode code="renewable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is allowed to be renewed</td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td>Whether the Subscription is active or the specific non-active state</td>
</tr>
<tr>
    <td><CopyableCode code="subscriptionId" /></td>
    <td><code>string</code></td>
    <td>Unique identifier of the Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="upgradeable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is allowed to be upgraded</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="list">

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
    <td><CopyableCode code="addons" /></td>
    <td><code>array</code></td>
    <td>An array of additional products that have been purchased to augment this Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="billing" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="cancelable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is allowed to be canceled</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>When the Subscription was created</td>
</tr>
<tr>
    <td><CopyableCode code="expiresAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>When the Subscription will expire</td>
</tr>
<tr>
    <td><CopyableCode code="label" /></td>
    <td><code>string</code></td>
    <td>A human readable description of this Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="launchUrl" /></td>
    <td><code>string (url)</code></td>
    <td>The url to use or manage this Subscription's active product</td>
</tr>
<tr>
    <td><CopyableCode code="paymentProfileId" /></td>
    <td><code>integer</code></td>
    <td>Unique identifier of the payment profile that will be used to automatically renew this Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="priceLocked" /></td>
    <td><code>boolean</code></td>
    <td>Whether the renewal price will be based from the list price or a locked-in price for this shopper</td>
</tr>
<tr>
    <td><CopyableCode code="product" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="relations" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="renewAuto" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is set to be automatically renewed via the billing agent</td>
</tr>
<tr>
    <td><CopyableCode code="renewable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is allowed to be renewed</td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td>Whether the Subscription is active or the specific non-active state</td>
</tr>
<tr>
    <td><CopyableCode code="subscriptionId" /></td>
    <td><code>string</code></td>
    <td>Unique identifier of the Subscription</td>
</tr>
<tr>
    <td><CopyableCode code="upgradeable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the Subscription is allowed to be upgraded</td>
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
    <td><a href="#get"><CopyableCode code="get" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-subscription_id"><code>subscription_id</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>Retrieve details for the specified Subscription</td>
</tr>
<tr>
    <td><a href="#list"><CopyableCode code="list" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a>, <a href="#parameter-productGroupKeys"><code>productGroupKeys</code></a>, <a href="#parameter-includes"><code>includes</code></a>, <a href="#parameter-offset"><code>offset</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-sort"><code>sort</code></a></td>
    <td>Retrieve a list of Subscriptions for the specified Shopper</td>
</tr>
<tr>
    <td><a href="#_list"><CopyableCode code="_list" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a>, <a href="#parameter-productGroupKeys"><code>productGroupKeys</code></a>, <a href="#parameter-includes"><code>includes</code></a>, <a href="#parameter-offset"><code>offset</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-sort"><code>sort</code></a></td>
    <td>Retrieve a list of Subscriptions for the specified Shopper</td>
</tr>
<tr>
    <td><a href="#product_groups"><CopyableCode code="product_groups" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>Retrieve a list of ProductGroups for the specified Shopper</td>
</tr>
<tr>
    <td><a href="#cancel"><CopyableCode code="cancel" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-subscription_id"><code>subscription_id</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Cancel the specified Subscription</td>
</tr>
<tr>
    <td><a href="#update"><CopyableCode code="update" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-subscription_id"><code>subscription_id</code></a></td>
    <td></td>
    <td>Only Subscription properties that can be changed without immediate  financial impact can be modified via PATCH, whereas some properties  can be changed by purchasing a renewal  This endpoint only supports JWT authentication</td>
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
<tr id="parameter-subscription_id">
    <td><CopyableCode code="subscription_id" /></td>
    <td><code>string</code></td>
    <td>Unique identifier of the Subscription to update</td>
</tr>
<tr id="parameter-X-Market-Id">
    <td><CopyableCode code="X-Market-Id" /></td>
    <td><code>string</code></td>
    <td>The market that the response should be formatted for</td>
</tr>
<tr id="parameter-X-Shopper-Id">
    <td><CopyableCode code="X-Shopper-Id" /></td>
    <td><code>string</code></td>
    <td>Shopper ID to cancel subscriptions for when not using JWT</td>
</tr>
<tr id="parameter-includes">
    <td><CopyableCode code="includes" /></td>
    <td><code>array</code></td>
    <td>Optional details to be included in the response</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>integer</code></td>
    <td>Number of Subscriptions to retrieve in this page, starting after offset</td>
</tr>
<tr id="parameter-offset">
    <td><CopyableCode code="offset" /></td>
    <td><code>integer</code></td>
    <td>Number of Subscriptions to skip before starting to return paged results (must be a multiple of the limit)</td>
</tr>
<tr id="parameter-productGroupKeys">
    <td><CopyableCode code="productGroupKeys" /></td>
    <td><code>array</code></td>
    <td>Only return Subscriptions with the specified product groups</td>
</tr>
<tr id="parameter-sort">
    <td><CopyableCode code="sort" /></td>
    <td><code>string</code></td>
    <td>Property name that will be used to sort results. "-" indicates descending</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get"
    values={[
        { label: 'get', value: 'get' },
        { label: 'list', value: 'list' }
    ]}
>
<TabItem value="get">

Retrieve details for the specified Subscription

```sql
SELECT
addons,
billing,
cancelable,
createdAt,
expiresAt,
label,
launchUrl,
paymentProfileId,
priceLocked,
product,
relations,
renewAuto,
renewable,
status,
subscriptionId,
upgradeable
FROM godaddy.subscriptions.subscriptions
WHERE subscription_id = '{{ subscription_id }}' -- required
AND X-Shopper-Id = '{{ X-Shopper-Id }}'
AND X-Market-Id = '{{ X-Market-Id }}'
;
```
</TabItem>
<TabItem value="list">

Retrieve a list of Subscriptions for the specified Shopper

```sql
SELECT
addons,
billing,
cancelable,
createdAt,
expiresAt,
label,
launchUrl,
paymentProfileId,
priceLocked,
product,
relations,
renewAuto,
renewable,
status,
subscriptionId,
upgradeable
FROM godaddy.subscriptions.subscriptions
WHERE X-Shopper-Id = '{{ X-Shopper-Id }}'
AND X-Market-Id = '{{ X-Market-Id }}'
AND productGroupKeys = '{{ productGroupKeys }}'
AND includes = '{{ includes }}'
AND offset = '{{ offset }}'
AND limit = '{{ limit }}'
AND sort = '{{ sort }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_list"
    values={[
        { label: '_list', value: '_list' },
        { label: 'product_groups', value: 'product_groups' },
        { label: 'cancel', value: 'cancel' },
        { label: 'update', value: 'update' }
    ]}
>
<TabItem value="_list">

Retrieve a list of Subscriptions for the specified Shopper

```sql
EXEC godaddy.subscriptions.subscriptions._list 
@X-Shopper-Id='{{ X-Shopper-Id }}', 
@X-Market-Id='{{ X-Market-Id }}', 
@productGroupKeys='{{ productGroupKeys }}', 
@includes='{{ includes }}', 
@offset='{{ offset }}', 
@limit='{{ limit }}', 
@sort='{{ sort }}'
;
```
</TabItem>
<TabItem value="product_groups">

Retrieve a list of ProductGroups for the specified Shopper

```sql
EXEC godaddy.subscriptions.subscriptions.product_groups 
@X-Shopper-Id='{{ X-Shopper-Id }}', 
@X-Market-Id='{{ X-Market-Id }}'
;
```
</TabItem>
<TabItem value="cancel">

Cancel the specified Subscription

```sql
EXEC godaddy.subscriptions.subscriptions.cancel 
@subscription_id='{{ subscription_id }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}'
;
```
</TabItem>
<TabItem value="update">

Only Subscription properties that can be changed without immediate  financial impact can be modified via PATCH, whereas some properties  can be changed by purchasing a renewal  This endpoint only supports JWT authentication

```sql
EXEC godaddy.subscriptions.subscriptions.update 
@subscription_id='{{ subscription_id }}' --required 
@@json=
'{
"paymentProfileId": {{ paymentProfileId }}, 
"renewAuto": {{ renewAuto }}
}'
;
```
</TabItem>
</Tabs>
