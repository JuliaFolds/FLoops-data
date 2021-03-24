# Benchmark result

* Pull request commit: [`3a6ee365bd42fc6da87e4c7eb4db4f41d5312c7a`](https://github.com/JuliaFolds/FLoops.jl/commit/3a6ee365bd42fc6da87e4c7eb4db4f41d5312c7a)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/77> (Hoist out threadid() in FAQ sample code)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 24 Mar 2021 - 01:12
    - Baseline: 24 Mar 2021 - 01:14
* Package commits:
    - Target: fc0e47
    - Baseline: 7a3f6f
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
| `["parallel_triangular_sum", "sequential"]`                       | 0.95 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded"]`                         | 0.90 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` | 0.91 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      | 0.93 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |                1.09 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 0.92 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 0.81 (5%) :white_check_mark: |                   1.00 (1%)  |

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
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      23424 s         17 s       1814 s      14886 s          0 s
       #2  2294 MHz      20787 s          7 s       1860 s      17842 s          0 s
       
  Memory: 6.791378021240234 GB (3390.09765625 MB free)
  Uptime: 417.0 sec
  Load Avg:  1.29833984375  1.1591796875  0.62158203125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

### Baseline
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.2 LTS
  uname: Linux 5.4.0-1040-azure #42-Ubuntu SMP Fri Feb 5 15:39:06 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      30582 s         17 s       1908 s      19193 s          0 s
       #2  2294 MHz      28082 s          7 s       2050 s      21925 s          0 s
       
  Memory: 6.791378021240234 GB (3287.23046875 MB free)
  Uptime: 532.0 sec
  Load Avg:  1.3017578125  1.193359375  0.7021484375
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 24 Mar 2021 - 1:12
* Package commit: fc0e47
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
| `["parallel_findminmax", "sequential"]`                           | 438.392 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 283.996 μs (5%) |         |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.917 ms (5%) |         |   8.80 MiB (1%) |      223019 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.706 ms (5%) |         |   8.81 MiB (1%) |      223073 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.506 ms (5%) |         |   8.89 MiB (1%) |      224868 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   2.954 ms (5%) |         |   9.10 MiB (1%) |      228681 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   4.056 ms (5%) |         |   9.63 MiB (1%) |      238727 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   1.670 μs (5%) |         |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  29.299 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 871.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 824.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 812.315 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.167 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   1.760 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 172.497 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      23424 s         17 s       1814 s      14886 s          0 s
       #2  2294 MHz      20787 s          7 s       1860 s      17842 s          0 s
       
  Memory: 6.791378021240234 GB (3390.09765625 MB free)
  Uptime: 417.0 sec
  Load Avg:  1.29833984375  1.1591796875  0.62158203125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 24 Mar 2021 - 1:14
* Package commit: 7a3f6f
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
| `["parallel_findminmax", "sequential"]`                           | 438.495 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 286.996 μs (5%) |            |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   4.125 ms (5%) |            |   8.80 MiB (1%) |      223019 |
| `["parallel_triangular_sum", "threaded"]`                         |   4.107 ms (5%) |            |   8.81 MiB (1%) |      223073 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.747 ms (5%) |            |   8.89 MiB (1%) |      224869 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |    6.793 s (5%) | 199.808 ms | 794.45 MiB (1%) |    12092772 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   16.216 s (5%) | 495.346 ms |   1.86 GiB (1%) |    28399314 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   1.800 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  29.299 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 800.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 899.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 999.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.199 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   1.799 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 165.299 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      30582 s         17 s       1908 s      19193 s          0 s
       #2  2294 MHz      28082 s          7 s       2050 s      21925 s          0 s
       
  Memory: 6.791378021240234 GB (3287.23046875 MB free)
  Uptime: 532.0 sec
  Load Avg:  1.3017578125  1.193359375  0.7021484375
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Runtime information
| Runtime Info | |
|:--|:--|
| BLAS #threads | 2 |
| `BLAS.vendor()` | `openblas64` |
| `Sys.CPU_THREADS` | 2 |

`lscpu` output:

    Architecture:                    x86_64
    CPU op-mode(s):                  32-bit, 64-bit
    Byte Order:                      Little Endian
    Address sizes:                   46 bits physical, 48 bits virtual
    CPU(s):                          2
    On-line CPU(s) list:             0,1
    Thread(s) per core:              1
    Core(s) per socket:              2
    Socket(s):                       1
    NUMA node(s):                    1
    Vendor ID:                       GenuineIntel
    CPU family:                      6
    Model:                           79
    Model name:                      Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz
    Stepping:                        1
    CPU MHz:                         2294.688
    BogoMIPS:                        4589.37
    Hypervisor vendor:               Microsoft
    Virtualization type:             full
    L1d cache:                       64 KiB
    L1i cache:                       64 KiB
    L2 cache:                        512 KiB
    L3 cache:                        50 MiB
    NUMA node0 CPU(s):               0,1
    Vulnerability Itlb multihit:     KVM: Vulnerable
    Vulnerability L1tf:              Mitigation; PTE Inversion
    Vulnerability Mds:               Mitigation; Clear CPU buffers; SMT Host state unknown
    Vulnerability Meltdown:          Mitigation; PTI
    Vulnerability Spec store bypass: Vulnerable
    Vulnerability Spectre v1:        Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Vulnerability Spectre v2:        Mitigation; Full generic retpoline, STIBP disabled, RSB filling
    Vulnerability Srbds:             Not affected
    Vulnerability Tsx async abort:   Mitigation; Clear CPU buffers; SMT Host state unknown
    Flags:                           fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology cpuid pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase bmi1 hle avx2 smep bmi2 erms invpcid rtm rdseed adx smap xsaveopt md_clear
    

| Cpu Property       | Value                                                   |
|:------------------ |:------------------------------------------------------- |
| Brand              | Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz               |
| Vendor             | :Intel                                                  |
| Architecture       | :Broadwell                                              |
| Model              | Family: 0x06, Model: 0x4f, Stepping: 0x01, Type: 0x00   |
| Cores              | 2 physical cores, 2 logical cores (on executing CPU)    |
|                    | No Hyperthreading hardware capability detected          |
| Clock Frequencies  | Not supported by CPU                                    |
| Data Cache         | Level 1:3 : (32, 256, 51200) kbytes                     |
|                    | 64 byte cache line size                                 |
| Address Size       | 48 bits virtual, 46 bits physical                       |
| SIMD               | 256 bit = 32 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

