# NYC Taxi Public Summary

Validated monthly aggregates from an independent Databricks lakehouse learning project. This repository supplies report data for a portfolio case study, not raw trip records or an official City report.

## Report

Use [reports/snapshot.json](reports/snapshot.json). Source periods identify the input file month. Counts reconcile Bronze = Silver + quarantine and Silver = Gold. Source amounts are represented as integer cents strings; they are not validated net revenue.

The initial reviewed report covers January 2024 through August 2026: 119,595,677 Bronze rows, 115,842,411 accepted rows, 3,753,266 quarantined rows and USD 3,388,158,595.79 in accepted source total_amount. Global persisted-table SQL totals were reviewed October 18, 2026.

## Dates and updates

`evidenceThroughUtc` is the reconciliation observation time; `generatedAtUtc` is export time. Neither is a daily Job heartbeat or proof of a new full-table audit. Reports are monthly batch evidence, not a real-time trip feed. Unchanged evidence skips new report commits.

As of October 19, 2026, public report delivery is available. Adding the post-pipeline publishing task and demonstrating its first scheduled run remain pending.

## Other folders

`_staging/` holds the same allowlisted summary during verified promotion. `_connection_test/` contains a harmless historical connection fixture, not real trip data. Consumers should use only `reports/snapshot.json`.

## Source and limitations

Source: [NYC TLC trip-record data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page). These are transformed, policy-filtered learning-project results, not official City statistics. No affiliation with or endorsement by NYC or Databricks is implied. Source accuracy and completeness are not guaranteed. No credentials, private workspace URLs or raw trip rows belong in this repository.
