--- 
title: orders
hide_title: false
hide_table_of_contents: false
keywords:
  - orders
  - orders
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

Creates, updates, deletes, gets or lists an <code>orders</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>orders</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.orders.orders" /></td></tr>
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
    <td><CopyableCode code="billTo" /></td>
    <td><code>object</code></td>
    <td>The billing contact information that was used at the time of purchase</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>Date and time when the current order is created on</td>
</tr>
<tr>
    <td><CopyableCode code="currency" /></td>
    <td><code>string (iso-currency-code)</code></td>
    <td>Currency in which the order has been placed</td>
</tr>
<tr>
    <td><CopyableCode code="items" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="orderId" /></td>
    <td><code>string</code></td>
    <td>Unique identifier of current order</td>
</tr>
<tr>
    <td><CopyableCode code="parentOrderId" /></td>
    <td><code>string</code></td>
    <td>Unique identifier of the parent order. All refund/chargeback orders are tied to the original order. The orginal order's `orderId` is the `parentOrderId` of refund/chargeback orders</td>
</tr>
<tr>
    <td><CopyableCode code="payments" /></td>
    <td><code>array</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="pricing" /></td>
    <td><code>object</code></td>
    <td>Pricing information for current order</td>
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
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>Date and time when the current order was created</td>
</tr>
<tr>
    <td><CopyableCode code="currency" /></td>
    <td><code>string (iso-currency-code)</code></td>
    <td>Currency in which the order was placed</td>
</tr>
<tr>
    <td><CopyableCode code="items" /></td>
    <td><code>array</code></td>
    <td>Sets of two or more line items in current order</td>
</tr>
<tr>
    <td><CopyableCode code="orderId" /></td>
    <td><code>integer</code></td>
    <td>Unique identifier of the current order</td>
</tr>
<tr>
    <td><CopyableCode code="parentOrderId" /></td>
    <td><code>string</code></td>
    <td>Unique identifier of the parent order. All refund/chargeback orders are tied to the original order. The orginal order's `orderId` is the `parentOrderId` of refund/chargeback orders</td>
</tr>
<tr>
    <td><CopyableCode code="pricing" /></td>
    <td><code>object</code></td>
    <td>Pricing information of the current order</td>
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
    <td><a href="#parameter-order_id"><code>order_id</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>API ResellersThis endpoint does not support subaccounts and therefore API Resellers should not supply an X-Shopper-Id header</td>
</tr>
<tr>
    <td><a href="#list"><CopyableCode code="list" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td><a href="#parameter-periodStart"><code>periodStart</code></a>, <a href="#parameter-periodEnd"><code>periodEnd</code></a>, <a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-productGroupId"><code>productGroupId</code></a>, <a href="#parameter-paymentProfileId"><code>paymentProfileId</code></a>, <a href="#parameter-parentOrderId"><code>parentOrderId</code></a>, <a href="#parameter-offset"><code>offset</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-sort"><code>sort</code></a>, <a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>API ResellersThis endpoint does not support subaccounts and therefore API Resellers should not supply an X-Shopper-Id header</td>
</tr>
<tr>
    <td><a href="#_list"><CopyableCode code="_list" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td><a href="#parameter-periodStart"><code>periodStart</code></a>, <a href="#parameter-periodEnd"><code>periodEnd</code></a>, <a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-productGroupId"><code>productGroupId</code></a>, <a href="#parameter-paymentProfileId"><code>paymentProfileId</code></a>, <a href="#parameter-parentOrderId"><code>parentOrderId</code></a>, <a href="#parameter-offset"><code>offset</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-sort"><code>sort</code></a>, <a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>API ResellersThis endpoint does not support subaccounts and therefore API Resellers should not supply an X-Shopper-Id header</td>
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
<tr id="parameter-order_id">
    <td><CopyableCode code="order_id" /></td>
    <td><code>string</code></td>
    <td>Order id whose details are to be retrieved</td>
</tr>
<tr id="parameter-X-Market-Id">
    <td><CopyableCode code="X-Market-Id" /></td>
    <td><code>string</code></td>
    <td>Unique identifier of the Market in which the request is happening</td>
</tr>
<tr id="parameter-X-Shopper-Id">
    <td><CopyableCode code="X-Shopper-Id" /></td>
    <td><code>string</code></td>
    <td>Shopper ID to be operated on, if different from JWTReseller subaccounts are not supported</td>
</tr>
<tr id="parameter-domain">
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>Domain name to use as the filter of results</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>integer</code></td>
    <td>Maximum number of items to return</td>
</tr>
<tr id="parameter-offset">
    <td><CopyableCode code="offset" /></td>
    <td><code>integer</code></td>
    <td>Number of results to skip for pagination</td>
</tr>
<tr id="parameter-parentOrderId">
    <td><CopyableCode code="parentOrderId" /></td>
    <td><code>string</code></td>
    <td>Parent order id to use as the filter of results</td>
</tr>
<tr id="parameter-paymentProfileId">
    <td><CopyableCode code="paymentProfileId" /></td>
    <td><code>integer</code></td>
    <td>Payment profile id to use as the filter of results</td>
</tr>
<tr id="parameter-periodEnd">
    <td><CopyableCode code="periodEnd" /></td>
    <td><code>string</code></td>
    <td>End of range indicating what time-frame should be returned. Inclusive</td>
</tr>
<tr id="parameter-periodStart">
    <td><CopyableCode code="periodStart" /></td>
    <td><code>string</code></td>
    <td>Start of range indicating what time-frame should be returned. Inclusive</td>
</tr>
<tr id="parameter-productGroupId">
    <td><CopyableCode code="productGroupId" /></td>
    <td><code>integer</code></td>
    <td>Product group id to use as the filter of results</td>
</tr>
<tr id="parameter-sort">
    <td><CopyableCode code="sort" /></td>
    <td><code>string</code></td>
    <td>Property name that will be used to sort results. '-' indicates descending</td>
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

API ResellersThis endpoint does not support subaccounts and therefore API Resellers should not supply an X-Shopper-Id header

```sql
SELECT
billTo,
createdAt,
currency,
items,
orderId,
parentOrderId,
payments,
pricing
FROM godaddy.orders.orders
WHERE order_id = '{{ order_id }}' -- required
AND X-Shopper-Id = '{{ X-Shopper-Id }}'
AND X-Market-Id = '{{ X-Market-Id }}'
;
```
</TabItem>
<TabItem value="list">

API ResellersThis endpoint does not support subaccounts and therefore API Resellers should not supply an X-Shopper-Id header

```sql
SELECT
createdAt,
currency,
items,
orderId,
parentOrderId,
pricing
FROM godaddy.orders.orders
WHERE periodStart = '{{ periodStart }}'
AND periodEnd = '{{ periodEnd }}'
AND domain = '{{ domain }}'
AND productGroupId = '{{ productGroupId }}'
AND paymentProfileId = '{{ paymentProfileId }}'
AND parentOrderId = '{{ parentOrderId }}'
AND offset = '{{ offset }}'
AND limit = '{{ limit }}'
AND sort = '{{ sort }}'
AND X-Shopper-Id = '{{ X-Shopper-Id }}'
AND X-Market-Id = '{{ X-Market-Id }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_list"
    values={[
        { label: '_list', value: '_list' }
    ]}
>
<TabItem value="_list">

API ResellersThis endpoint does not support subaccounts and therefore API Resellers should not supply an X-Shopper-Id header

```sql
EXEC godaddy.orders.orders._list 
@periodStart='{{ periodStart }}', 
@periodEnd='{{ periodEnd }}', 
@domain='{{ domain }}', 
@productGroupId='{{ productGroupId }}', 
@paymentProfileId='{{ paymentProfileId }}', 
@parentOrderId='{{ parentOrderId }}', 
@offset='{{ offset }}', 
@limit='{{ limit }}', 
@sort='{{ sort }}', 
@X-Shopper-Id='{{ X-Shopper-Id }}', 
@X-Market-Id='{{ X-Market-Id }}'
;
```
</TabItem>
</Tabs>
