--- 
title: domains
hide_title: false
hide_table_of_contents: false
keywords:
  - domains
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

Creates, updates, deletes, gets or lists a <code>domains</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>domains</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.domains.domains" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="get"
    values={[
        { label: 'get', value: 'get' },
        { label: 'list', value: 'list' }
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
    <td><CopyableCode code="authCode" /></td>
    <td><code>string</code></td>
    <td>Authorization code for transferring the Domain</td>
</tr>
<tr>
    <td><CopyableCode code="contactAdmin" /></td>
    <td><code>object</code></td>
    <td>Administrative contact for the domain registration</td>
</tr>
<tr>
    <td><CopyableCode code="contactBilling" /></td>
    <td><code>object</code></td>
    <td>Billing contact for the domain registration</td>
</tr>
<tr>
    <td><CopyableCode code="contactRegistrant" /></td>
    <td><code>object</code></td>
    <td>Registration contact for the domain</td>
</tr>
<tr>
    <td><CopyableCode code="contactTech" /></td>
    <td><code>object</code></td>
    <td>Technical contact for the domain registration</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date and time when this domain was created</td>
</tr>
<tr>
    <td><CopyableCode code="deletedAt" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date and time when this domain was deleted</td>
</tr>
<tr>
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>Name of the domain</td>
</tr>
<tr>
    <td><CopyableCode code="domainId" /></td>
    <td><code>number (double)</code></td>
    <td>Unique identifier for this Domain</td>
</tr>
<tr>
    <td><CopyableCode code="expirationProtected" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is protected from expiration</td>
</tr>
<tr>
    <td><CopyableCode code="expires" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date and time when this domain will expire</td>
</tr>
<tr>
    <td><CopyableCode code="holdRegistrar" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is on-hold by the registrar</td>
</tr>
<tr>
    <td><CopyableCode code="locked" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is locked to prevent transfers</td>
</tr>
<tr>
    <td><CopyableCode code="nameServers" /></td>
    <td><code>array</code></td>
    <td>Fully-qualified domain names for DNS servers</td>
</tr>
<tr>
    <td><CopyableCode code="privacy" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain has privacy protection</td>
</tr>
<tr>
    <td><CopyableCode code="renewAuto" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is configured to automatically renew</td>
</tr>
<tr>
    <td><CopyableCode code="renewDeadline" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date the domain must renew on</td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td>Processing status of the domain ACTIVE - All is well AWAITING* - System is waiting for the end-user to complete an action CANCELLED* - Domain has been cancelled, and may or may not be reclaimable CONFISCATED - Domain has been confiscated, usually for abuse, chargeback, or fraud DISABLED* - Domain has been disabled EXCLUDED* - Domain has been excluded from Firehose registration EXPIRED* - Domain has expired FAILED* - Domain has failed a required action, and the system is no longer retrying HELD* - Domain has been placed on hold, and likely requires intervention from Support LOCKED* - Domain has been locked, and likely requires intervention from Support PARKED* - Domain has been parked, and likely requires intervention from Support PENDING* - Domain is working its way through an automated workflow RESERVED* - Domain is reserved, and likely requires intervention from Support REVERTED - Domain has been reverted, and likely requires intervention from Support SUSPENDED* - Domain has been suspended, and likely requires intervention from Support TRANSFERRED* - Domain has been transferred out UNKNOWN - Domain is in an unknown state UNLOCKED* - Domain has been unlocked, and likely requires intervention from Support UNPARKED* - Domain has been unparked, and likely requires intervention from Support UPDATED* - Domain ownership has been transferred to another account </td>
</tr>
<tr>
    <td><CopyableCode code="subaccountId" /></td>
    <td><code>string</code></td>
    <td>Reseller subaccount shopperid who can manage the domain</td>
</tr>
<tr>
    <td><CopyableCode code="transferProtected" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is protected from transfer</td>
</tr>
<tr>
    <td><CopyableCode code="verifications" /></td>
    <td><code>object</code></td>
    <td>Progress and status for each of the verification processes requested for this domain</td>
</tr>
</tbody>
</table>
</TabItem>
<TabItem value="list">

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
    <td><CopyableCode code="authCode" /></td>
    <td><code>string</code></td>
    <td>Authorization code for transferring the Domain</td>
</tr>
<tr>
    <td><CopyableCode code="contactAdmin" /></td>
    <td><code>object</code></td>
    <td>Administrative contact for the domain registration</td>
</tr>
<tr>
    <td><CopyableCode code="contactBilling" /></td>
    <td><code>object</code></td>
    <td>Billing contact for the domain registration</td>
</tr>
<tr>
    <td><CopyableCode code="contactRegistrant" /></td>
    <td><code>object</code></td>
    <td>Registration contact for the domain</td>
</tr>
<tr>
    <td><CopyableCode code="contactTech" /></td>
    <td><code>object</code></td>
    <td>Technical contact for the domain registration</td>
</tr>
<tr>
    <td><CopyableCode code="createdAt" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date and time when this domain was created</td>
</tr>
<tr>
    <td><CopyableCode code="deletedAt" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date and time when this domain was deleted</td>
</tr>
<tr>
    <td><CopyableCode code="domain" /></td>
    <td><code>string</code></td>
    <td>Name of the domain</td>
</tr>
<tr>
    <td><CopyableCode code="domainId" /></td>
    <td><code>number (double)</code></td>
    <td>Unique identifier for this Domain</td>
</tr>
<tr>
    <td><CopyableCode code="expirationProtected" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is protected from expiration</td>
</tr>
<tr>
    <td><CopyableCode code="expires" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date and time when this domain will expire</td>
</tr>
<tr>
    <td><CopyableCode code="holdRegistrar" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is on-hold by the registrar</td>
</tr>
<tr>
    <td><CopyableCode code="locked" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is locked to prevent transfers</td>
</tr>
<tr>
    <td><CopyableCode code="nameServers" /></td>
    <td><code>array</code></td>
    <td>Fully-qualified domain names for DNS servers</td>
</tr>
<tr>
    <td><CopyableCode code="privacy" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain has privacy protection</td>
</tr>
<tr>
    <td><CopyableCode code="renewAuto" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is configured to automatically renew</td>
</tr>
<tr>
    <td><CopyableCode code="renewDeadline" /></td>
    <td><code>string (date-time)</code></td>
    <td>Date the domain must renew on</td>
</tr>
<tr>
    <td><CopyableCode code="renewable" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is eligble for renewal based on status</td>
</tr>
<tr>
    <td><CopyableCode code="status" /></td>
    <td><code>string</code></td>
    <td>Processing status of the domain ACTIVE - All is well AWAITING* - System is waiting for the end-user to complete an action CANCELLED* - Domain has been cancelled, and may or may not be reclaimable CONFISCATED - Domain has been confiscated, usually for abuse, chargeback, or fraud DISABLED* - Domain has been disabled EXCLUDED* - Domain has been excluded from Firehose registration EXPIRED* - Domain has expired FAILED* - Domain has failed a required action, and the system is no longer retrying HELD* - Domain has been placed on hold, and likely requires intervention from Support LOCKED* - Domain has been locked, and likely requires intervention from Support PARKED* - Domain has been parked, and likely requires intervention from Support PENDING* - Domain is working its way through an automated workflow RESERVED* - Domain is reserved, and likely requires intervention from Support REVERTED - Domain has been reverted, and likely requires intervention from Support SUSPENDED* - Domain has been suspended, and likely requires intervention from Support TRANSFERRED* - Domain has been transferred out UNKNOWN - Domain is in an unknown state UNLOCKED* - Domain has been unlocked, and likely requires intervention from Support UNPARKED* - Domain has been unparked, and likely requires intervention from Support UPDATED* - Domain ownership has been transferred to another account </td>
</tr>
<tr>
    <td><CopyableCode code="transferProtected" /></td>
    <td><code>boolean</code></td>
    <td>Whether or not the domain is protected from transfer</td>
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
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Retrieve details for the specified Domain</td>
</tr>
<tr>
    <td><a href="#list"><CopyableCode code="list" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a>, <a href="#parameter-statuses"><code>statuses</code></a>, <a href="#parameter-statusGroups"><code>statusGroups</code></a>, <a href="#parameter-limit"><code>limit</code></a>, <a href="#parameter-marker"><code>marker</code></a>, <a href="#parameter-includes"><code>includes</code></a>, <a href="#parameter-modifiedDate"><code>modifiedDate</code></a></td>
    <td>Retrieve a list of Domains for the specified Shopper</td>
</tr>
<tr>
    <td><a href="#contacts_validate"><CopyableCode code="contacts_validate" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domains"><code>domains</code></a></td>
    <td><a href="#parameter-X-Private-Label-Id"><code>X-Private-Label-Id</code></a>, <a href="#parameter-marketId"><code>marketId</code></a></td>
    <td>All contacts specified in request will be validated against all domains specifed in "domains". As an alternative, you can also pass in tlds, with the exception of `uk`, which requires full domain names</td>
</tr>
<tr>
    <td><a href="#purchase"><CopyableCode code="purchase" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-consent"><code>consent</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Purchase and register the specified Domain</td>
</tr>
<tr>
    <td><a href="#validate"><CopyableCode code="validate" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-consent"><code>consent</code></a></td>
    <td></td>
    <td>Validate the request body using the Domain Purchase Schema for the specified TLD</td>
</tr>
<tr>
    <td><a href="#cancel"><CopyableCode code="cancel" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td></td>
    <td>Cancel a purchased domain</td>
</tr>
<tr>
    <td><a href="#update"><CopyableCode code="update" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Update details for the specified Domain</td>
</tr>
<tr>
    <td><a href="#update_contacts"><CopyableCode code="update_contacts" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-contactRegistrant"><code>contactRegistrant</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Update domain</td>
</tr>
<tr>
    <td><a href="#cancel_privacy"><CopyableCode code="cancel_privacy" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Submit a privacy cancellation request for the given domain</td>
</tr>
<tr>
    <td><a href="#purchase_privacy"><CopyableCode code="purchase_privacy" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-consent"><code>consent</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Purchase privacy for a specified domain</td>
</tr>
<tr>
    <td><a href="#renew"><CopyableCode code="renew" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Renew the specified Domain</td>
</tr>
<tr>
    <td><a href="#transfer_in"><CopyableCode code="transfer_in" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a>, <a href="#parameter-authCode"><code>authCode</code></a>, <a href="#parameter-consent"><code>consent</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Purchase and start or restart transfer process</td>
</tr>
<tr>
    <td><a href="#verify_email"><CopyableCode code="verify_email" /></a></td>
    <td><CopyableCode code="exec" /></td>
    <td><a href="#parameter-domain"><code>domain</code></a></td>
    <td><a href="#parameter-X-Shopper-Id"><code>X-Shopper-Id</code></a></td>
    <td>Re-send Contact E-mail Verification for specified Domain</td>
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
    <td>Domain whose Contact E-mail should be verified.</td>
</tr>
<tr id="parameter-X-Private-Label-Id">
    <td><CopyableCode code="X-Private-Label-Id" /></td>
    <td><code>integer</code></td>
    <td>PrivateLabelId to operate as, if different from JWT</td>
</tr>
<tr id="parameter-X-Shopper-Id">
    <td><CopyableCode code="X-Shopper-Id" /></td>
    <td><code>string</code></td>
    <td>Shopper for whom domain contact e-mail should be verified. NOTE: This is only required if you are a Reseller managing a domain purchased outside the scope of your reseller account. For instance, if you're a Reseller, but purchased a Domain via http://www.godaddy.com</td>
</tr>
<tr id="parameter-includes">
    <td><CopyableCode code="includes" /></td>
    <td><code>array</code></td>
    <td>Optional details to be included in the response</td>
</tr>
<tr id="parameter-limit">
    <td><CopyableCode code="limit" /></td>
    <td><code>integer</code></td>
    <td>Maximum number of domains to return</td>
</tr>
<tr id="parameter-marker">
    <td><CopyableCode code="marker" /></td>
    <td><code>string</code></td>
    <td>Marker Domain to use as the offset in results</td>
</tr>
<tr id="parameter-marketId">
    <td><CopyableCode code="marketId" /></td>
    <td><code>string (bcp-47)</code></td>
    <td>MarketId in which the request is being made, and for which responses should be localized</td>
</tr>
<tr id="parameter-modifiedDate">
    <td><CopyableCode code="modifiedDate" /></td>
    <td><code>string (iso-datetime)</code></td>
    <td>Only include results that have been modified since the specified date</td>
</tr>
<tr id="parameter-statusGroups">
    <td><CopyableCode code="statusGroups" /></td>
    <td><code>array</code></td>
    <td>Only include results with `status` value in any of the specified groups</td>
</tr>
<tr id="parameter-statuses">
    <td><CopyableCode code="statuses" /></td>
    <td><code>array</code></td>
    <td>Only include results with `status` value in the specified set</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="get"
    values={[
        { label: 'get', value: 'get' },
        { label: 'list', value: 'list' }
    ]}
>
<TabItem value="get">

Retrieve details for the specified Domain

```sql
SELECT
authCode,
contactAdmin,
contactBilling,
contactRegistrant,
contactTech,
createdAt,
deletedAt,
domain,
domainId,
expirationProtected,
expires,
holdRegistrar,
locked,
nameServers,
privacy,
renewAuto,
renewDeadline,
status,
subaccountId,
transferProtected,
verifications
FROM godaddy.domains.domains
WHERE domain = '{{ domain }}' -- required
AND X-Shopper-Id = '{{ X-Shopper-Id }}'
;
```
</TabItem>
<TabItem value="list">

Retrieve a list of Domains for the specified Shopper

```sql
SELECT
authCode,
contactAdmin,
contactBilling,
contactRegistrant,
contactTech,
createdAt,
deletedAt,
domain,
domainId,
expirationProtected,
expires,
holdRegistrar,
locked,
nameServers,
privacy,
renewAuto,
renewDeadline,
renewable,
status,
transferProtected
FROM godaddy.domains.domains
WHERE X-Shopper-Id = '{{ X-Shopper-Id }}'
AND statuses = '{{ statuses }}'
AND statusGroups = '{{ statusGroups }}'
AND limit = '{{ limit }}'
AND marker = '{{ marker }}'
AND includes = '{{ includes }}'
AND modifiedDate = '{{ modifiedDate }}'
;
```
</TabItem>
</Tabs>


## Lifecycle Methods

<Tabs
    defaultValue="contacts_validate"
    values={[
        { label: 'contacts_validate', value: 'contacts_validate' },
        { label: 'purchase', value: 'purchase' },
        { label: 'validate', value: 'validate' },
        { label: 'cancel', value: 'cancel' },
        { label: 'update', value: 'update' },
        { label: 'update_contacts', value: 'update_contacts' },
        { label: 'cancel_privacy', value: 'cancel_privacy' },
        { label: 'purchase_privacy', value: 'purchase_privacy' },
        { label: 'renew', value: 'renew' },
        { label: 'transfer_in', value: 'transfer_in' },
        { label: 'verify_email', value: 'verify_email' }
    ]}
>
<TabItem value="contacts_validate">

All contacts specified in request will be validated against all domains specifed in "domains". As an alternative, you can also pass in tlds, with the exception of `uk`, which requires full domain names

```sql
EXEC godaddy.domains.domains.contacts_validate 
@X-Private-Label-Id='{{ X-Private-Label-Id }}', 
@marketId='{{ marketId }}' 
@@json=
'{
"contactAdmin": "{{ contactAdmin }}", 
"contactBilling": "{{ contactBilling }}", 
"contactPresence": "{{ contactPresence }}", 
"contactRegistrant": "{{ contactRegistrant }}", 
"contactTech": "{{ contactTech }}", 
"domains": "{{ domains }}", 
"entityType": "{{ entityType }}"
}'
;
```
</TabItem>
<TabItem value="purchase">

Purchase and register the specified Domain

```sql
EXEC godaddy.domains.domains.purchase 
@X-Shopper-Id='{{ X-Shopper-Id }}' 
@@json=
'{
"consent": "{{ consent }}", 
"contactAdmin": "{{ contactAdmin }}", 
"contactBilling": "{{ contactBilling }}", 
"contactRegistrant": "{{ contactRegistrant }}", 
"contactTech": "{{ contactTech }}", 
"domain": "{{ domain }}", 
"nameServers": "{{ nameServers }}", 
"period": {{ period }}, 
"privacy": {{ privacy }}, 
"renewAuto": {{ renewAuto }}
}'
;
```
</TabItem>
<TabItem value="validate">

Validate the request body using the Domain Purchase Schema for the specified TLD

```sql
EXEC godaddy.domains.domains.validate 
@@json=
'{
"consent": "{{ consent }}", 
"contactAdmin": "{{ contactAdmin }}", 
"contactBilling": "{{ contactBilling }}", 
"contactRegistrant": "{{ contactRegistrant }}", 
"contactTech": "{{ contactTech }}", 
"domain": "{{ domain }}", 
"nameServers": "{{ nameServers }}", 
"period": {{ period }}, 
"privacy": {{ privacy }}, 
"renewAuto": {{ renewAuto }}
}'
;
```
</TabItem>
<TabItem value="cancel">

Cancel a purchased domain

```sql
EXEC godaddy.domains.domains.cancel 
@domain='{{ domain }}' --required
;
```
</TabItem>
<TabItem value="update">

Update details for the specified Domain

```sql
EXEC godaddy.domains.domains.update 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}' 
@@json=
'{
"locked": {{ locked }}, 
"nameServers": "{{ nameServers }}", 
"renewAuto": {{ renewAuto }}, 
"subaccountId": "{{ subaccountId }}"
}'
;
```
</TabItem>
<TabItem value="update_contacts">

Update domain

```sql
EXEC godaddy.domains.domains.update_contacts 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}' 
@@json=
'{
"contactAdmin": "{{ contactAdmin }}", 
"contactBilling": "{{ contactBilling }}", 
"contactRegistrant": "{{ contactRegistrant }}", 
"contactTech": "{{ contactTech }}"
}'
;
```
</TabItem>
<TabItem value="cancel_privacy">

Submit a privacy cancellation request for the given domain

```sql
EXEC godaddy.domains.domains.cancel_privacy 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}'
;
```
</TabItem>
<TabItem value="purchase_privacy">

Purchase privacy for a specified domain

```sql
EXEC godaddy.domains.domains.purchase_privacy 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}' 
@@json=
'{
"consent": "{{ consent }}"
}'
;
```
</TabItem>
<TabItem value="renew">

Renew the specified Domain

```sql
EXEC godaddy.domains.domains.renew 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}' 
@@json=
'{
"period": {{ period }}
}'
;
```
</TabItem>
<TabItem value="transfer_in">

Purchase and start or restart transfer process

```sql
EXEC godaddy.domains.domains.transfer_in 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}' 
@@json=
'{
"authCode": "{{ authCode }}", 
"consent": "{{ consent }}", 
"period": {{ period }}, 
"privacy": {{ privacy }}, 
"renewAuto": {{ renewAuto }}
}'
;
```
</TabItem>
<TabItem value="verify_email">

Re-send Contact E-mail Verification for specified Domain

```sql
EXEC godaddy.domains.domains.verify_email 
@domain='{{ domain }}' --required, 
@X-Shopper-Id='{{ X-Shopper-Id }}'
;
```
</TabItem>
</Tabs>
