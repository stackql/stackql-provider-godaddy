--- 
title: site_seal
hide_title: false
hide_table_of_contents: false
keywords:
  - site_seal
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

Creates, updates, deletes, gets or lists a <code>site_seal</code> resource.

## Overview
<table><tbody>
<tr><td><b>Name</b></td><td><code>site_seal</code></td></tr>
<tr><td><b>Type</b></td><td>Resource</td></tr>
<tr><td><b>Id</b></td><td><CopyableCode code="godaddy.certificates.site_seal" /></td></tr>
</tbody></table>

## Fields

The following fields are returned by `SELECT` queries:

<Tabs
    defaultValue="certificate_siteseal_get"
    values={[
        { label: 'certificate_siteseal_get', value: 'certificate_siteseal_get' }
    ]}
>
<TabItem value="certificate_siteseal_get">

Site seal retrieved

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
    <td><CopyableCode code="html" /></td>
    <td><code>string</code></td>
    <td>Certificate Seal HTML</td>
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
    <td><a href="#certificate_siteseal_get"><CopyableCode code="certificate_siteseal_get" /></a></td>
    <td><CopyableCode code="select" /></td>
    <td><a href="#parameter-certificate_id"><code>certificate_id</code></a></td>
    <td><a href="#parameter-theme"><code>theme</code></a>, <a href="#parameter-locale"><code>locale</code></a></td>
    <td>This method is used to obtain the site seal information for an issued certificate. A site seal is a graphic that the certificate purchaser can embed on their web site to show  their visitors information about their SSL certificate. If a web site visitor clicks on the  site seal image, a pop-up page is displayed that contains detailed information about the SSL  certificate. The site seal token is used to link the site seal graphic image to the appropriate  certificate details pop-up page display when a user clicks on the site seal. The site seal  images are expected to be static images and hosted on the reseller''s website, to minimize  delays for customer page load times.</td>
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
    <td>Certificate id</td>
</tr>
<tr id="parameter-locale">
    <td><CopyableCode code="locale" /></td>
    <td><code>string</code></td>
    <td>Determine locale for text displayed in seal image and verification page. If seal doesn't exist, default values are used if params not present. If seal does exist, default values will not be used to update unless params present.</td>
</tr>
<tr id="parameter-theme">
    <td><CopyableCode code="theme" /></td>
    <td><code>string</code></td>
    <td>This value represents the visual theme of the seal. If seal doesn't exist, default values are used if params not present. If seal does exist, default values will not be used to update unless params present.</td>
</tr>
</tbody>
</table>

## `SELECT` examples

<Tabs
    defaultValue="certificate_siteseal_get"
    values={[
        { label: 'certificate_siteseal_get', value: 'certificate_siteseal_get' }
    ]}
>
<TabItem value="certificate_siteseal_get">

This method is used to obtain the site seal information for an issued certificate. A site seal is a graphic that the certificate purchaser can embed on their web site to show  their visitors information about their SSL certificate. If a web site visitor clicks on the  site seal image, a pop-up page is displayed that contains detailed information about the SSL  certificate. The site seal token is used to link the site seal graphic image to the appropriate  certificate details pop-up page display when a user clicks on the site seal. The site seal  images are expected to be static images and hosted on the reseller''s website, to minimize  delays for customer page load times.

```sql
SELECT
html
FROM godaddy.certificates.site_seal
WHERE certificate_id = '{{ certificate_id }}' -- required
AND theme = '{{ theme }}'
AND locale = '{{ locale }}'
;
```
</TabItem>
</Tabs>
