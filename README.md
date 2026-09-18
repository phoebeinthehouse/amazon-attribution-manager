# Amazon Attribution QA

A lightweight reconciliation dashboard for Manyo's US Meta → Amazon Attribution workflow.

## Purpose

This dashboard compares `meta-raw-new` and `amz-raw-new` at the parsed key:

```
creative name + owner + product
```

It highlights:

- matched ads
- Meta ads not confirmed in the Amazon raw data
- Amazon rows not found in the selected Meta period
- names that cannot be parsed to ad level
- spend, clicks, purchases, and KRW revenue for reconciliation

## Important interpretation

`Amazon 미확인` does **not** prove that an Attribution link is missing. It means the selected Amazon raw data does not contain the same parsed ad key. Confirm the link mapping or Amazon creation result before classifying it as missing.

## Data sources

The page reads the existing Google Apps Script endpoint in parallel:

- `meta-raw-new`
- `amz-raw-new`

No Amazon credentials or tokens are stored in this repository.

## Performance

- no image data
- no chart library
- two parallel data requests
- 10-minute browser cache
- default view: latest 14 days

## Deployment

Publish `main` / root through GitHub Pages.
