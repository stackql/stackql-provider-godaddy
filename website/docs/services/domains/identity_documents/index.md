--- 
title: identity_documents
hide_title: false
hide_table_of_contents: false
keywords:
  - identity_documents
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

Creates, updates, deletes, gets or lists an <code>identity_documents</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>identity_documents</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.identity_documents" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="list_identity_documents"
    values={[
        { label: 'list_identity_documents', value: 'list_identity_documents' }
    ]}
>
<TabItem value="list_identity_documents">

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
    <td><CopyableCode code="contact" /></td>
    <td><code>object</code></td>
    <td></td>
</tr>
<tr>
    <td><CopyableCode code="identificationCountry" /></td>
    <td><code>string (iso-country-code)</code></td>
    <td>Two-letter ISO country code to be used as a hint for target region NOTE: These are sample values, there are many  more </td>
</tr>
<tr>
    <td><CopyableCode code="identificationNumber" /></td>
    <td><code>string</code></td>
    <td>Individual or business identification number written on the document. Must match image exactly</td>
</tr>
<tr>
    <td><CopyableCode code="identificationType" /></td>
    <td><code>string</code></td>
    <td>Type of the identity document</td>
</tr>
<tr>
    <td><CopyableCode code="identityDocumentId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of an identity document</td>
</tr>
<tr>
    <td><CopyableCode code="legalEntityName" /></td>
    <td><code>string</code></td>
    <td>Individual or business name written on the document. Must match image exactly</td>
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
    <td><a href="#list_identity_documents"><CopyableCode code="list_identity_documents" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Get a collection of identity documents the current shopper owns</td>
</tr>
<tr>
    <td><a href="#create_identity_document"><CopyableCode code="create_identity_document" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-data__contact"><code>data__contact</code></a>, <a href="#parameter-data__identificationCountry"><code>data__identificationCountry</code></a>, <a href="#parameter-data__identificationNumber"><code>data__identificationNumber</code></a>, <a href="#parameter-data__identificationType"><code>data__identificationType</code></a>, <a href="#parameter-data__image"><code>data__image</code></a>, <a href="#parameter-data__legalEntityName"><code>data__legalEntityName</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Create an Identity Document from uploaded image</td>
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
<tr id="parameter-X-Shopper-Id">
    <td><CopyableCode code="X-Shopper-Id" /></td>
    <td><code>string</code></td>
    <td>Shopper ID of the owner of the identity document. This is only required if you are a Reseller managing identity documents for your customers. Use this header to pass in their subaccount ID</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="list_identity_documents"
    values={[
        { label: 'list_identity_documents', value: 'list_identity_documents' }
    ]}
>
<TabItem value="list_identity_documents">

Get a collection of identity documents the current shopper owns

```sql
SELECT
contact,
identificationCountry,
identificationNumber,
identificationType,
identityDocumentId,
legalEntityName
FROM godaddy.domains.identity_documents
WHERE X-Shopper-Id = '{{ X-Shopper-Id }}'
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="create_identity_document"
    values={[
        { label: 'create_identity_document', value: 'create_identity_document' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="create_identity_document">

Create an Identity Document from uploaded image

```sql
INSERT INTO godaddy.domains.identity_documents (
data__contact,
data__identificationCountry,
data__identificationNumber,
data__identificationType,
data__image,
data__legalEntityName,
X-Shopper-Id
)
SELECT 
'{{ contact }}' /* required */,
'{{ identificationCountry }}' /* required */,
'{{ identificationNumber }}' /* required */,
'{{ identificationType }}' /* required */,
'{{ image }}' /* required */,
'{{ legalEntityName }}' /* required */,
'{{ X-Shopper-Id }}'
RETURNING
identityDocumentId
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: identity_documents
  props:
    - name: contact
      value: object
    - name: identificationCountry
      value: string
      description: |
        Two-letter ISO country code to be used as a hint for target region NOTE: These are sample values, there are many  more
      valid_values: ['AD', 'AE', 'AF', 'AG', 'AI', 'AL', 'AM', 'AO', 'AQ', 'AR', 'AS', 'AT', 'AU', 'AW', 'AX', 'AZ', 'BA', 'BB', 'BD', 'BE', 'BF', 'BG', 'BH', 'BI', 'BJ', 'BL', 'BM', 'BN', 'BO', 'BQ', 'BR', 'BS', 'BT', 'BV', 'BW', 'BY', 'BZ', 'CA', 'CC', 'CD', 'CF', 'CG', 'CH', 'CI', 'CK', 'CL', 'CM', 'CN', 'CO', 'CR', 'CU', 'CV', 'CW', 'CX', 'CY', 'CZ', 'DE', 'DJ', 'DK', 'DM', 'DO', 'DZ', 'EC', 'EE', 'EG', 'EH', 'ER', 'ES', 'ET', 'FI', 'FJ', 'FK', 'FM', 'FO', 'FR', 'GA', 'GB', 'GD', 'GE', 'GF', 'GG', 'GH', 'GI', 'GL', 'GM', 'GN', 'GP', 'GQ', 'GR', 'GS', 'GT', 'GU', 'GW', 'GY', 'HK', 'HM', 'HN', 'HR', 'HT', 'HU', 'ID', 'IE', 'IL', 'IM', 'IN', 'IO', 'IQ', 'IR', 'IS', 'IT', 'JE', 'JM', 'JO', 'JP', 'KE', 'KG', 'KH', 'KI', 'KM', 'KN', 'KP', 'KR', 'KW', 'KY', 'KZ', 'LA', 'LB', 'LC', 'LI', 'LK', 'LR', 'LS', 'LT', 'LU', 'LV', 'LY', 'MA', 'MC', 'MD', 'ME', 'MF', 'MG', 'MH', 'MK', 'ML', 'MM', 'MN', 'MO', 'MP', 'MQ', 'MR', 'MS', 'MT', 'MU', 'MV', 'MW', 'MX', 'MY', 'MZ', 'NA', 'NC', 'NE', 'NF', 'NG', 'NI', 'NL', 'NO', 'NP', 'NR', 'NU', 'NZ', 'OM', 'PA', 'PE', 'PF', 'PG', 'PH', 'PK', 'PL', 'PM', 'PN', 'PR', 'PS', 'PT', 'PW', 'PY', 'QA', 'RE', 'RO', 'RS', 'RU', 'RW', 'SA', 'SB', 'SC', 'SD', 'SE', 'SG', 'SH', 'SI', 'SJ', 'SK', 'SL', 'SM', 'SN', 'SO', 'SR', 'SS', 'ST', 'SV', 'SX', 'SY', 'SZ', 'TC', 'TD', 'TF', 'TG', 'TH', 'TJ', 'TK', 'TL', 'TM', 'TN', 'TO', 'TR', 'TT', 'TV', 'TW', 'TZ', 'UA', 'UG', 'UM', 'US', 'UY', 'UZ', 'VA', 'VC', 'VE', 'VG', 'VI', 'VN', 'VU', 'WF', 'WS', 'YE', 'YT', 'ZA', 'ZM', 'ZW']
    - name: identificationNumber
      value: string
      description: |
        Individual or business identification number written on the document. Must match image exactly
    - name: identificationType
      value: string
      description: |
        Type of the identity document
      valid_values: ['BUSINESS_LICENSE', 'DRIVERS_LICENSE', 'ORGANIZATION_CODE_CERTIFICATE', 'PASSPORT', 'RESIDENT_ID', 'RESIDENT_ID_TEMPORARY']
    - name: image
      value: string
      description: |
        The base64 encoded string of the document image. The document image size must be between 4KB and 10MB. Supported formats are bmp, jpg/jpeg, jfif, png, gif, and tiff
    - name: legalEntityName
      value: string
      description: |
        Individual or business name written on the document. Must match image exactly
    - name: X-Shopper-Id
      value: string
      description: Shopper ID of the owner of the identity document. This is only required if you are a Reseller managing identity documents for your customers. Use this header to pass in their subaccount ID
```
</TabItem>
</Tabs>
