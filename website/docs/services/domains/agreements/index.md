--- 
title: agreements
hide_title: false
hide_table_of_contents: false
keywords:
  - agreements
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

Creates, updates, deletes, gets or lists an <code>agreements</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>agreements</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.agreements" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_agreement"
    values={[
        { label: 'get_agreement', value: 'get_agreement' }
    ]}
>
<TabItem value="get_agreement">

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
    <td><a href="#get_agreement"><CopyableCode code="get_agreement" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-tlds"><code>tlds</code></a>, <a href="#parameter-privacy"><code>privacy</code></a></td>
    <td><a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a>, <a href="#parameter-forTransfer"><code>forTransfer</code></a></td>
    <td>Retrieve the legal agreement(s) required to purchase the specified TLD and add-ons</td>
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
<tr id="parameter-privacy">
    <td><CopyableCode code="privacy" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not privacy has been requested</td>
</tr>
<tr id="parameter-tlds">
    <td><CopyableCode code="tlds" /></td>
    <td><code>array</code></td>
    <td>list of TLDs whose legal agreements are to be retrieved</td>
</tr>
<tr id="parameter-X-Market-Id">
    <td><CopyableCode code="X-Market-Id" /></td>
    <td><code>string (bcp-47)</code></td>
    <td>Unique identifier of the Market used to retrieve/translate Legal Agreements</td>
</tr>
<tr id="parameter-forTransfer">
    <td><CopyableCode code="forTransfer" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not domain tranfer has been requested</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_agreement"
    values={[
        { label: 'get_agreement', value: 'get_agreement' }
    ]}
>
<TabItem value="get_agreement">

Retrieve the legal agreement(s) required to purchase the specified TLD and add-ons

```sql
SELECT
agreementKey,
content,
title,
url
FROM godaddy.domains.agreements
WHERE tlds = '{{ tlds }}' -- required
AND privacy = '{{ privacy }}' -- required
AND X-Market-Id = '{{ X-Market-Id }}'
AND forTransfer = '{{ forTransfer }}'
;
```
</TabItem>
</Tabs>
