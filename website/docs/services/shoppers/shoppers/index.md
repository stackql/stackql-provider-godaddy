--- 
title: shoppers
hide_title: false
hide_table_of_contents: false
keywords:
  - shoppers
  - shoppers
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

Creates, updates, deletes, gets or lists a <code>shoppers</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>shoppers</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.shoppers.shoppers" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get"
    values={[
        { label: 'get', value: 'get' }
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
    <td><CopyableCode code="email" /></td>
    <td><code>string (email)</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="externalId" /></td>
    <td><code>integer</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="marketId" /></td>
    <td><code>string (bcp-47)</code></td>
    <td> (default: en-US)</td>
</tr>
<tr>
    <td><CopyableCode code="nameFirst" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="nameLast" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="shopperId" /></td>
    <td><code>string</code></td>
    <td></td>
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
    <td><a href="#parameter-shopper_id"><code>shopper_id</code></a></td>
    <td></td>
    <td>Get details for the specified Shopper</td>
</tr>
<tr>
    <td><a href="#create_subaccount"><CopyableCode code="create_subaccount" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-data__email"><code>data__email</code></a>, <a href="#parameter-data__password"><code>data__password</code></a>, <a href="#parameter-data__nameFirst"><code>data__nameFirst</code></a>, <a href="#parameter-data__nameLast"><code>data__nameLast</code></a></td>
    <td></td>
    <td>Create a Subaccount owned by the authenticated Reseller</td>
</tr>
<tr>
    <td><a href="#update"><CopyableCode code="update" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-shopper_id"><code>shopper_id</code></a></td>
    <td></td>
    <td>Update details for the specified Shopper</td>
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
<tr id="parameter-shopper_id">
    <td><CopyableCode code="shopper_id" /></td>
    <td><code>string</code></td>
    <td>The ID of the Shopper to update</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get"
    values={[
        { label: 'get', value: 'get' }
    ]}
>
<TabItem value="get">

Get details for the specified Shopper

```sql
SELECT
email,
externalId,
marketId,
nameFirst,
nameLast,
shopperId
FROM godaddy.shoppers.shoppers
WHERE shopper_id = '{{ shopper_id }}' -- required
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_subaccount"
    values={[
        { label: 'create_subaccount', value: 'create_subaccount' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_subaccount">

Create a Subaccount owned by the authenticated Reseller

```sql
INSERT INTO godaddy.shoppers.shoppers (
data__email,
data__externalId,
data__marketId,
data__nameFirst,
data__nameLast,
data__password
)
SELECT 
'{{ email }}' /* required */,
{{ externalId }},
'{{ marketId }}',
'{{ nameFirst }}' /* required */,
'{{ nameLast }}' /* required */,
'{{ password }}' /* required */
RETURNING
customerId,
shopperId
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: shoppers
  props:
    - name: email
      value: string
    - name: externalId
      value: integer
    - name: marketId
      value: string
      default: en-US
    - name: nameFirst
      value: string
    - name: nameLast
      value: string
    - name: password
      value: string
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="update"
    values={[
        { label: 'update', value: 'update' }
    ]}
>
<TabItem value="update">

Update details for the specified Shopper

```sql
EXEC godaddy.shoppers.shoppers.update 
@shopper_id='{{ shopper_id }}' --required 
@@json=
'{
"email": "{{ email }}", 
"externalId": {{ externalId }}, 
"marketId": "{{ marketId }}", 
"nameFirst": "{{ nameFirst }}", 
"nameLast": "{{ nameLast }}"
}'
;
```
</TabItem>
</Tabs>
