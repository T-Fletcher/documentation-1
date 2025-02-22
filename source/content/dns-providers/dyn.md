---
title: Dyn Domain Configuration
provider: Dyn
dnsprovider: true
description: Learn how to point your Dyn domain to a Pantheon site.
tags: [dns]
permalink: docs/:basename
editpath: dns-providers/dyn.md/
newtype: doc
categories: [domains, launch]
newcms: [--]
audience: [--]
product: [--]
integration: [--]
---
## Before You Begin
Be sure that you have a:


- Registered domain name using Dyn to host DNS

- [Paid Pantheon plan](/guides/launch/plans)

- [Domain connected](/guides/launch/domains) to the target Pantheon environment (typically Live):

 ![Domains / HTTPS](../../images/dashboard/domain-added.png)

## Locate Pantheon's DNS Values
Identify DNS values to point your domain to Pantheon:

1. Navigate to the Site Dashboard and select the target environment (typically <span class="glyphicons glyphicons-cardio"></span> Live) then click **<span class="glyphicons glyphicons-global"></span> Domains / HTTPS**.
2. Click the **Details** button next to your domain.

Keep this page open and login to your [Dyn DNS account](https://portal.dynect.net/login/) in a new tab before you continue.

## Configure DNS Records on Dyn

### A Record
1. Click **Overview** then **Manage** from the far right menu.
1. Navigate to **Simple Editor** > **Records**.
1. Select **A** from the record type dropdown menu.
1. Enter the A record value provided by Pantheon in the **IP Address** field.
1. Select desired Time to Live (TTL).

  <Accordion title="Learn More" id="ttl" icon="info-sign">

  #### Time to Live (TTL)

  The TTL dictates the lifespan of a DNS record; a shorter time means less time to wait until the changes go into effect. TTLs are always set in seconds with a few common ones being 86400 (24 hours), 43200 (12 hours), and 3600 (1 hour).

  When you make a change to the TTL of an existing record, you need to wait for the old TTL time to pass - that is, if it had been set to 86400, you would need to wait a full 24 hours for the new setting to begin propagating everywhere.

  </Accordion>

1. Click **Add**.

### AAAA Records
1. Select **AAAA** from the record type dropdown menu.
1. Enter the first AAAA record value provided by Pantheon in the **IP Address** field.
1. Select desired Time to Live (TTL).
1. Click **Add**.
1. Repeat steps 1-4 for the second AAAA record value provided by Pantheon. There are two AAAA records for improved uptime and reliability.

### A Record for subdomain
An A record is required to configure a subdomain (e.g., `www.example.com`).

1. Select **A** from the record type dropdown menu.
2. Enter the A record value provided by Pantheon (e.g. `23.185.0.2`) in the **IP Address** field.
3. Select desired Time to Live (TTL).
4. Click **Add**.

## Dyn Docs

* [Creating a Zone](https://help.dyn.com/creating-a-zone/)
* [Zone Records](https://help.dyn.com/zone-records/)

## Next Steps

* [Launch Essentials: Domains & HTTPS](/guides/launch/domains)

* [Launch Essentials: Redirect to a Primary Domain](/guides/launch/redirects)
