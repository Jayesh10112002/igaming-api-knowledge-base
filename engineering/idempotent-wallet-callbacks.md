---
layout: article
title: "Designing Idempotent Wallet Callbacks for Gaming APIs"
description: "Use durable transaction identities, atomic updates, and reconciliation to handle duplicate wallet callbacks safely."
category: "Engineering"
permalink: /engineering/idempotent-wallet-callbacks/
date: 2026-10-17
---

Wallet callbacks are distributed transactions across services. A caller may time out even after the receiving service commits a transaction, so retry behavior must be designed deliberately.

## Why retries create risk

A debit request may reach the wallet service and commit, but the response can be lost. The provider cannot distinguish a failed operation from a successful operation with a lost response and may retry. If the retry becomes a new debit, the player may be charged twice.

## Use stable transaction identities

Use a provider-defined transaction ID or a carefully specified idempotency key. Enforce it with a unique constraint in durable storage, not just an application-level check. When a duplicate arrives, compare player, currency, amount, and operation type. Reusing an identifier with conflicting details should be treated as an integrity error.

## Make balance updates atomic

A read-then-write balance sequence can fail under concurrency. Two simultaneous debits may both read the same balance. Use a conditional atomic update or database transaction that checks the balance and applies the debit as one consistent operation.

## Keep an auditable ledger

Store the original transaction and any reversal as distinct linked events. Avoid deleting a completed transaction to represent a refund. A durable ledger helps reconstruct balance changes and investigate disputes.

## Define states and reconciliation

For unresolved workflows, use explicit states and controlled transitions. A timeout does not automatically imply failure. Compare internal records with provider reports to identify missing events, mismatched amounts, and unresolved outcomes.

## Test failure scenarios

- Repeated delivery of the same request
- Concurrent debits for one player
- Timeout after commit but before response
- Database unavailability or worker restart
- Duplicate refunds or reversals
- Reuse of a transaction ID with different parameters

Monitor duplicate attempts, callback latency, timeouts, database conflicts, unresolved transactions, and reconciliation differences. Avoid logging credentials or unnecessary personal data. Validate behavior in a sandbox and confirm the formal transaction contract before launch.
