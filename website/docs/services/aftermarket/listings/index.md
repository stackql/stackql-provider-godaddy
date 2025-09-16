--- 
title: listings
hide_title: false
hide_table_of_contents: false
keywords:
  - listings
  - aftermarket
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

Creates, updates, deletes, gets or lists a <code>listings</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>listings</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.aftermarket.listings" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

`SELECT` not supported for this resource, use `SHOW METHODS` to view available operations for the resource.


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
    <td><a href="#delete_listings"><CopyableCode code="delete_listings" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-domains"><code>domains</code></a></td>
    <td></td>
    <td>Remove listings from GoDaddy Auction</td>
</tr>
<tr>
    <td><a href="#add_expiry_listings"><CopyableCode code="add_expiry_listings" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td></td>
    <td>Add expiry listings into GoDaddy Auction</td>
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
<tr id="parameter-domains">
    <td><CopyableCode code="domains" /></td>
    <td><code>array</code></td>
    <td>A comma separated list of domain names</td>
</tr>
</tbody>
</table>

## `DELETE` examples

<Tabs
    defaultValue="delete_listings"
    values={[
        { label: 'delete_listings', value: 'delete_listings' }
    ]}
>
<TabItem value="delete_listings">

Remove listings from GoDaddy Auction

```sql
DELETE FROM godaddy.aftermarket.listings
WHERE domains = '{{ domains }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="add_expiry_listings"
    values={[
        { label: 'add_expiry_listings', value: 'add_expiry_listings' }
    ]}
>
<TabItem value="add_expiry_listings">

Add expiry listings into GoDaddy Auction

```sql
EXEC godaddy.aftermarket.listings.add_expiry_listings 

;
```
</TabItem>
</Tabs>
