--- 
title: purchase_schema
hide_title: false
hide_table_of_contents: false
keywords:
  - purchase_schema
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

Creates, updates, deletes, gets or lists a <code>purchase_schema</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>purchase_schema</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.purchase_schema" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="schema"
    values={[
        { label: 'schema', value: 'schema' }
    ]}
>
<TabItem value="schema">

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
    <td><CopyableCode code="id" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="models" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="properties" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="required" /></td>
    <td><code>array</code></td>
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
    <td><a href="#schema"><CopyableCode code="schema" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-tld"><code>tld</code></a></td>
    <td></td>
    <td>Retrieve the schema to be submitted when registering a Domain for the specified TLD</td>
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
<tr id="parameter-tld">
    <td><CopyableCode code="tld" /></td>
    <td><code>string</code></td>
    <td>The Top-Level Domain whose schema should be retrieved</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="schema"
    values={[
        { label: 'schema', value: 'schema' }
    ]}
>
<TabItem value="schema">

Retrieve the schema to be submitted when registering a Domain for the specified TLD

```sql
SELECT
id,
models,
properties,
required
FROM godaddy.domains.purchase_schema
WHERE tld = '{{ tld }}' -- required
;
```
</TabItem>
</Tabs>
