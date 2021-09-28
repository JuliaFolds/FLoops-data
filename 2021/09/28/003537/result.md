# Benchmark result

* Pull request commit: [`85eb6e7fced875de4f4f388fe456780931b67626`](https://github.com/JuliaFolds/FLoops.jl/commit/85eb6e7fced875de4f4f388fe456780931b67626)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/33> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 28 Sep 2021 - 00:31
    - Baseline: 28 Sep 2021 - 00:34
* Package commits:
    - Target: 208b8c
    - Baseline: 255382
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
| `["parallel_triangular_sum", "sequential"]`                       | 0.95 (5%) :white_check_mark: |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded"]`                         | 0.89 (5%) :white_check_mark: |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` | 0.88 (5%) :white_check_mark: |                   1.01 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |                1.07 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 0.90 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             | 0.92 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |                1.06 (5%) :x: |                   1.00 (1%)  |

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
      Ubuntu 20.04.3 LTS
  uname: Linux 5.8.0-1041-azure #44~20.04.1-Ubuntu SMP Fri Aug 20 20:41:09 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      20374 s         14 s       1720 s      31454 s          0 s
       #2  2294 MHz      22642 s         13 s       1848 s      29405 s          0 s
       
  Memory: 6.790924072265625 GB (3418.703125 MB free)
  Uptime: 544.0 sec
  Load Avg:  1.33349609375  0.93212890625  0.458984375
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
      Ubuntu 20.04.3 LTS
  uname: Linux 5.8.0-1041-azure #44~20.04.1-Ubuntu SMP Fri Aug 20 20:41:09 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      32977 s         14 s       2322 s      38069 s          0 s
       #2  2294 MHz      32447 s         13 s       2221 s      39049 s          0 s
       
  Memory: 6.790924072265625 GB (2979.78125 MB free)
  Uptime: 742.0 sec
  Load Avg:  1.337890625  1.08447265625  0.61328125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 28 Sep 2021 - 0:31
* Package commit: 208b8c
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
| `["parallel_findminmax", "sequential"]`                           | 437.706 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 263.803 μs (5%) |         |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.772 ms (5%) |         |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.779 ms (5%) |         |   9.48 MiB (1%) |      239383 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.241 ms (5%) |         |   9.53 MiB (1%) |      240205 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   2.609 ms (5%) |         |   9.60 MiB (1%) |      240911 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   3.148 ms (5%) |         |   9.78 MiB (1%) |      243168 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   1.760 μs (5%) |         |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  32.201 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 898.214 ns (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 898.214 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 879.381 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.311 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.020 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 161.502 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
      Ubuntu 20.04.3 LTS
  uname: Linux 5.8.0-1041-azure #44~20.04.1-Ubuntu SMP Fri Aug 20 20:41:09 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      20374 s         14 s       1720 s      31454 s          0 s
       #2  2294 MHz      22642 s         13 s       1848 s      29405 s          0 s
       
  Memory: 6.790924072265625 GB (3418.703125 MB free)
  Uptime: 544.0 sec
  Load Avg:  1.33349609375  0.93212890625  0.458984375
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 28 Sep 2021 - 0:34
* Package commit: 255382
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
| `["parallel_findminmax", "sequential"]`                           | 436.306 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 286.604 μs (5%) |            |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.972 ms (5%) |            |   9.35 MiB (1%) |      231163 |
| `["parallel_triangular_sum", "threaded"]`                         |   4.256 ms (5%) |            |   9.36 MiB (1%) |      231233 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.557 ms (5%) |            |   9.44 MiB (1%) |      233021 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |    8.495 s (5%) | 226.158 ms | 785.25 MiB (1%) |    11963118 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   18.074 s (5%) | 602.875 ms |   1.86 GiB (1%) |    28447629 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   1.800 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  30.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.000 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   1.900 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 155.704 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
      Ubuntu 20.04.3 LTS
  uname: Linux 5.8.0-1041-azure #44~20.04.1-Ubuntu SMP Fri Aug 20 20:41:09 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      32977 s         14 s       2322 s      38069 s          0 s
       #2  2294 MHz      32447 s         13 s       2221 s      39049 s          0 s
       
  Memory: 6.790924072265625 GB (2979.78125 MB free)
  Uptime: 742.0 sec
  Load Avg:  1.337890625  1.08447265625  0.61328125
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
    Vulnerability Itlb multihit:     KVM: Mitigation: VMX unsupported
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

