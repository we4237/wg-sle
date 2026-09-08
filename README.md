# WG-SLE data splits

This repository provides the exact record-disjoint DeepShip and ShipsEar data partitions used in the WG-SLE study. It contains partition metadata only; no audio recordings, model weights, or experiment outputs are redistributed.

## Contents

- `deepship/`: DeepShip split files for four-class recognition (cargo, passenger ship, tanker, and tug).
- `shipsear/`: ShipsEar split files for five-class recognition (small motor vessel, small fishing vessel, passenger vessel, tugboat, and ambient background).
- `target_train_data.json`, `target_valid_data.json`, and `target_eval_data.json`: clip-level manifests with relative paths and class identifiers.
- `split_manifest.json`: seed, partition sizes, source-manifest checksums, and the recording identifiers assigned to each partition.
- `leakage_report.json`: recording- and clip-overlap checks across partitions.
- `label_map.csv`: mapping from manifest class identifiers to display names.

The released partitions use random seed 42. Recordings are assigned to partitions before segmentation, so clips derived from the same source recording do not cross the training, validation, and evaluation partitions. DeepShip recordings are represented by non-overlapping 30 s clips; ShipsEar recordings are represented by 30 s clips with 50% overlap within each partition.

## Source data

The original audio is not included. Obtain DeepShip from the [dataset authors' repository](https://github.com/irfankamboh/DeepShip) and ShipsEar from the [Universidade de Vigo underwater-noise database](https://underwaternoise.atlanttic.uvigo.es/), subject to the original providers' access conditions and terms of use. The relative `pt` entries identify the processed clips used by the study and are intended to make the experimental partitioning auditable and reproducible.

## Citation

Please cite the WG-SLE article associated with these splits, together with the original DeepShip and ShipsEar dataset papers. The article citation will be added after publication.
