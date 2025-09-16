--- 
title: callback
hide_title: false
hide_table_of_contents: false
keywords:
  - callback
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

Creates, updates, deletes, gets or lists a <code>callback</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>callback</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.certificates.callback" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="certificate_callback_get"
    values={[
        { label: 'certificate_callback_get', value: 'certificate_callback_get' }
    ]}
>
<TabItem value="certificate_callback_get">

Callback registered

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
    <td><CopyableCode code="callbackUrl" /></td>
    <td><code>string</code></td>
    <td>Callback url registered to receive stateful actions</td>
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
    <td><a href="#certificate_callback_get"><CopyableCode code="certificate_callback_get" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>This method is used to retrieve the registered callback url for a certificate.</td>
</tr>
<tr>
    <td><a href="#certificate_callback_delete"><CopyableCode code="certificate_callback_delete" /></a></td>
    <td><CopyableCode code="delete" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>Unregister the callback for a particular certificate.</td>
</tr>
<tr>
    <td><a href="#certificate_callback_replace"><CopyableCode code="certificate_callback_replace" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a>, <a href="#parameter-callbackUrl"><code>callbackUrl</code></a></td>
    <td></td>
    <td>This method is used to register/replace url for callbacks for stateful actions relating to a certificate lifecycle. The callback url is a Webhook style pattern and will receive POST http requests with json body defined in the CertificateAction model definition for each certificate action.  Only one callback URL is allowed to be registered for each certificateId, so it will replace a previous registration.</td>
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
<tr id="parameter-callbackUrl">
    <td><CopyableCode code="callbackUrl" /></td>
    <td><code>string</code></td>
    <td>Callback url registered/replaced to receive stateful actions</td>
</tr>
<tr id="parameter-certificate_id">
    <td><CopyableCode code="certificate_id" /></td>
    <td><code>string</code></td>
    <td>Certificate id to register/replace for callback</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="certificate_callback_get"
    values={[
        { label: 'certificate_callback_get', value: 'certificate_callback_get' }
    ]}
>
<TabItem value="certificate_callback_get">

This method is used to retrieve the registered callback url for a certificate.

```sql
SELECT
callbackUrl
FROM godaddy.certificates.callback
WHERE certificate_id = '{{ certificate_id }}' -- required
;
```
</TabItem>
</Tabs>


## `DELETE` examples

<Tabs
    defaultValue="certificate_callback_delete"
    values={[
        { label: 'certificate_callback_delete', value: 'certificate_callback_delete' }
    ]}
>
<TabItem value="certificate_callback_delete">

Unregister the callback for a particular certificate.

```sql
DELETE FROM godaddy.certificates.callback
WHERE certificate_id = '{{ certificate_id }}' --required
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="certificate_callback_replace"
    values={[
        { label: 'certificate_callback_replace', value: 'certificate_callback_replace' }
    ]}
>
<TabItem value="certificate_callback_replace">

This method is used to register/replace url for callbacks for stateful actions relating to a certificate lifecycle. The callback url is a Webhook style pattern and will receive POST http requests with json body defined in the CertificateAction model definition for each certificate action.  Only one callback URL is allowed to be registered for each certificateId, so it will replace a previous registration.

```sql
EXEC godaddy.certificates.callback.certificate_callback_replace 
@certificate_id='{{ certificate_id }}' --required, 
@callbackUrl='{{ callbackUrl }}' --required
;
```
</TabItem>
</Tabs>
