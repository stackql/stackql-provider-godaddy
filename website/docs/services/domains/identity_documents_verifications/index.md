--- 
title: identity_documents_verifications
hide_title: false
hide_table_of_contents: false
keywords:
  - identity_documents_verifications
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

Creates, updates, deletes, gets or lists an <code>identity_documents_verifications</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>identity_documents_verifications</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.identity_documents_verifications" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get_identity_document_verification"
    values={[
        { label: 'get_identity_document_verification', value: 'get_identity_document_verification' }
    ]}
>
<TabItem value="get_identity_document_verification">

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
    <td>Timestamp indicating when the user created the identity document verification job</td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="tld" /></td>
    <td><code>string</code></td>
    <td>Top level domain the current identity document verification is for</td>
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
    <td><a href="#get_identity_document_verification"><CopyableCode code="get_identity_document_verification" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-identity_document_id"><code>identity_document_id</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-tlds"><code>tlds</code></a></td>
    <td>Retrieve a list of Verifications for the specified Identity Document</td>
</tr>
<tr>
    <td><a href="#create_verification"><CopyableCode code="create_verification" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-identity_document_id"><code>identity_document_id</code></a>, <a href="#parameter-tlds"><code>tlds</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Only one verification job is needed for one TLD, Top Level Domain, per identity document. Sending in request(s) with multiple domains for the same TLD, will not create multiple verification jobs. We accept domain names for the convenience of our customers so that they don't need to worry about parsing TLDs out of domain names</td>
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
<tr id="parameter-identity_document_id">
    <td><CopyableCode code="identity_document_id" /></td>
    <td><code>string</code></td>
    <td>Unique id of an identity document</td>
</tr>
<tr id="parameter-tlds">
    <td><CopyableCode code="tlds" /></td>
    <td><code>array</code></td>
    <td>An array of TLDs for which the verification was started. Alternately you can specify the whole domain from which the TLD will be extracted</td>
</tr>
<tr id="parameter-X-Shopper-Id">
    <td><CopyableCode code="X-Shopper-Id" /></td>
    <td><code>string</code></td>
    <td>Shopper ID of the owner of the identity document. This is only required if you are a Reseller managing identity documents for your customers. Use this header to pass in their subaccount ID</td>
</tr>
<tr id="parameter-tlds">
    <td><CopyableCode code="tlds" /></td>
    <td><code>array</code></td>
    <td>An array of TLDs for which to retrieve identity document verification jobs. Alternately you can specify the whole domain from which the TLD will be extracted</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get_identity_document_verification"
    values={[
        { label: 'get_identity_document_verification', value: 'get_identity_document_verification' }
    ]}
>
<TabItem value="get_identity_document_verification">

Retrieve a list of Verifications for the specified Identity Document

```sql
SELECT
createdAt,
status,
tld
FROM godaddy.domains.identity_documents_verifications
WHERE identity_document_id = '{{ identity_document_id }}' -- required
AND X-Shopper-Id = '{{ X-Shopper-Id }}'
AND tlds = '{{ tlds }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_verification"
    values={[
        { label: 'create_verification', value: 'create_verification' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_verification">

Only one verification job is needed for one TLD, Top Level Domain, per identity document. Sending in request(s) with multiple domains for the same TLD, will not create multiple verification jobs. We accept domain names for the convenience of our customers so that they don't need to worry about parsing TLDs out of domain names

```sql
INSERT INTO godaddy.domains.identity_documents_verifications (
identity_document_id,
tlds,
X-Shopper-Id
)
SELECT 
'{{ identity_document_id }}',
'{{ tlds }}',
'{{ X-Shopper-Id }}'
RETURNING
createdAt,
status,
tld
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: identity_documents_verifications
  props:
    - name: identity_document_id
      value: string
      description: Required parameter for the identity_documents_verifications resource.
    - name: tlds
      value: array
      description: Required parameter for the identity_documents_verifications resource.
    - name: X-Shopper-Id
      value: string
      description: Shopper ID of the owner of the identity document. This is only required if you are a Reseller managing identity documents for your customers. Use this header to pass in their subaccount ID
```
</TabItem>
</Tabs>
