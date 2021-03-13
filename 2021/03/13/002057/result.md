# Benchmark result

* Pull request commit: [`f51e2b8342e659b52d9c6e8b2611dcef5fe159f5`](https://github.com/JuliaFolds/FLoops.jl/commit/f51e2b8342e659b52d9c6e8b2611dcef5fe159f5)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/33> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 13 Mar 2021 - 00:18
    - Baseline: 13 Mar 2021 - 00:20
* Package commits:
    - Target: 5bd354
    - Baseline: 4dd89a
* Julia commits:
    - Target: 44fa15
    - Baseline: 44fa15
* Julia command flags:
    - Target: None
    - Baseline: None
* Environment variables:
    - Target: `OMP_NUM_THREADS => 1` `JULIA_NUM_THREADS => 2`
    - Baseline: `OMP_NUM_THREADS => 1` `JULIA_NUM_THREADS => 2`

## Results
A ratio greater than `1.0` denotes a possible regression (marked with :x:), while a ratio less
than `1.0` denotes a possible improvement (marked with :white_check_mark:). Only significant results - results
that indicate possible regressions or improvements - are shown below (thus, an empty table means that all
benchmark results remained invariant between builds).

| ID                                                                | time ratio                   | memory ratio                 |
|-------------------------------------------------------------------|------------------------------|------------------------------|
| `["parallel_findminmax", "threaded"]`                             |                   0.99 (5%)  | 0.47 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "sequential"]`                       |                   1.00 (5%)  |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded"]`                         |                   1.02 (5%)  |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.83 (5%) :white_check_mark: |                   0.99 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.00 (1%) :white_check_mark: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |                1.79 (5%) :x: |                 Inf (1%) :x: |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             | 0.90 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            |                1.10 (5%) :x: |                   1.00 (1%)  |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
- `["parallel_triangular_sum"]`
- `["parallel_triangular_sum", "threaded_nest"]`
- `["sum", ":label => \"BlockVector\""]`
- `["sum", ":label => \"Vector\""]`
- `["sum", ":label => \"filter\""]`
- `["sum", ":label => \"flatten\""]`

## Julia versioninfo

### Target
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.2 LTS
  uname: Linux 5.4.0-1040-azure #42-Ubuntu SMP Fri Feb 5 15:39:06 UTC 2021 x86_64 x86_64
  CPU: AMD EPYC 7452 32-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2345 MHz      11125 s         15 s        970 s     103439 s          0 s
       #2  2345 MHz       9571 s          6 s        926 s     105445 s          0 s
       #3  2345 MHz       7495 s          4 s        856 s     107077 s          0 s
       #4  2345 MHz       5957 s          4 s        659 s     109468 s          0 s
       
  Memory: 15.638629913330078 GB (12156.58984375 MB free)
  Uptime: 1170.0 sec
  Load Avg:  1.27001953125  0.76904296875  0.36572265625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, znver1)
```

### Baseline
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.2 LTS
  uname: Linux 5.4.0-1040-azure #42-Ubuntu SMP Fri Feb 5 15:39:06 UTC 2021 x86_64 x86_64
  CPU: AMD EPYC 7452 32-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2345 MHz      12716 s         15 s       1055 s     115191 s          0 s
       #2  2345 MHz      16925 s          6 s       1096 s     111364 s          0 s
       #3  2345 MHz       8824 s          4 s        914 s     119125 s          0 s
       #4  2345 MHz      10870 s          4 s        870 s     117779 s          0 s
       
  Memory: 15.638629913330078 GB (12149.60546875 MB free)
  Uptime: 1304.0 sec
  Load Avg:  1.26708984375  0.92138671875  0.4765625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, znver1)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 13 Mar 2021 - 0:18
* Package commit: 5bd354
* Julia commit: 44fa15
* Julia command flags: None
* Environment variables: `OMP_NUM_THREADS => 1` `JULIA_NUM_THREADS => 2`

## Results
Below is a table of this job's results, obtained by running the benchmarks.
The values listed in the `ID` column have the structure `[parent_group, child_group, ..., key]`, and can be used to
index into the BaseBenchmarks suite to retrieve the corresponding benchmarks.
The percentages accompanying time and memory values in the below table are noise tolerances. The "true"
time/memory value for a given benchmark is expected to fall within this percentage of the reported value.
An empty cell means that the value was zero.

| ID                                                                | time            | GC time | memory          | allocations |
|-------------------------------------------------------------------|----------------:|--------:|----------------:|------------:|
| `["parallel_findminmax", "sequential"]`                           | 474.015 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 265.408 μs (5%) |         |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.097 ms (5%) |         |   8.93 MiB (1%) |      231170 |
| `["parallel_triangular_sum", "threaded"]`                         |   2.934 ms (5%) |         |   8.93 MiB (1%) |      231223 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   1.649 ms (5%) |         |   8.98 MiB (1%) |      232053 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   1.718 ms (5%) |         |   9.05 MiB (1%) |      232932 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   1.917 ms (5%) |         |   9.25 MiB (1%) |      235593 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   3.225 μs (5%) |         |  15.88 KiB (1%) |           2 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  24.400 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 880.412 ns (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 881.151 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 861.306 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   1.970 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   1.790 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 161.705 μs (5%) |         | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
- `["parallel_triangular_sum"]`
- `["parallel_triangular_sum", "threaded_nest"]`
- `["sum", ":label => \"BlockVector\""]`
- `["sum", ":label => \"Vector\""]`
- `["sum", ":label => \"filter\""]`
- `["sum", ":label => \"flatten\""]`

## Julia versioninfo
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.2 LTS
  uname: Linux 5.4.0-1040-azure #42-Ubuntu SMP Fri Feb 5 15:39:06 UTC 2021 x86_64 x86_64
  CPU: AMD EPYC 7452 32-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2345 MHz      11125 s         15 s        970 s     103439 s          0 s
       #2  2345 MHz       9571 s          6 s        926 s     105445 s          0 s
       #3  2345 MHz       7495 s          4 s        856 s     107077 s          0 s
       #4  2345 MHz       5957 s          4 s        659 s     109468 s          0 s
       
  Memory: 15.638629913330078 GB (12156.58984375 MB free)
  Uptime: 1170.0 sec
  Load Avg:  1.27001953125  0.76904296875  0.36572265625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, znver1)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 13 Mar 2021 - 0:20
* Package commit: 4dd89a
* Julia commit: 44fa15
* Julia command flags: None
* Environment variables: `OMP_NUM_THREADS => 1` `JULIA_NUM_THREADS => 2`

## Results
Below is a table of this job's results, obtained by running the benchmarks.
The values listed in the `ID` column have the structure `[parent_group, child_group, ..., key]`, and can be used to
index into the BaseBenchmarks suite to retrieve the corresponding benchmarks.
The percentages accompanying time and memory values in the below table are noise tolerances. The "true"
time/memory value for a given benchmark is expected to fall within this percentage of the reported value.
An empty cell means that the value was zero.

| ID                                                                | time            | GC time    | memory          | allocations |
|-------------------------------------------------------------------|----------------:|-----------:|----------------:|------------:|
| `["parallel_findminmax", "sequential"]`                           | 472.914 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 268.508 μs (5%) |            |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.088 ms (5%) |            |   8.80 MiB (1%) |      223019 |
| `["parallel_triangular_sum", "threaded"]`                         |   2.879 ms (5%) |            |   8.81 MiB (1%) |      223073 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   1.713 ms (5%) |            |   8.89 MiB (1%) |      224868 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   2.070 ms (5%) |            |   9.10 MiB (1%) |      228680 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |    9.885 s (5%) | 359.948 ms |   1.86 GiB (1%) |    28399319 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   1.800 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  24.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   1.800 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 146.604 μs (5%) |            | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
- `["parallel_triangular_sum"]`
- `["parallel_triangular_sum", "threaded_nest"]`
- `["sum", ":label => \"BlockVector\""]`
- `["sum", ":label => \"Vector\""]`
- `["sum", ":label => \"filter\""]`
- `["sum", ":label => \"flatten\""]`

## Julia versioninfo
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.2 LTS
  uname: Linux 5.4.0-1040-azure #42-Ubuntu SMP Fri Feb 5 15:39:06 UTC 2021 x86_64 x86_64
  CPU: AMD EPYC 7452 32-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2345 MHz      12716 s         15 s       1055 s     115191 s          0 s
       #2  2345 MHz      16925 s          6 s       1096 s     111364 s          0 s
       #3  2345 MHz       8824 s          4 s        914 s     119125 s          0 s
       #4  2345 MHz      10870 s          4 s        870 s     117779 s          0 s
       
  Memory: 15.638629913330078 GB (12149.60546875 MB free)
  Uptime: 1304.0 sec
  Load Avg:  1.26708984375  0.92138671875  0.4765625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, znver1)
```

---
# Runtime information
| Runtime Info | |
|:--|:--|
| BLAS #threads | 4 |
| `BLAS.vendor()` | `openblas64` |
| `Sys.CPU_THREADS` | 4 |

`lscpu` output:

    Architecture:                    x86_64
    CPU op-mode(s):                  32-bit, 64-bit
    Byte Order:                      Little Endian
    Address sizes:                   48 bits physical, 48 bits virtual
    CPU(s):                          4
    On-line CPU(s) list:             0-3
    Thread(s) per core:              2
    Core(s) per socket:              2
    Socket(s):                       1
    NUMA node(s):                    1
    Vendor ID:                       AuthenticAMD
    CPU family:                      23
    Model:                           49
    Model name:                      AMD EPYC 7452 32-Core Processor
    Stepping:                        0
    CPU MHz:                         2345.608
    BogoMIPS:                        4691.21
    Hypervisor vendor:               Microsoft
    Virtualization type:             full
    L1d cache:                       64 KiB
    L1i cache:                       64 KiB
    L2 cache:                        1 MiB
    L3 cache:                        16 MiB
    NUMA node0 CPU(s):               0-3
    Vulnerability Itlb multihit:     Not affected
    Vulnerability L1tf:              Not affected
    Vulnerability Mds:               Not affected
    Vulnerability Meltdown:          Not affected
    Vulnerability Spec store bypass: Mitigation; Speculative Store Bypass disabled via prctl and seccomp
    Vulnerability Spectre v1:        Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Vulnerability Spectre v2:        Mitigation; Full AMD retpoline, STIBP disabled, RSB filling
    Vulnerability Srbds:             Not affected
    Vulnerability Tsx async abort:   Not affected
    Flags:                           fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx mmxext fxsr_opt pdpe1gb rdtscp lm rep_good nopl cpuid extd_apicid pni pclmulqdq ssse3 fma cx16 sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm cmp_legacy cr8_legacy abm sse4a misalignsse 3dnowprefetch osvw topoext ssbd vmmcall fsgsbase bmi1 avx2 smep bmi2 rdseed adx smap clflushopt clwb sha_ni xsaveopt xsavec xgetbv1 xsaves xsaveerptr arat umip rdpid
    

| Cpu Property       | Value                                                   |
|:------------------ |:------------------------------------------------------- |
| Brand              | AMD EPYC 7452 32-Core Processor                         |
| Vendor             | :AMD                                                    |
| Architecture       | :Zen                                                    |
| Model              | Family: 0x8f, Model: 0x31, Stepping: 0x00, Type: 0x00   |
| Cores              | 4 physical cores, 4 logical cores (on executing CPU)    |
|                    | No Hyperthreading hardware capability detected          |
| Clock Frequencies  | Not supported by CPU                                    |
| Data Cache         | Level 1:3 : (32, 512, 16384) kbytes                     |
|                    | 64 byte cache line size                                 |
| Address Size       | 48 bits virtual, 48 bits physical                       |
| SIMD               | 256 bit = 32 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

