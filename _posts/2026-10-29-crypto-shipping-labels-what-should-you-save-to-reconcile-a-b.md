---
title: "Crypto shipping labels: what should you save to reconcile a BTC or ETH payment?"
date: 2026-10-29
excerpt: ""
keywords: ["crypto shipping labels", "Bitcoin shipping payments", "Ethereum shipping payments", "shipping payment reconciliation", "shipping label records"]
category: "crypto-shipping"
author: "Bitcoin Shipping Labels"
---

A carrier tracking number and a crypto transaction ID answer different operational questions. When buying **crypto shipping labels**, build a record that connects the parcel, the payment and the resulting label. That gives your bookkeeping or support workflow a useful starting point when someone asks, “Which shipment did this wallet transaction pay for?”

This walkthrough covers a local reconciliation record for Bitcoin Shipping Labels purchases paid in BTC or ETH. The goal: make each purchase understandable later without searching wallet history, downloaded PDFs and packing notes separately.

## 1. Give the shipment a reference before payment

Start with a reference you control, such as `SHIP-2026-0042`. Create it before opening the purchase flow, and use it consistently in your local records.

Keep the reference free of customer information. An internal shipment ID works better as a filename than a recipient’s name or street address.

For each parcel, record:

- Your internal shipment reference.
- The associated order reference, where applicable.
- The intended carrier and service.
- The packed weight and dimensions used for the purchase.
- The destination country.
- The person or process responsible for reconciliation.

Treat this as the shipment’s index entry. Payment details and label details will attach to it as you collect them.

Bitcoin Shipping Labels sells USPS, UPS, FedEx, DHL Express and Canada Post labels paid with crypto. Record the carrier you actually select rather than leaving the field at a default from an earlier purchase.

## 2. Build a small evidence record

A spreadsheet is enough for a small workflow. A database table is a natural fit if you already maintain an order-management tool.

Organize the record into three groups:

| Group | Fields to keep | Purpose |
| --- | --- | --- |
| Shipment | Internal reference, order reference, carrier, service | Identifies what you intended to ship |
| Payment | Asset, network, requested amount, sent amount, transaction ID, timestamps | Identifies the payment you made |
| Label | PDF location, tracking number, review status | Connects the purchase to its shipping artifact |

Use explicit units in field names. For example, `sent_amount_btc` is clearer than `amount`. If you support several assets in one table, keep separate `asset` and `sent_amount` fields.

Choose a consistent timestamp format with a timezone. Preserve the original timestamps in supporting records when available; use your normalized timestamp for sorting and searching.

Store evidence files in a restricted folder associated with the shipment reference. Keep wallet secrets, recovery phrases and private keys out of this record entirely.

## 3. Capture the payment request before sending

Bitcoin Shipping Labels accepts 100+ cryptocurrencies through NOWPayments, including BTC and ETH. For this workflow, choose the asset first, then record the payment instructions shown for that purchase.

Capture:

1. The selected asset.
2. The network specified in the payment instructions.
3. The requested crypto amount.
4. The destination payment address.
5. Any payment reference or deadline displayed.
6. The time you captured those instructions.

Copy addresses directly and check them against the displayed instructions before authorizing the transfer. Review the asset, network, address and amount together.

For a focused discussion of the two payment choices, read [Bitcoin versus Ethereum for buying shipping labels](https://www.bitcoinshippinglabels.com/blog/bitcoin-vs-ethereum-for-shipping-which-is-better). Keep the selected asset attached to the individual purchase in your ledger, even if your shop usually pays with the same coin.

A saved payment request gives you a concrete reference for the next step: comparing what was requested with what your wallet sent.

## 4. Record the wallet transaction separately

After sending payment, add the transaction identifier from your wallet to the shipment record. Preserve the full value rather than an abbreviated display string.

Collect these details from the wallet’s transaction view:

- Asset and network.
- Destination address.
- Amount sent.
- Transaction ID.
- Send timestamp.
- Network fee, if shown.
- Transaction status at the time of review.

Keep the sent amount and the network fee in separate fields. That makes later review more precise: you can compare the requested payment with the transfer amount while retaining the fee as its own entry.

Also keep wallet status and purchase status separate. Record each status as displayed, along with the time you observed it. Use the payment page to establish the purchase’s payment status, and the wallet to document the transaction you submitted.

If your reconciliation process needs confirmation details, capture the confirmation information shown by the payment provider or wallet. Follow the purchase’s displayed payment instructions rather than inserting a fixed confirmation threshold into your local checklist.

## 5. Attach the label as a distinct artifact

Once the label is available, save its PDF under the internal shipment reference. Bitcoin Shipping Labels provides labels as 4×6 PDFs.

A simple local naming convention is:

`SHIP-2026-0042-label.pdf`

Add the PDF’s storage location and the carrier tracking number to the record. Then review the document against the shipment you intended to purchase:

- Does the recipient match the order?
- Is the apartment or unit information correct?
- Does the carrier and service match your selection?
- Is the tracking number transcribed accurately?
- For an international shipment, is the required customs information correct?

Address suggestions can help catch apartment or unit mistakes during purchase. Include the final address check in your reconciliation review as well, particularly when someone has edited the shipment details.

Protect the PDF as shipping data. Keep label files and screenshots containing recipient information out of public GitHub repositories and issue threads.

## 6. Use evidence-based local statuses

Define a few statuses for your own ledger. Give each one a specific entry condition so that another team member can understand it.

| Local status | Evidence required |
| --- | --- |
| `prepared` | Shipment reference and intended parcel details recorded |
| `payment_sent` | Wallet transaction ID and sent amount captured |
| `payment_confirmed` | Payment page shows confirmation; observation recorded |
| `label_saved` | Label PDF saved and tracking number recorded |
| `reconciled` | Payment evidence and label reviewed against the same shipment |
| `needs_review` | A mismatch or missing artifact has an assigned follow-up |

Treat these as bookkeeping states in your own system. Record carrier tracking observations in a separate field, with their own timestamps.

For exceptions, write a specific follow-up such as “Compare sent amount with saved payment request” or “Locate PDF for shipment reference.” A precise action is easier to resolve than a generic error flag.

## 7. Test the record with a hypothetical purchase

Take the example reference `SHIP-2026-0042` and walk through it from both directions.

**Start from the wallet.** Search your ledger for the full transaction ID. Open the matching shipment reference, review the saved payment request and locate the label PDF.

**Start from the parcel.** Search for the carrier tracking number. Open the associated shipment record and locate the wallet transaction evidence.

Both searches should lead to the same record. If either route stops at a missing field, repair that gap before marking the purchase reconciled.

Bitcoin Shipping Labels requires no account to buy a label; accounts add a credit wallet, label history and bulk tools. Choose a local evidence routine that fits your purchasing setup, and consult the [shipping and payment FAQ](https://www.bitcoinshippinglabels.com/faq) when you need purchase guidance.

The practical test is straightforward: can someone open one shipment reference and explain what was requested, what was paid and which label resulted? Make that the acceptance criterion for reconciliation.

---

*Originally published on [Bitcoin Shipping Labels](https://www.bitcoinshippinglabels.com/blog/bitcoin-vs-ethereum-for-shipping-which-is-better) - Pay for shipping with cryptocurrency.*
