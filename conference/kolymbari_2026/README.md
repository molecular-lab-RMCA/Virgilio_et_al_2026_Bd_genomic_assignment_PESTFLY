# Kolymbari 2026 - refreshed B. dorsalis WGS analysis

This branch is for development and review of a *new* local-analysis snapshot. Do not overwrite the frozen v1.04 outputs on main.

## Input candidate

NAS (read-only): `\\NASBIOCOL250\Molecular-genetic data\Projects\2025_PESTFLY_Bdorsalis\20_read2tree_output\30_output_step3\000_merged_WGS_20261006`

WSL mount: `/mnt/nasbiocol250/Projects/2025_PESTFLY_Bdorsalis/20_read2tree_output/30_output_step3/000_merged_WGS_20261006`

Local input (outside Git): `/mnt/d/PESTFLY_local_data/Bdorsalis/000_merged_WGS_20261006`

The transfer script is supplied separately for first workstation setup. The script must be committed under `conference/kolymbari_2026/scripts/sync_bd_wgs_20261006.sh` before using the commands below.

## First local commands

```bash
sudo mkdir -p /mnt/nasbiocol250
sudo mount -t drvfs '\\NASBIOCOL250\Molecular-genetic data' /mnt/nasbiocol250
SCRIPT=conference/kolymbari_2026/scripts/sync_bd_wgs_20261006.sh
bash "$SCRIPT" --inspect
bash "$SCRIPT" --dry-run
bash "$SCRIPT" --apply
bash "$SCRIPT" --verify
```

Review free disk space before apply. Keep large alignments, original read2tree data, raw genomic files, caches and bulk results outside the repository. Version scripts, documented parameters, lightweight verified summaries and selected figures.

## Analysis sequence

1. Inspect the local dataset's ortholog files, sample labels, reference/query metadata and checksums.
2. Compare the October 6 merged dataset with the frozen public v1.04 snapshot and the 440-specimen extended dataset. Do not presume equivalence.
3. Develop updated SNP-panel and assignment scripts on this branch; run them locally into a separate output directory (never the v1.04 `results/`).
4. Check macroregion/subregion validation, reference coverage, country/site holdout, and query reporting before creating conference figures.

**Status:** Branch prepared. The actual NAS directory has not been accessed from ChatGPT; local transfer and scientific data audit remain to be run on the RMCA workstation.
