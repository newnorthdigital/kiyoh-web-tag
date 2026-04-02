# Kiyoh Review Invite — GTM Web Tag Template

A Google Tag Manager web tag template for [Kiyoh](https://www.kiyoh.com) and [Klantenvertellen](https://www.klantenvertellen.nl) review invitations. Trigger review invitation emails on the order confirmation page.

## Features

- **Review Invitations** — Send review invite emails to customers after purchase
- **Dual Platform** — Supports both Kiyoh (tenantId 98) and Klantenvertellen (tenantId 99)
- **Personalization** — Include customer name for personalized invitations
- **Delayed Sending** — Configure a delay (in days) before the invitation is sent
- **Multi-Language** — Dutch, English, German, French
- **Order Tracking** — Include order reference ID for cross-referencing

## Setup

1. Create a new tag using the **Kiyoh Review Invite** template
2. Enter your **API Hash** (from Kiyoh dashboard > Publish > Extra options)
3. Enter your **Location ID** (from your dashboard URL)
4. Select your **Platform** (Kiyoh or Klantenvertellen)
5. Map customer data to GTM variables:
   - **Customer Email**: e.g. `{{dlv - customer_email}}`
   - **First Name**: e.g. `{{dlv - customer_first_name}}`
   - **Last Name**: e.g. `{{dlv - customer_last_name}}`
   - **Order ID**: e.g. `{{dlv - order_id}}`
6. Set the trigger to fire on the **Order Confirmation Page**

## Template Fields

| Field | Required | Description |
|-------|----------|-------------|
| API Hash | Yes | Kiyoh API authentication hash |
| Location ID | Yes | Your business location identifier |
| Platform | Yes | Kiyoh or Klantenvertellen |
| Customer Email | Yes | Email for the review invitation |
| First Name | No | Customer first name |
| Last Name | No | Customer last name |
| Order ID | No | Order reference for tracking |
| Delay (days) | No | Days to wait before sending (default: 0) |
| Language | No | Invitation language (default: Nederlands) |

## How It Works

On the order confirmation page, this tag sends a GET request to the Kiyoh invite API (`kiyoh.com/v1/invite/external`) with the customer and order data. Kiyoh then schedules a review invitation email to the customer.

## Permissions

- **Send Pixel** — Sends GET request to `https://www.kiyoh.com/v1/invite/external`
- **Logging** — Console logging in debug/preview mode only

## Resources

- [Kiyoh Dashboard](https://www.kiyoh.com)
- [Klantenvertellen](https://www.klantenvertellen.nl)

## Author

Created by [New North Digital](https://newnorth.digital?utm_source=github&utm_medium=gtm-template&utm_campaign=kiyoh-web-tag)

## License

Apache 2.0 — see [LICENSE](LICENSE).
