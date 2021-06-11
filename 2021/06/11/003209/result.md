# Benchmark result

* Pull request commit: [`de27ee5cd090fd38556326aa9d3218ca86f0a842`](https://github.com/JuliaFolds/FLoops.jl/commit/de27ee5cd090fd38556326aa9d3218ca86f0a842)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/33> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 11 Jun 2021 - 00:28
    - Baseline: 11 Jun 2021 - 00:31
* Package commits:
    - Target: 23a486
    - Baseline: 719c1f
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
| `["parallel_findminmax", "threaded"]`                             | 0.92 (5%) :white_check_mark: | 0.47 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "sequential"]`                       |                1.07 (5%) :x: |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded"]`                         |                1.07 (5%) :x: |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |                1.99 (5%) :x: |                 Inf (1%) :x: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        | 0.92 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             | 0.82 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            |                1.07 (5%) :x: |                   1.00 (1%)  |

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
  uname: Linux 5.8.0-1033-azure #35~20.04.1-Ubuntu SMP Wed May 19 06:46:04 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      21025 s          2 s       1734 s      25493 s          0 s
       #2  2593 MHz      16713 s         18 s       1546 s      30207 s          0 s
       
  Memory: 6.790924072265625 GB (3448.8984375 MB free)
  Uptime: 488.0 sec
  Load Avg:  1.34326171875  0.9140625  0.43310546875
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
      Ubuntu 20.04.2 LTS
  uname: Linux 5.8.0-1033-azure #35~20.04.1-Ubuntu SMP Wed May 19 06:46:04 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      30581 s          2 s       2118 s      31503 s          0 s
       #2  2593 MHz      25302 s         18 s       1867 s      37250 s          0 s
       
  Memory: 6.790924072265625 GB (3312.7890625 MB free)
  Uptime: 648.0 sec
  Load Avg:  1.3212890625  1.05126953125  0.564453125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 11 Jun 2021 - 0:28
* Package commit: 23a486
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
| `["parallel_findminmax", "sequential"]`                           | 555.502 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 367.605 μs (5%) |         |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.774 ms (5%) |         |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.716 ms (5%) |         |   9.48 MiB (1%) |      239382 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.084 ms (5%) |         |   9.53 MiB (1%) |      240204 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   2.358 ms (5%) |         |   9.60 MiB (1%) |      240909 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   2.740 ms (5%) |         |   9.78 MiB (1%) |      243161 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   4.586 μs (5%) |         |  15.88 KiB (1%) |           2 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  29.200 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.140 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.140 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   1.500 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.055 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.367 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 153.201 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.8.0-1033-azure #35~20.04.1-Ubuntu SMP Wed May 19 06:46:04 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      21025 s          2 s       1734 s      25493 s          0 s
       #2  2593 MHz      16713 s         18 s       1546 s      30207 s          0 s
       
  Memory: 6.790924072265625 GB (3448.8984375 MB free)
  Uptime: 488.0 sec
  Load Avg:  1.34326171875  0.9140625  0.43310546875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 11 Jun 2021 - 0:31
* Package commit: 719c1f
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
| `["parallel_findminmax", "sequential"]`                           | 558.807 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 401.505 μs (5%) |            |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.533 ms (5%) |            |   9.35 MiB (1%) |      231163 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.459 ms (5%) |            |   9.36 MiB (1%) |      231232 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.178 ms (5%) |            |   9.44 MiB (1%) |      233021 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |    5.385 s (5%) | 204.104 ms | 785.27 MiB (1%) |    11963786 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   12.721 s (5%) | 510.989 ms |   1.86 GiB (1%) |    28449563 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   2.300 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  31.900 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   1.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.400 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 143.602 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.8.0-1033-azure #35~20.04.1-Ubuntu SMP Wed May 19 06:46:04 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      30581 s          2 s       2118 s      31503 s          0 s
       #2  2593 MHz      25302 s         18 s       1867 s      37250 s          0 s
       
  Memory: 6.790924072265625 GB (3312.7890625 MB free)
  Uptime: 648.0 sec
  Load Avg:  1.3212890625  1.05126953125  0.564453125
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
    Model:                           85
    Model name:                      Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz
    Stepping:                        7
    CPU MHz:                         2593.905
    BogoMIPS:                        5187.81
    Hypervisor vendor:               Microsoft
    Virtualization type:             full
    L1d cache:                       64 KiB
    L1i cache:                       64 KiB
    L2 cache:                        2 MiB
    L3 cache:                        35.8 MiB
    NUMA node0 CPU(s):               0,1
    Vulnerability Itlb multihit:     KVM: Mitigation: VMX unsupported
    Vulnerability L1tf:              Mitigation; PTE Inversion
    Vulnerability Mds:               Mitigation; Clear CPU buffers; SMT Host state unknown
    Vulnerability Meltdown:          Mitigation; PTI
    Vulnerability Spec store bypass: Vulnerable
    Vulnerability Spectre v1:        Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Vulnerability Spectre v2:        Mitigation; Full generic retpoline, STIBP disabled, RSB filling
    Vulnerability Srbds:             Not affected
    Vulnerability Tsx async abort:   Mitigation; Clear CPU buffers; SMT Host state unknown
    Flags:                           fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology cpuid pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase bmi1 hle avx2 smep bmi2 erms invpcid rtm mpx avx512f avx512dq rdseed adx smap clflushopt avx512cd avx512bw avx512vl xsaveopt xsavec xsaves md_clear
    

| Cpu Property       | Value                                                   |
|:------------------ |:------------------------------------------------------- |
| Brand              | Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz          |
| Vendor             | :Intel                                                  |
| Architecture       | :Skylake                                                |
| Model              | Family: 0x06, Model: 0x55, Stepping: 0x07, Type: 0x00   |
| Cores              | 2 physical cores, 2 logical cores (on executing CPU)    |
|                    | No Hyperthreading hardware capability detected          |
| Clock Frequencies  | Not supported by CPU                                    |
| Data Cache         | Level 1:3 : (32, 1024, 36608) kbytes                    |
|                    | 64 byte cache line size                                 |
| Address Size       | 48 bits virtual, 46 bits physical                       |
| SIMD               | 512 bit = 64 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

