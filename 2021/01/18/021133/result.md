# Benchmark result

* Pull request commit: [`70f2d811cf24d0d37992bfd14e6ee386ffcbb9ee`](https://github.com/JuliaFolds/FLoops.jl/commit/70f2d811cf24d0d37992bfd14e6ee386ffcbb9ee)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/61> (Use promotion mechanism to automatically choose executor)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 18 Jan 2021 - 02:08
    - Baseline: 18 Jan 2021 - 02:10
* Package commits:
    - Target: c70076
    - Baseline: 69ddf4
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
| `["parallel_findminmax", "sequential"]`                           |                   0.98 (5%)  |                 Inf (1%) :x: |
| `["parallel_triangular_sum", "sequential"]`                       | 0.78 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded"]`                         | 0.79 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` | 0.80 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      | 0.85 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 0.71 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 0.71 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 0.68 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          | 0.68 (5%) :white_check_mark: |                   1.00 (1%)  |

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
      Ubuntu 18.04.5 LTS
  uname: Linux 5.4.0-1036-azure #38~18.04.1-Ubuntu SMP Wed Jan 6 18:26:30 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      20769 s          0 s       1655 s      15026 s          0 s
       #2  2095 MHz      18784 s          0 s       1625 s      17247 s          0 s
       
  Memory: 6.791393280029297 GB (3406.21484375 MB free)
  Uptime: 392.0 sec
  Load Avg:  1.33837890625  0.98828125  0.4814453125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

### Baseline
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 18.04.5 LTS
  uname: Linux 5.4.0-1036-azure #38~18.04.1-Ubuntu SMP Wed Jan 6 18:26:30 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      26243 s          0 s       1826 s      22111 s          0 s
       #2  2095 MHz      28746 s          0 s       1897 s      19753 s          0 s
       
  Memory: 6.791393280029297 GB (3404.46484375 MB free)
  Uptime: 520.0 sec
  Load Avg:  1.3828125  1.11083984375  0.59326171875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 18 Jan 2021 - 2:8
* Package commit: c70076
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
| `["parallel_findminmax", "sequential"]`                           | 507.503 μs (5%) |         |  176 bytes (1%) |           5 |
| `["parallel_findminmax", "threaded"]`                             | 341.101 μs (5%) |         |   3.52 KiB (1%) |          77 |
| `["parallel_triangular_sum", "sequential"]`                       |   2.839 ms (5%) |         |   8.80 MiB (1%) |      223023 |
| `["parallel_triangular_sum", "threaded"]`                         |   2.992 ms (5%) |         |   8.81 MiB (1%) |      223075 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   1.868 ms (5%) |         |   8.89 MiB (1%) |      224873 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   2.131 ms (5%) |         |   9.10 MiB (1%) |      228677 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   3.151 ms (5%) |         |   9.63 MiB (1%) |      238731 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   2.200 μs (5%) |         |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  29.800 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.070 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.070 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   1.420 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.344 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.233 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 136.001 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
      Ubuntu 18.04.5 LTS
  uname: Linux 5.4.0-1036-azure #38~18.04.1-Ubuntu SMP Wed Jan 6 18:26:30 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      20769 s          0 s       1655 s      15026 s          0 s
       #2  2095 MHz      18784 s          0 s       1625 s      17247 s          0 s
       
  Memory: 6.791393280029297 GB (3406.21484375 MB free)
  Uptime: 392.0 sec
  Load Avg:  1.33837890625  0.98828125  0.4814453125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 18 Jan 2021 - 2:10
* Package commit: 69ddf4
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
| `["parallel_findminmax", "sequential"]`                           | 515.306 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 341.304 μs (5%) |            |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.652 ms (5%) |            |   8.80 MiB (1%) |      223019 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.799 ms (5%) |            |   8.81 MiB (1%) |      223073 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.340 ms (5%) |            |   8.89 MiB (1%) |      224869 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |    5.901 s (5%) | 181.488 ms | 779.12 MiB (1%) |    11859493 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   14.286 s (5%) | 460.670 ms |   1.84 GiB (1%) |    28193279 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   2.600 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  29.800 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   2.100 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.300 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   3.300 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 136.101 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
      Ubuntu 18.04.5 LTS
  uname: Linux 5.4.0-1036-azure #38~18.04.1-Ubuntu SMP Wed Jan 6 18:26:30 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      26243 s          0 s       1826 s      22111 s          0 s
       #2  2095 MHz      28746 s          0 s       1897 s      19753 s          0 s
       
  Memory: 6.791393280029297 GB (3404.46484375 MB free)
  Uptime: 520.0 sec
  Load Avg:  1.3828125  1.11083984375  0.59326171875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Runtime information
| Runtime Info | |
|:--|:--|
| BLAS #threads | 2 |
| `BLAS.vendor()` | `openblas64` |
| `Sys.CPU_THREADS` | 2 |

`lscpu` output:

    Architecture:        x86_64
    CPU op-mode(s):      32-bit, 64-bit
    Byte Order:          Little Endian
    CPU(s):              2
    On-line CPU(s) list: 0,1
    Thread(s) per core:  1
    Core(s) per socket:  2
    Socket(s):           1
    NUMA node(s):        1
    Vendor ID:           GenuineIntel
    CPU family:          6
    Model:               85
    Model name:          Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz
    Stepping:            4
    CPU MHz:             2095.076
    BogoMIPS:            4190.15
    Hypervisor vendor:   Microsoft
    Virtualization type: full
    L1d cache:           32K
    L1i cache:           32K
    L2 cache:            1024K
    L3 cache:            36608K
    NUMA node0 CPU(s):   0,1
    Flags:               fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology cpuid pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase bmi1 hle avx2 smep bmi2 erms invpcid rtm mpx avx512f avx512dq rdseed adx smap clflushopt avx512cd avx512bw avx512vl xsaveopt xsavec xsaves md_clear
    

| Cpu Property       | Value                                                   |
|:------------------ |:------------------------------------------------------- |
| Brand              | Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz           |
| Vendor             | :Intel                                                  |
| Architecture       | :Skylake                                                |
| Model              | Family: 0x06, Model: 0x55, Stepping: 0x04, Type: 0x00   |
| Cores              | 2 physical cores, 2 logical cores (on executing CPU)    |
|                    | No Hyperthreading detected                              |
| Clock Frequencies  | Not supported by CPU                                    |
| Data Cache         | Level 1:3 : (32, 1024, 36608) kbytes                    |
|                    | 64 byte cache line size                                 |
| Address Size       | 48 bits virtual, 46 bits physical                       |
| SIMD               | 512 bit = 64 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

