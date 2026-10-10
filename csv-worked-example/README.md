# CSV comparison worked example

Two small **synthetic** CSV snapshots demonstrate added, deleted, modified, and unchanged records. No personal or customer data is included.

## Inputs and expected differences

Download [old.csv](old.csv) and [new.csv](new.csv) from this directory. Both files use UTF-8, have the same header **id,name,qty**, and keep IDs such as **001** as strings.

| ID | Expected result | Details |
| --- | --- | --- |
| 001 | Modified | qty changes from 10 to 11 |
| 002 | Unchanged | pen, qty 2 in both snapshots |
| 003 | Deleted | notebook exists only in old.csv |
| 004 | Added | eraser exists only in new.csv |

Expected counts: **1 added, 1 deleted, 1 modified, 1 unchanged, 1 changed field**. [expected.json](expected.json) contains the exact expected strings and counts.

## Try the example

1. [Open HaoToolbox's English CSV comparison tool](https://haotoolbox.com/en/tools/csv-diff/).
2. Choose old.csv as the old version and new.csv as the new version.
3. Select **Compare and create report**. Inspect the previews or download the four-sheet XLSX report: Summary, Added, Deleted, Modified.

## Input rules and limits

- The first column must contain a nonblank, unique ID. Both files must have identical headers in identical order.
- UTF-8 CSV only; at most 128 KiB and 500 records including the header per file, with 2–20 columns.
- IDs and values are compared as exact strings, including leading zeros and whitespace. Record order is ignored.
- Headers must be nonblank and unique; the reserved header **__record** is not allowed.
- Up to 2,000 changed fields and an 8 MiB report. Oversized or malformed inputs stop without a partial report. Previews show at most 10 data records per sheet; the report contains the full accepted result.

## Privacy and evidence

Selected files are processed in your browser and are not uploaded by the comparison tool. Loading the page still requests the site and scripts; it is not an offline application. The English tool page has no analytics script. Reports contain source filenames, hashes, and changed source values: review them before sharing. Native desktop Excel display has not been verified.

The first two records reuse the accepted HaoToolbox C130 synthetic example. Records 003 and 004 are additional synthetic examples to show deletion and addition; this four-file delivery is checked against the existing comparison core, without introducing a new algorithm.

This is a reproducible example, not evidence of GitHub search ranking, site visitor numbers, or third-party endorsement.
