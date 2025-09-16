--- 
title: certificates
hide_title: false
hide_table_of_contents: false
keywords:
  - certificates
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

Creates, updates, deletes, gets or lists a <code>certificates</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>certificates</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.certificates.certificates" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="certificate_get"
    values={[
        { label: 'certificate_get', value: 'certificate_get' }
    ]}
>
<TabItem value="certificate_get">

Certificate details retrieved

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
    <td><CopyableCode code="certificateId" /></td>
    <td><code>string</code></td>
    <td>The unique identifier of the certificate request. Only present if no errors returned</td>
</tr>
<tr>
    <td><CopyableCode code="commonName" /></td>
    <td><code>string</code></td>
    <td>Common name of certificate</td>
</tr>
<tr>
    <td><CopyableCode code="contact" /></td>
    <td><code>object</code></td>
    <td>Requestor contact information</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The date the certificate was ordered.</td>
</tr>
<tr>
    <td><CopyableCode code="deniedReason" /></td>
    <td><code>string</code></td>
    <td>Only present if certificate order has been denied</td>
</tr>
<tr>
    <td><CopyableCode code="organization" /></td>
    <td><code>object</code></td>
    <td>Organization Name in certificate</td>
</tr>
<tr>
    <td><CopyableCode code="period" /></td>
    <td><code>integer</code></td>
    <td>Validity period of order. Specified in years</td>
</tr>
<tr>
    <td><CopyableCode code="productType" /></td>
    <td><code>string</code></td>
    <td>Certificate product type</td>
</tr>
<tr>
    <td><CopyableCode code="progress" /></td>
    <td><code>integer</code></td>
    <td>Percentage of completion for certificate vetting</td>
</tr>
<tr>
    <td><CopyableCode code="revokedAt" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The revocation date of certificate (if revoked).</td>
</tr>
<tr>
    <td><CopyableCode code="rootType" /></td>
    <td><code>string</code></td>
    <td>Root Type</td>
</tr>
<tr>
    <td><CopyableCode code="serialNumber" /></td>
    <td><code>string</code></td>
    <td>Serial number of certificate (if issued or revoked)</td>
</tr>
<tr>
    <td><CopyableCode code="serialNumberHex" /></td>
    <td><code>string</code></td>
    <td>Hexadecmial format for Serial number of certificate(if issued or revoked)</td>
</tr>
<tr>
    <td><CopyableCode code="slotSize" /></td>
    <td><code>string</code></td>
    <td>Number of subject alternative names(SAN) to be included in certificate </td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td>Status of certificate</td>
</tr>
<tr>
    <td><CopyableCode code="subjectAlternativeNames" /></td>
    <td><code>array</code></td>
    <td>Contains subject alternative names set</td>
</tr>
<tr>
    <td><CopyableCode code="validEnd" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The end date of the certificate's validity (if issued or revoked).</td>
</tr>
<tr>
    <td><CopyableCode code="validStart" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>The start date of the certificate's validity (if issued or revoked).</td>
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
    <td><a href="#certificate_get"><CopyableCode code="certificate_get" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>Once the certificate order has been created, this method can be used to check the status of the certificate. This method can also be used to retrieve details of the certificate.</td>
</tr>
<tr>
    <td><a href="#certificate_create"><CopyableCode code="certificate_create" /></a></td>
    <td><CopyableCode code="insert" /></td>
    <td><a href="#parameter-data__csr"><code>data__csr</code></a>, <a href="#parameter-data__productType"><code>data__productType</code></a>, <a href="#parameter-data__period"><code>data__period</code></a>, <a href="#parameter-data__contact"><code>data__contact</code></a></td>
    <td><a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>Creating a certificate order can be a long running asynchronous operation in the PKI workflow. The PKI API supports 2 options for getting the completion stateful actions for this asynchronous operations: 1) by polling operations -- see /v1/certificates/&#123;certificateId&#125;/actions 2) via WebHook style callback -- see '/v1/certificates/&#123;certificateId&#125;/callback'.</td>
</tr>
<tr>
    <td><a href="#certificate_validate"><CopyableCode code="certificate_validate" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-csr"><code>csr</code></a>, <a href="#parameter-productType"><code>productType</code></a>, <a href="#parameter-period"><code>period</code></a>, <a href="#parameter-contact"><code>contact</code></a></td>
    <td><a href="#parameter-X-Market-Id"><code>X-Market-Id</code></a></td>
    <td>Validate a pending order for certificate</td>
</tr>
<tr>
    <td><a href="#certificate_cancel"><CopyableCode code="certificate_cancel" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>Use the cancel call to cancel a pending certificate order.</td>
</tr>
<tr>
    <td><a href="#certificate_download"><CopyableCode code="certificate_download" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>Download certificate</td>
</tr>
<tr>
    <td><a href="#certificate_reissue"><CopyableCode code="certificate_reissue" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>Rekeying is the process by which the private and public key is changed for a certificate. It is a simplified reissue,where only the CSR is changed. Reissuing is the process by which domain  names are added or removed from a certificate.Once a request is validated and approved, the certificate  will be reissued with the new common name and sans specified. Unlimited reissues are available during the  lifetime of the certificate.New names added to a certificate that do not share the base domain of the  common name may take additional time to validate. If this API call is made before a previous pending  reissue has been validated and issued, the previous reissue request is automatically rejected and replaced  with the current request.'</td>
</tr>
<tr>
    <td><a href="#certificate_renew"><CopyableCode code="certificate_renew" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>Renewal is the process by which the validity of a certificate is extended. Renewal is only available 60 days prior to expiration of the previous certificate and 30 days after the expiration of the previous certificate.  The renewal supports modifying a set of the original certificate order information. Once a request is validated and approved, the certificate  will be issued with extended validity. Since subject alternative names can be removed during a renewal, we  require that you provide the subject alternative names you expect in the renewed certificate. New names added to a certificate that do not share the base domain of the  common name may take additional time to validate. </td>
</tr>
<tr>
    <td><a href="#certificate_revoke"><CopyableCode code="certificate_revoke" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a>, <a href="#parameter-reason"><code>reason</code></a></td>
    <td></td>
    <td>Use revoke call to revoke an active certificate, if the certificate has not been issued a 404 response will be returned.</td>
</tr>
<tr>
    <td><a href="#certificate_verifydomaincontrol"><CopyableCode code="certificate_verifydomaincontrol" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td></td>
    <td>Domain control is a means for verifying the domain included in the certificate order. This resource is useful for resellers that control the domains for their customers, and can expedite the verification process. See https://www.godaddy.com/help/verifying-your-domain-ownership-for-ssl-certificate-requests-html-or-dns-7452</td>
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
    <td>Certificate id to lookup</td>
</tr>
<tr id="parameter-X-Market-Id">
    <td><CopyableCode code="X-Market-Id" /></td>
    <td><code>string</code></td>
    <td>Setting locale for communications such as emails and error messages</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="certificate_get"
    values={[
        { label: 'certificate_get', value: 'certificate_get' }
    ]}
>
<TabItem value="certificate_get">

Once the certificate order has been created, this method can be used to check the status of the certificate. This method can also be used to retrieve details of the certificate.

```sql
SELECT
certificateId,
commonName,
contact,
createdAt,
deniedReason,
organization,
period,
productType,
progress,
revokedAt,
rootType,
serialNumber,
serialNumberHex,
slotSize,
status,
subjectAlternativeNames,
validEnd,
validStart
FROM godaddy.certificates.certificates
WHERE certificate_id = '{{ certificate_id }}' -- required
;
```
</TabItem>
</Tabs>


## `INSERT` examples

<Tabs
    defaultValue="certificate_create"
    values={[
        { label: 'certificate_create', value: 'certificate_create' },
        { label: 'Manifest', value: 'manifest' }
    ]}
>
<TabItem value="certificate_create">

Creating a certificate order can be a long running asynchronous operation in the PKI workflow. The PKI API supports 2 options for getting the completion stateful actions for this asynchronous operations: 1) by polling operations -- see /v1/certificates/&#123;certificateId&#125;/actions 2) via WebHook style callback -- see '/v1/certificates/&#123;certificateId&#125;/callback'.

```sql
INSERT INTO godaddy.certificates.certificates (
data__callbackUrl,
data__commonName,
data__contact,
data__csr,
data__intelVPro,
data__organization,
data__period,
data__productType,
data__rootType,
data__slotSize,
data__subjectAlternativeNames,
X-Market-Id
)
SELECT 
'{{ callbackUrl }}',
'{{ commonName }}',
'{{ contact }}' /* required */,
'{{ csr }}' /* required */,
{{ intelVPro }},
'{{ organization }}',
{{ period }} /* required */,
'{{ productType }}' /* required */,
'{{ rootType }}',
'{{ slotSize }}',
'{{ subjectAlternativeNames }}',
'{{ X-Market-Id }}'
;
```
</TabItem>
<TabItem value="manifest">

```yaml
# Description fields are for documentation purposes
- name: certificates
  props:
    - name: callbackUrl
      value: string
      description: |
        Required if client would like to receive stateful actions via callback during certificate lifecyle
    - name: commonName
      value: string
      description: |
        Name to be secured in certificate. If provided, CN field in CSR will be ignored.
    - name: contact
      value: object
      description: |
        Requestor contact information
    - name: csr
      value: string
      description: |
        Certificate Signing Request
    - name: intelVPro
      value: boolean
      description: |
        Only used for OV
      default: false
    - name: organization
      value: object
      description: |
        Required for EVSSL, OVSSL, CS, and DS
    - name: period
      value: integer
      description: |
        Number of years for certificate validity period
    - name: productType
      value: string
      description: |
        Type of product requesting a certificate. Only required non-renewal
      valid_values: ['DV_SSL', 'DV_WILDCARD_SSL', 'EV_SSL', 'OV_CS', 'OV_DS', 'OV_SSL', 'OV_WILDCARD_SSL', 'UCC_DV_SSL', 'UCC_EV_SSL', 'UCC_OV_SSL']
    - name: rootType
      value: string
      description: |
        Root Type. Depending on certificate expiration date, SHA_1 not be allowed. Will default to SHA_2 if expiration date exceeds sha1 allowed date
      valid_values: ['GODADDY_SHA_1', 'GODADDY_SHA_2', 'STARFIELD_SHA_1', 'STARFIELD_SHA_2']
      default: STARFIELD_SHA_2
    - name: slotSize
      value: string
      description: |
        Number of subject alternative names(SAN) to be included in certificate
      valid_values: ['FIVE', 'TEN', 'FIFTEEN', 'TWENTY', 'THIRTY', 'FOURTY', 'FIFTY', 'ONE_HUNDRED']
    - name: subjectAlternativeNames
      value: array
      description: |
        Subject Alternative names. Collection of subjectAlternativeNames to be included in certificate.
    - name: X-Market-Id
      value: string
      description: Setting locale for communications such as emails and error messages
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="certificate_validate"
    values={[
        { label: 'certificate_validate', value: 'certificate_validate' },
        { label: 'certificate_cancel', value: 'certificate_cancel' },
        { label: 'certificate_download', value: 'certificate_download' },
        { label: 'certificate_reissue', value: 'certificate_reissue' },
        { label: 'certificate_renew', value: 'certificate_renew' },
        { label: 'certificate_revoke', value: 'certificate_revoke' },
        { label: 'certificate_verifydomaincontrol', value: 'certificate_verifydomaincontrol' }
    ]}
>
<TabItem value="certificate_validate">

Validate a pending order for certificate

```sql
EXEC godaddy.certificates.certificates.certificate_validate 
@X-Market-Id='{{ X-Market-Id }}' 
@@json=
'{
"callbackUrl": "{{ callbackUrl }}", 
"commonName": "{{ commonName }}", 
"contact": "{{ contact }}", 
"csr": "{{ csr }}", 
"intelVPro": {{ intelVPro }}, 
"organization": "{{ organization }}", 
"period": {{ period }}, 
"productType": "{{ productType }}", 
"rootType": "{{ rootType }}", 
"slotSize": "{{ slotSize }}", 
"subjectAlternativeNames": "{{ subjectAlternativeNames }}"
}'
;
```
</TabItem>
<TabItem value="certificate_cancel">

Use the cancel call to cancel a pending certificate order.

```sql
EXEC godaddy.certificates.certificates.certificate_cancel 
@certificate_id='{{ certificate_id }}' --required
;
```
</TabItem>
<TabItem value="certificate_download">

Download certificate

```sql
EXEC godaddy.certificates.certificates.certificate_download 
@certificate_id='{{ certificate_id }}' --required
;
```
</TabItem>
<TabItem value="certificate_reissue">

Rekeying is the process by which the private and public key is changed for a certificate. It is a simplified reissue,where only the CSR is changed. Reissuing is the process by which domain  names are added or removed from a certificate.Once a request is validated and approved, the certificate  will be reissued with the new common name and sans specified. Unlimited reissues are available during the  lifetime of the certificate.New names added to a certificate that do not share the base domain of the  common name may take additional time to validate. If this API call is made before a previous pending  reissue has been validated and issued, the previous reissue request is automatically rejected and replaced  with the current request.'

```sql
EXEC godaddy.certificates.certificates.certificate_reissue 
@certificate_id='{{ certificate_id }}' --required 
@@json=
'{
"callbackUrl": "{{ callbackUrl }}", 
"commonName": "{{ commonName }}", 
"csr": "{{ csr }}", 
"delayExistingRevoke": {{ delayExistingRevoke }}, 
"rootType": "{{ rootType }}", 
"subjectAlternativeNames": "{{ subjectAlternativeNames }}"
}'
;
```
</TabItem>
<TabItem value="certificate_renew">

Renewal is the process by which the validity of a certificate is extended. Renewal is only available 60 days prior to expiration of the previous certificate and 30 days after the expiration of the previous certificate.  The renewal supports modifying a set of the original certificate order information. Once a request is validated and approved, the certificate  will be issued with extended validity. Since subject alternative names can be removed during a renewal, we  require that you provide the subject alternative names you expect in the renewed certificate. New names added to a certificate that do not share the base domain of the  common name may take additional time to validate. 

```sql
EXEC godaddy.certificates.certificates.certificate_renew 
@certificate_id='{{ certificate_id }}' --required 
@@json=
'{
"callbackUrl": "{{ callbackUrl }}", 
"commonName": "{{ commonName }}", 
"csr": "{{ csr }}", 
"period": {{ period }}, 
"rootType": "{{ rootType }}", 
"subjectAlternativeNames": "{{ subjectAlternativeNames }}"
}'
;
```
</TabItem>
<TabItem value="certificate_revoke">

Use revoke call to revoke an active certificate, if the certificate has not been issued a 404 response will be returned.

```sql
EXEC godaddy.certificates.certificates.certificate_revoke 
@certificate_id='{{ certificate_id }}' --required 
@@json=
'{
"reason": "{{ reason }}"
}'
;
```
</TabItem>
<TabItem value="certificate_verifydomaincontrol">

Domain control is a means for verifying the domain included in the certificate order. This resource is useful for resellers that control the domains for their customers, and can expedite the verification process. See https://www.godaddy.com/help/verifying-your-domain-ownership-for-ssl-certificate-requests-html-or-dns-7452

```sql
EXEC godaddy.certificates.certificates.certificate_verifydomaincontrol 
@certificate_id='{{ certificate_id }}' --required
;
```
</TabItem>
</Tabs>
