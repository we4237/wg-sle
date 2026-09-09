# WG-SLE

This is the official research repository for the WG-SLE study. At present, it provides only the DeepShip and ShipsEar task3 recording-level training/evaluation partitions used in the study. Source code will be added in a future release; no audio recordings, model weights, or experiment outputs are redistributed here.

## Contents

- `deepship/`: DeepShip split files for four-class recognition (cargo, passenger ship, tanker, and tug).
- `shipsear/`: ShipsEar split files for five-class recognition (small motor vessel, small fishing vessel, passenger vessel, tugboat, and ambient background).
- `target_train_data.json` and `target_eval_data.json`: the task3 clip-level training and evaluation manifests, with dataset-relative paths and class identifiers.
- `target_valid_data.json`: a byte-identical alias of `target_eval_data.json` retained only for compatibility with the training framework; it is not an independent validation partition.
- `split_manifest.json`: task3 partition metadata, counts, checksums, and recording identifiers.
- `leakage_report.json`: recording- and clip-overlap checks for the task3 training/evaluation split, together with verification of the validation-file alias.
- `label_map.csv`: mapping from manifest class identifiers to display names.

The released files reproduce the task3 protocol described in the manuscript: recordings are assigned before segmentation to an approximate 7:3 training/evaluation split, so clips derived from one recording do not cross those two partitions. The framework-level validation manifest duplicates the evaluation manifest and must not be interpreted as an independent partition. DeepShip recordings are represented by non-overlapping 30 s clips; ShipsEar recordings are represented by 30 s clips with 50% overlap within each partition.

## Source data

The original audio is not included. Obtain DeepShip from the [dataset authors' repository](https://github.com/irfankamboh/DeepShip) and ShipsEar from the [Universidade de Vigo underwater-noise database](https://underwaternoise.atlanttic.uvigo.es/), subject to the original providers' access conditions and terms of use. The dataset-relative `pt` entries identify the processed clips used by the study and make the task3 partition membership auditable without exposing machine-specific absolute paths.

## Citation

Please cite the WG-SLE article associated with these splits, together with the original DeepShip and ShipsEar dataset papers. The article citation will be added after publication.
