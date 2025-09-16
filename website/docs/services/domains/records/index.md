--- 
title: records
hide_title: false
hide_table_of_contents: false
keywords:
  - records
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

Creates, updates, deletes, gets or lists a <code>records</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>records</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.records" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="record_get"
    values={[
        { label: 'record_get', value: 'record_get' }
    ]}
>
<TabItem value="record_get">

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
    <td><CopyableCode code="name" /></td>
    <td><code>string (domain)</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="data" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="port" /></td>
    <td><code>integer</code></td>
    <td>Service port (SRV only)</td>
</tr>
<tr>
    <td><CopyableCode code="priority" /></td>
    <td><code>integer (integer-positive)</code></td>
    <td>Record priority (MX and SRV only)</td>
</tr>
<tr>
    <td><CopyableCode code="protocol" /></td>
    <td><code>string</code></td>
    <td>Service protocol (SRV only)</td>
</tr>
<tr>
    <td><CopyableCode code="service" /></td>
    <td><code>string</code></td>
    <td>Service type (SRV only)</td>
</tr>
<tr>
    <td><CopyableCode code="ttl" /></td>
    <td><code>integer (integer-positive)</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="weight" /></td>
    <td><code>integer (integer-positive)</code></td>
    <td>Record weight (SRV only)</td>
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
    <td><a href="#record_get"><CopyableCode code="record_get" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-type"><code>type</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-offset"><code>offset</code></a>, <a href="#parameter-limit"><code>limit</code></a></td>
    <td>Retrieve DNS Records for the specified Domain, optionally with the specified Type and/or Name</td>
</tr>
<tr>
    <td><a href="#record_add"><CopyableCode code="record_add" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Add the specified DNS Records to the specified Domain</td>
</tr>
<tr>
    <td><a href="#record_replace"><CopyableCode code="record_replace" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Replace all DNS Records for the specified Domain</td>
</tr>
<tr>
    <td><a href="#record_replace_type"><CopyableCode code="record_replace_type" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-type"><code>type</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Replace all DNS Records for the specified Domain with the specified Type</td>
</tr>
<tr>
    <td><a href="#record_replace_type_name"><CopyableCode code="record_replace_type_name" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-type"><code>type</code></a>, <a href="#parameter-name"><code>name</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Replace all DNS Records for the specified Domain with the specified Type and Name</td>
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
    <td>Domain whose DNS Records are to be replaced</td>
</tr>
<tr id="parameter-name">
    <td><CopyableCode code="name" /></td>
    <td><code>string</code></td>
    <td>DNS Record Name for which DNS Records are to be replaced</td>
</tr>
<tr id="parameter-type">
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td>DNS Record Type for which DNS Records are to be replaced</td>
</tr>
<tr id="parameter-X-Shopper-Id">
    <td><CopyableCode code="X-Shopper-Id" /></td>
    <td><code>string</code></td>
    <td>Shopper ID which owns the domain. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com</td>
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
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="record_get"
    values={[
        { label: 'record_get', value: 'record_get' }
    ]}
>
<TabItem value="record_get">

Retrieve DNS Records for the specified Domain, optionally with the specified Type and/or Name

```sql
SELECT
name,
data,
port,
priority,
protocol,
service,
ttl,
type,
weight
FROM godaddy.domains.records
WHERE domain = '{{ domain }}' -- required
AND type = '{{ type }}' -- required
AND X-Shopper-Id = '{{ X-Shopper-Id }}'
AND offset = '{{ offset }}'
AND limit = '{{ limit }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="record_add"
    values={[
        { label: 'record_add', value: 'record_add' },
        { label: 'record_replace', value: 'record_replace' },
        { label: 'record_replace_type', value: 'record_replace_type' },
        { label: 'record_replace_type_name', value: 'record_replace_type_name' }
    ]}
>
<TabItem value="record_add">

Add the specified DNS Records to the specified Domain

```sql
EXEC godaddy.domains.records.record_add 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}'
;
```
</TabItem>
<TabItem value="record_replace">

Replace all DNS Records for the specified Domain

```sql
EXEC godaddy.domains.records.record_replace 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}'
;
```
</TabItem>
<TabItem value="record_replace_type">

Replace all DNS Records for the specified Domain with the specified Type

```sql
EXEC godaddy.domains.records.record_replace_type 
@domain='{{ domain }}' --required, 
@type='{{ type }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}'
;
```
</TabItem>
<TabItem value="record_replace_type_name">

Replace all DNS Records for the specified Domain with the specified Type and Name

```sql
EXEC godaddy.domains.records.record_replace_type_name 
@domain='{{ domain }}' --required, 
@type='{{ type }}' --required, 
@name='{{ name }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}'
;
```
</TabItem>
</Tabs>
