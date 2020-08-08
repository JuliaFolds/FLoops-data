# Benchmark result

* Pull request commit: [`693cd21d0b2d83907efd6b0bd1254b3a6035412c`](https://github.com/JuliaFolds/FLoops.jl/commit/693cd21d0b2d83907efd6b0bd1254b3a6035412c)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/29> (Verify that the reducing function does not have boxed variables)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 8 Aug 2020 - 21:00
    - Baseline: 8 Aug 2020 - 21:01
* Package commits:
    - Target: 89c422
    - Baseline: 1a1a4c
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

| ID                                                           | time ratio                   | memory ratio |
|--------------------------------------------------------------|------------------------------|--------------|
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]` |                1.08 (5%) :x: |   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`      | 0.87 (5%) :white_check_mark: |   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`       | 0.95 (5%) :white_check_mark: |   1.00 (1%)  |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
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
      Ubuntu 18.04.4 LTS
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      12646 s          0 s       1416 s      20248 s          0 s
       #2  2095 MHz      10433 s          0 s       1424 s      22104 s          0 s
       
  Memory: 6.764881134033203 GB (2943.78515625 MB free)
  Uptime: 357.0 sec
  Load Avg:  1.1318359375  0.7001953125  0.318359375
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
      Ubuntu 18.04.4 LTS
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      18858 s          0 s       1502 s      21169 s          0 s
       #2  2095 MHz      11805 s          0 s       1475 s      27918 s          0 s
       
  Memory: 6.764881134033203 GB (2892.39453125 MB free)
  Uptime: 430.0 sec
  Load Avg:  1.11962890625  0.78271484375  0.37744140625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 8 Aug 2020 - 21:0
* Package commit: 89c422
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

| ID                                                           | time            | GC time | memory          | allocations |
|--------------------------------------------------------------|----------------:|--------:|----------------:|------------:|
| `["parallel_findminmax", "sequential"]`                      | 595.627 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                        | 395.717 μs (5%) |         |   3.52 KiB (1%) |          77 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]` |  45.502 μs (5%) |         |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`   |  34.601 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`      |   1.250 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`        |   1.250 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`      |   1.650 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`        |   2.800 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`     |   2.589 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`       | 148.407 μs (5%) |         | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
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
      Ubuntu 18.04.4 LTS
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      12646 s          0 s       1416 s      20248 s          0 s
       #2  2095 MHz      10433 s          0 s       1424 s      22104 s          0 s
       
  Memory: 6.764881134033203 GB (2943.78515625 MB free)
  Uptime: 357.0 sec
  Load Avg:  1.1318359375  0.7001953125  0.318359375
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 8 Aug 2020 - 21:1
* Package commit: 1a1a4c
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

| ID                                                           | time            | GC time | memory          | allocations |
|--------------------------------------------------------------|----------------:|--------:|----------------:|------------:|
| `["parallel_findminmax", "sequential"]`                      | 595.521 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                        | 395.614 μs (5%) |         |   3.52 KiB (1%) |          77 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]` |  42.101 μs (5%) |         |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`   |  35.001 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`      |   1.300 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`        |   1.300 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`      |   1.900 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`        |   2.700 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`     |   2.600 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`       | 157.006 μs (5%) |         | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
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
      Ubuntu 18.04.4 LTS
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      18858 s          0 s       1502 s      21169 s          0 s
       #2  2095 MHz      11805 s          0 s       1475 s      27918 s          0 s
       
  Memory: 6.764881134033203 GB (2892.39453125 MB free)
  Uptime: 430.0 sec
  Load Avg:  1.11962890625  0.78271484375  0.37744140625
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
    CPU MHz:             2095.197
    BogoMIPS:            4190.39
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
| Address Size       | 48 bits virtual, 44 bits physical                       |
| SIMD               | 512 bit = 64 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

