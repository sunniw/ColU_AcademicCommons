# Columbia University Academic Commons Weeding Project
- First created: 2022-11-10.
- Version 2 completed: 2022-12-23.
- Last edit: 2023-04-18 (README.md)

This is a project of weeding legacy duplicate materials from Columbia University Libraries' Academic Commons done in Fall 2022.

A list of duplicate resources are identified on Academic Commons (AC) — the digital scholarship repository of Columbia University. Duplicates are flagged and pointed to the ones that would be remained in the repository before removing from users' view. Stats of the duplicates will be merged on child access level. DOIs of those removed resources will be redirected on to the available ones.

This project was presented as a poster at Code4Lib on 16 March 2023, at Princeton University, which is available in [OSF](https://osf.io/ufk7c/ "OSF"). It will also be presented as a short session at the Southern Miss Institutional Repository Conference (SMIRC), 28 April 2023, at the University of Southern Mississippi.

## Dupe merge stat flowchart.pdf

Duplicate items on AC carry usage stats, which we wanted to keep and merge with the items that will stay published on the platform. This flowchart accompanies version 2 of the script that shows how to merge the stats on child asset level before unpublish them with their parent items.

## all_dupe_and_related.ipynb

From the duplicate list of parent items, this script searches their children (assets) from the repository. The resulting list will be exported as 2 CSV files. On Hyacinth — the backend digital object management platform — the exported list will be used to merge stats of duplicates before unpublished. On DataCite, the duplicates will be redirected to appropriate resources.

**Outputs:**
- 1 CSV file for Hyacinth
- 1 CSV file for DataCite

**Main Processes:**
1. Import (a) the complete data exported from AC, and (b) the list of current duplicates identified in AC.
2. Select items from (b) that are marked as duplicates ('Yes dupe').
3. Look up bulk AC data for duplicates' child assets.
4. Output as 2 CSV, one for Hyacinth, the other one for DataCite.

## all_dupe_and_related_v2.ipynb

Adding a new part in [21] to do a child-level mapping from the duplicate asset to its equivalent keeping asset. This mapping facilitates Hyacinth to merge usage stats before unpublishing the duplicates. The mapping will skip any originally unpublished duplicates and metadata XML.

**Outputs:**
- 1 additional CSV file for Hyacinth

**Main Processes:**
1. Collect a list of child assets of the stay-published parent items.
2. Continue to work on the duplicate child assets found before this step, while skipping those that had not been published on Academic Commons, and the duplicate items’ metadata XML, which were unintentionally published.
3. Mapping the two sets of assets.
4. Output as a CSV file for Hyacinth.

