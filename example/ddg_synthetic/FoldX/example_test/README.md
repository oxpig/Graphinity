## Graphinity inference: test example

### Data
The parquet files for the test example, corresponding to the PDBs in Synthetic_FoldX_ddG-example_test-w_paths.csv, are in data/pdb_wt/ and data/pdb_mut/. These were generated by processing (atom typing) the input PDB files using src/ddg_regression/base/dataset.py. NB the parquet files have a smaller file size than the corresponding PDB files and inference is faster when starting with pre-processed files.

### Running Graphinity inference

From the root directory of the repository, run:

CPU-only:
```
python3 src/ddg_regression/graphinity_inference.py -c example/ddg_synthetic/FoldX/example_test/configs/config-example_test.yaml
```

With a GPU:
```
python3 src/ddg_regression/graphinity_inference.py -c example/ddg_synthetic/FoldX/example_test/configs/config-example_test-gpu.yaml
```

This test took less than 20 seconds to run with 1 CPU (on Linux and Mac) and 1 GPU + 1 CPU (on Linux).

The expected outputs are included in outputs/preds_Graphinity-example_test.csv.