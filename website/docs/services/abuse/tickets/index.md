--- 
title: tickets
hide_title: false
hide_table_of_contents: false
keywords:
  - tickets
  - abuse
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

Creates, updates, deletes, gets or lists a <code>tickets</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>tickets</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.abuse.tickets" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_ticket_info"
    values={[
        { label: 'get_ticket_info', value: 'get_ticket_info' },
        { label: 'get_tickets', value: 'get_tickets' }
    ]}
>
<TabItem value="get_ticket_info">

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
    <td><CopyableCode code="closed" /></td>
    <td><code>boolean</code></td>
    <td>Is this abuse ticket closed?</td>
</tr>
<tr>
    <td><CopyableCode code="closedAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The date the abuse ticket was closed</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The date the abuse ticket was created</td>
</tr>
<tr>
    <td><CopyableCode code="domainIp" /></td>
    <td><code>string</code></td>
    <td>The domain or IP the suspected abuse was reported against</td>
</tr>
<tr>
    <td><CopyableCode code="reporter" /></td>
    <td><code>string</code></td>
    <td>The shopper id of the person who reported the suspected abuse</td>
</tr>
<tr>
    <td><CopyableCode code="source" /></td>
    <td><code>string</code></td>
    <td>The single URL or IP the suspected abuse was reported against</td>
</tr>
<tr>
    <td><CopyableCode code="target" /></td>
    <td><code>string</code></td>
    <td>The company the suspected abuse is targeting</td>
</tr>
<tr>
    <td><CopyableCode code="ticketId" /></td>
    <td><code>string</code></td>
    <td>Abuse ticket ID</td>
</tr>
<tr>
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td>The type of abuse being reported</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="get_tickets">

<table>
<thead>
    <tr>
    <th>Name</th>
    <th>Datatype</th>
    <th>Description</th>
    </tr>
</thead>
<tbody>
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
    <td><a href="#get_ticket_info"><CopyableCode code="get_ticket_info" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-ticket_id"><code>ticket_id</code></a></td>
    <td></td>
    <td>Return the abuse ticket data for a given ticket id</td>
</tr>
<tr>
    <td><a href="#get_tickets"><CopyableCode code="get_tickets" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td><a href="#parameter-type"><code>type</code></a>, <a href="#parameter-closed"><code>closed</code></a>, <a href="#parameter-sourceDomainOrIp"><code>sourceDomainOrIp</code></a>, <a href="#parameter-target"><code>target</code></a>, <a href="#parameter-createdStart"><code>createdStart</code></a>, <a href="#parameter-createdEnd"><code>createdEnd</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-offset"><code>offset</code></a></td>
    <td>List all abuse tickets ids that match user provided filters</td>
</tr>
<tr>
    <td><a href="#create_ticket"><CopyableCode code="create_ticket" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td></td>
    <td></td>
    <td>Create a new abuse ticket</td>
</tr>
<tr>
    <td><a href="#_get_tickets"><CopyableCode code="_get_tickets" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td></td>
    <td><a href="#parameter-type"><code>type</code></a>, <a href="#parameter-closed"><code>closed</code></a>, <a href="#parameter-sourceDomainOrIp"><code>sourceDomainOrIp</code></a>, <a href="#parameter-target"><code>target</code></a>, <a href="#parameter-createdStart"><code>createdStart</code></a>, <a href="#parameter-createdEnd"><code>createdEnd</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-offset"><code>offset</code></a></td>
    <td>List all abuse tickets ids that match user provided filters</td>
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
<tr id="parameter-ticket_id">
    <td><CopyableCode code="ticket_id" /></td>
    <td><code>string</code></td>
    <td>A unique abuse ticket identifier</td>
</tr>
<tr id="parameter-closed">
    <td><CopyableCode code="closed" /></td>
    <td><code>boolean</code></td>
    <td>Is this abuse ticket closed?</td>
</tr>
<tr id="parameter-createdEnd">
    <td><CopyableCode code="createdEnd" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The latest abuse ticket creation date to pull abuse tickets for</td>
</tr>
<tr id="parameter-createdStart">
    <td><CopyableCode code="createdStart" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The earliest abuse ticket creation date to pull abuse tickets for</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>integer (integer-positive)</code></td>
    <td>Number of abuse ticket numbers to return.</td>
</tr>
<tr id="parameter-offset">
    <td><CopyableCode code="offset" /></td>
    <td><code>integer (integer-positive)</code></td>
    <td>The earliest result set record number to pull abuse tickets for</td>
</tr>
<tr id="parameter-sourceDomainOrIp">
    <td><CopyableCode code="sourceDomainOrIp" /></td>
    <td><code>string (host-name-or-ip-address)</code></td>
    <td>The domain name or ip address abuse originated from</td>
</tr>
<tr id="parameter-target">
    <td><CopyableCode code="target" /></td>
    <td><code>string</code></td>
    <td>The brand/company the abuse is targeting. ie: brand name/bank name</td>
</tr>
<tr id="parameter-type">
    <td><CopyableCode code="type" /></td>
    <td><code>string</code></td>
    <td>The type of abuse.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_ticket_info"
    values={[
        { label: 'get_ticket_info', value: 'get_ticket_info' },
        { label: 'get_tickets', value: 'get_tickets' }
    ]}
>
<TabItem value="get_ticket_info">

Return the abuse ticket data for a given ticket id

```sql
SELECT
closed,
closedAt,
createdAt,
domainIp,
reporter,
source,
target,
ticketId,
type
FROM godaddy.abuse.tickets
WHERE ticket_id = '{{ ticket_id }}' -- required
;
```
</TabItem>
<TabItem value="get_tickets">

List all abuse tickets ids that match user provided filters

```sql
SELECT
*
FROM godaddy.abuse.tickets
WHERE type = '{{ type }}'
AND closed = '{{ closed }}'
AND sourceDomainOrIp = '{{ sourceDomainOrIp }}'
AND target = '{{ target }}'
AND createdStart = '{{ createdStart }}'
AND createdEnd = '{{ createdEnd }}'
AND limit = '{{ limit }}'
AND offset = '{{ offset }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_ticket"
    values={[
        { label: 'create_ticket', value: 'create_ticket' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_ticket">

Create a new abuse ticket

```sql
INSERT INTO godaddy.abuse.tickets (
data__info,
data__infoUrl,
data__intentional,
data__proxy,
data__source,
data__target,
data__type
)
SELECT 
'{{ info }}',
'{{ infoUrl }}',
{{ intentional }},
'{{ proxy }}',
'{{ source }}',
'{{ target }}',
'{{ type }}'
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: tickets
  props:
    - name: info
      value: string
      description: |
        Additional information that may assist the abuse investigator. ie: server logs or email headers/body for SPAM
    - name: infoUrl
      value: string
      description: |
        Reporter URL if housing additional information that may assist the abuse investigator
    - name: intentional
      value: boolean
      description: |
        Do you believe this is intentional abuse by the domain holder?
      default: false
    - name: proxy
      value: string
      description: |
        The Proxy information required to view the abuse being reported. ie: Specific IP used, or country of IP viewing from
    - name: source
      value: string
      description: |
        The URL or IP where live abuse content is located at. ie: https://www.example.com/bad_stuff/bad.php
    - name: target
      value: string
      description: |
        The brand/company the abuse is targeting. ie: brand name/bank name
    - name: type
      value: string
      description: |
        The type of abuse being reported.
      valid_values: ['A_RECORD', 'CHILD_ABUSE', 'CONTENT', 'FRAUD_WIRE', 'IP_BLOCK', 'MALWARE', 'NETWORK_ABUSE', 'PHISHING', 'SPAM']
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="_get_tickets"
    values={[
        { label: '_get_tickets', value: '_get_tickets' }
    ]}
>
<TabItem value="_get_tickets">

List all abuse tickets ids that match user provided filters

```sql
EXEC godaddy.abuse.tickets._get_tickets 
@type='{{ type }}', 
@closed={{ closed }}, 
@sourceDomainOrIp='{{ sourceDomainOrIp }}', 
@target='{{ target }}', 
@createdStart='{{ createdStart }}', 
@createdEnd='{{ createdEnd }}', 
@limit='{{ limit }}', 
@offset='{{ offset }}'
;
```
</TabItem>
</Tabs>
