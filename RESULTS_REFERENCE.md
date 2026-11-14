# Results: 217 GEMM / cuBLAS Microbenchmark

**Main goal:** Measure GEMM throughput across dtypes/shapes  
**Tools:** Compile cublas_gemm.cu with nvcc; run bin/cublas_gemm twice via collect_cublas_gemm.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_140 · recorded 2026-11-13). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 PCIe (81559 MiB) · Intel(R) Xeon(R) Platinum 8352Y CPU @ 2.20GHz · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.91.07
- **Run:** 2026-11-13T20:49:54Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 01:05 · benchmark 00:03 · whole run 01:19
- **Source:** run 217_20261113_204954
- **Command:** `bash run_benchmark.sh --smoke --dtype f32_r --M 64 --N 64 --K 64 --transposeA N --transposeB N --alpha 1 --beta 0 --lda 64 --ldb 64 --ldc 64 --batch-count 1 --warmup-iters 2 --num-iterations 2 --norm-check 1`

| # | Metric | Result |
|---|---|---|
| 1 | Achieved compute throughput, TFLOP/s (achieved_compute_tflops) | 0.02024 |
| 2 | Kernel execution time (kernel_time_msec) | 0.025904 |
| 3 | Minimum operand traffic, GB/s (minimum_operand_traffic_gb_s) | 1.897468 |
| 4 | Relative L1 of checked columns (relative_l1_checked_columns) | 2.59177062e-08 |
| 5 | Relative L2 error of checked columns (norm_error_2) | 5.07249905e-08 |
<!-- /profile:smoke -->
