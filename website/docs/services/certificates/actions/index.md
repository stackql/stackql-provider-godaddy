--- 
title: actions
hide_title: false
hide_table_of_contents: false
keywords:
  - actions
  - certificates
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

Creates, updates, deletes, gets or lists an <code>actions</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>actions</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.certificates.actions" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="certificate_action_retrieve"
    values={[
        { label: 'certificate_action_retrieve', value: 'certificate_action_retrieve' }
    ]}
>
<TabItem value="certificate_action_retrieve">

Action retrieval successful

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
    <td>Date action created</td>
</tr>
<tr>
    <td><CopyableCode code="type" /></td>
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
    <td><a href="#certificate_action_retrieve"><CopyableCode code="certificate_action_retrieve" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>This method is used to retrieve all stateful actions relating to a certificate lifecycle.</td>
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
<tr id="parameter-certificate_id">
    <td><CopyableCode code="certificate_id" /></td>
    <td><code>string</code></td>
    <td>Certificate id to register for callback</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="certificate_action_retrieve"
    values={[
        { label: 'certificate_action_retrieve', value: 'certificate_action_retrieve' }
    ]}
>
<TabItem value="certificate_action_retrieve">

This method is used to retrieve all stateful actions relating to a certificate lifecycle.

```sql
SELECT
createdAt,
type
FROM godaddy.certificates.actions
WHERE certificate_id = '{{ certificate_id }}' -- required
;
```
</TabItem>
</Tabs>
