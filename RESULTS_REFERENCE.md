# Results: 217 GEMM / cuBLAS Microbenchmark

**Main goal:** Measure GEMM throughput across dtypes/shapes  
**Tools:** Compile cublas_gemm.cu with nvcc; run bin/cublas_gemm twice via collect_cublas_gemm.py

Reference results measured by the maintainer on the system shown in each section (generator TEMPLATE_00_145 · recorded 2026-11-17). Your own runs write `results/RESULTS_ACTUAL.md` in the same format.

> Smoke runs use deliberately small sizes. They check that the workload installs and runs end to end; their numbers are not performance results. Baseline and extended are.

<!-- profile:smoke -->
## smoke

- **System:** 1× NVIDIA H100 NVL (95830 MiB) · AMD EPYC 9374F 32-Core Processor · Ubuntu 24.04.5 LTS · kernel 6.8.0-138-generic · driver 595.112.07
- **Run:** 2026-11-17T11:09:11Z · status **PASS** (exit 0)
- **Time (mm:ss):** setup 00:29 · benchmark 00:01 · whole run 00:35
- **Source:** run 217_20261117_110911
- **Command:** `bash run_benchmark.sh --smoke --dtype f32_r --M 64 --N 64 --K 64 --transposeA N --transposeB N --alpha 1 --beta 0 --lda 64 --ldb 64 --ldc 64 --batch-count 1 --warmup-iters 2 --num-iterations 2 --norm-check 1`

| # | Metric | Result |
|---|---|---|
| 1 | Achieved compute throughput, TFLOP/s (achieved_compute_tflops) | 0.050882 |
| 2 | Kernel execution time (kernel_time_msec) | 0.010304 |
| 3 | Minimum operand traffic, GB/s (minimum_operand_traffic_gb_s) | 4.770186 |
| 4 | Relative L1 of checked columns (relative_l1_checked_columns) | 2.59177062e-08 |
| 5 | Relative L2 error of checked columns (norm_error_2) | 5.07249905e-08 |
<!-- /profile:smoke -->
