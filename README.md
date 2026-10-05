# AMA FreightOS

AMA FreightOS is the operational platform for AMA Shipping's freight-forwarding and customs-clearing workflow.

## Current architecture

`Public Front Door → Inquiry/Booking → Shipment Digital Twin → Workflow Desk → Operations Brain → Human Approval → Queued Action → Worker → Audit/Notification`

## V6.1 baseline

V6.1 establishes the first production-oriented shipment operations slice:

- PostgreSQL persistence
- Authenticated HttpOnly sessions and RBAC
- Organization-isolated shipments
- Workflow proposals and explicit human approval
- Redis/BullMQ background processing
- S3-compatible document storage
- Audit and notification records
- V5 workflow-engine integration boundary

## Development

```bash
npm ci
npm run migrate
npm test
npm run build
npm run dev
```

Production deployment requires PostgreSQL, Redis, and S3-compatible object storage. The deterministic workflow fallback must remain disabled in production.
