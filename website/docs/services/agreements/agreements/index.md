--- 
title: agreements
hide_title: false
hide_table_of_contents: false
keywords:
  - agreements
  - agreements
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

Creates, updates, deletes, gets or lists an <code>agreements</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>agreements</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.agreements.agreements" /></td></tr>
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
    <td><CopyableCode code="agreementKey" /></td>
    <td><code>string</code></td>
    <td>Unique identifier for the legal agreement</td>
</tr>
<tr>
    <td><CopyableCode code="content" /></td>
    <td><code>string</code></td>
    <td>Contents of the legal agreement, suitable for embedding</td>
</tr>
<tr>
    <td><CopyableCode code="title" /></td>
    <td><code>string</code></td>
    <td>Title of the legal agreement</td>
</tr>
<tr>
    <td><CopyableCode code="url" /></td>
    <td><code>string (url)</code></td>
    <td>URL to a page containing the legal agreement</td>
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
    <td><a href="#parameter-keys"><code>keys</code></a></td>
    <td><a href="#parameter-X-Private-Label-Id"><code>X-Private-Label-Id</code></a>, <a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>Retrieve Legal Agreements for provided agreements keys</td>
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
<tr id="parameter-keys">
    <td><CopyableCode code="keys" /></td>
    <td><code>array</code></td>
    <td>Keys for Agreements whose details are to be retrieved</td>
</tr>
<tr id="parameter-X-Market-Id">
    <td><CopyableCode code="X-Market-Id" /></td>
    <td><code>string (bcp-47)</code></td>
    <td>Unique identifier of the Market used to retrieve/translate Legal Agreements</td>
</tr>
<tr id="parameter-X-Private-Label-Id">
    <td><CopyableCode code="X-Private-Label-Id" /></td>
    <td><code>integer</code></td>
    <td>PrivateLabelId to operate as, if different from JWT</td>
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

Retrieve Legal Agreements for provided agreements keys

```sql
SELECT
agreementKey,
content,
title,
url
FROM godaddy.agreements.agreements
WHERE keys = '{{ keys }}' -- required
AND X-Private-Label-Id = '{{ X-Private-Label-Id }}'
AND X-Market-Id = '{{ X-Market-Id }}'
;
```
</TabItem>
</Tabs>
