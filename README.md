# Columbia University Academic Commons Weeding Project
A project of weeding legacy duplicate materials from Academic Commons, Fall 2022.

A list of duplicate resources are identified from Academic Commons (AC) — the digital scholarship repository of Columbia University. Duplicates are flagged and pointed to the ones that would be remained in the repository for further actions.

## all_dupe_and_related.ipynb

From the duplicate list of parent items, this script searches for their children (assets) from the repository. The resulting list will be exported as 2 CSV files. On Hyacinth — the backend digital object management platform — the exported list will be used to merge stats of duplicates before removal. On DataCite, the duplicates will be redirected to appropriate resources.

**Outputs:**
- 1 CSV file for Hyacinth
- 1 CSV file for DataCite

**Main Processes:**
1. Import (a) the complete data exported from AC, and (b) the list of current duplicates identified in AC.
2. Select items from (b) that are marked as duplicates ('Yes dupe').
3. Look up bulk AC data for duplicates' child assets.
4. Output as 2 CSV, one for Hyacinth, the other one for DataCite. See descriptions below.
