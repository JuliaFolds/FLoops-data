# Benchmark result

* Pull request commit: [`97f3338cd8701baa54bbed185fbac27d0a1642ee`](https://github.com/JuliaFolds/FLoops.jl/commit/97f3338cd8701baa54bbed185fbac27d0a1642ee)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/19> (Support MLStyle 0.4)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 29 Jul 2020 - 01:46
    - Baseline: 29 Jul 2020 - 01:46
* Package commits:
    - Target: a9e023
    - Baseline: b21bd6
* Julia commits:
    - Target: 44fa15
    - Baseline: 44fa15
* Julia command flags:
    - Target: None
    - Baseline: None
* Environment variables:
    - Target: None
    - Baseline: None

## Results
A ratio greater than `1.0` denotes a possible regression (marked with :x:), while a ratio less
than `1.0` denotes a possible improvement (marked with :white_check_mark:). Only significant results - results
that indicate possible regressions or improvements - are shown below (thus, an empty table means that all
benchmark results remained invariant between builds).

| ID                                                           | time ratio                   | memory ratio |
|--------------------------------------------------------------|------------------------------|--------------|
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]` | 0.83 (5%) :white_check_mark: |   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`       |                1.11 (5%) :x: |   1.00 (1%)  |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

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
  uname: Linux 5.3.0-1032-azure #33~18.04.1-Ubuntu SMP Fri Jun 26 15:01:15 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      13396 s          0 s       1338 s       6236 s          0 s
       #2  2294 MHz       4786 s          0 s       1306 s      15179 s          0 s
       
  Memory: 6.764884948730469 GB (2948.2578125 MB free)
  Uptime: 229.0 sec
  Load Avg:  1.0830078125  0.68994140625  0.29736328125
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
      Ubuntu 18.04.4 LTS
  uname: Linux 5.3.0-1032-azure #33~18.04.1-Ubuntu SMP Fri Jun 26 15:01:15 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      14182 s          0 s       1358 s       9814 s          0 s
       #2  2294 MHz       8320 s          0 s       1384 s      15951 s          0 s
       
  Memory: 6.764884948730469 GB (2847.10546875 MB free)
  Uptime: 273.0 sec
  Load Avg:  1.10595703125  0.7509765625  0.337890625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 29 Jul 2020 - 1:46
* Package commit: a9e023
* Julia commit: 44fa15
* Julia command flags: None
* Environment variables: None

## Results
Below is a table of this job's results, obtained by running the benchmarks.
The values listed in the `ID` column have the structure `[parent_group, child_group, ..., key]`, and can be used to
index into the BaseBenchmarks suite to retrieve the corresponding benchmarks.
The percentages accompanying time and memory values in the below table are noise tolerances. The "true"
time/memory value for a given benchmark is expected to fall within this percentage of the reported value.
An empty cell means that the value was zero.

| ID                                                           | time            | GC time | memory          | allocations |
|--------------------------------------------------------------|----------------:|--------:|----------------:|------------:|
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]` |  38.301 μs (5%) |         |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`   |  27.700 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`      | 822.353 ns (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`        | 822.892 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`      | 805.505 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`        |   2.056 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`     |   1.660 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`       | 157.001 μs (5%) |         | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

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
  uname: Linux 5.3.0-1032-azure #33~18.04.1-Ubuntu SMP Fri Jun 26 15:01:15 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      13396 s          0 s       1338 s       6236 s          0 s
       #2  2294 MHz       4786 s          0 s       1306 s      15179 s          0 s
       
  Memory: 6.764884948730469 GB (2948.2578125 MB free)
  Uptime: 229.0 sec
  Load Avg:  1.0830078125  0.68994140625  0.29736328125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 29 Jul 2020 - 1:46
* Package commit: b21bd6
* Julia commit: 44fa15
* Julia command flags: None
* Environment variables: None

## Results
Below is a table of this job's results, obtained by running the benchmarks.
The values listed in the `ID` column have the structure `[parent_group, child_group, ..., key]`, and can be used to
index into the BaseBenchmarks suite to retrieve the corresponding benchmarks.
The percentages accompanying time and memory values in the below table are noise tolerances. The "true"
time/memory value for a given benchmark is expected to fall within this percentage of the reported value.
An empty cell means that the value was zero.

| ID                                                           | time            | GC time | memory          | allocations |
|--------------------------------------------------------------|----------------:|--------:|----------------:|------------:|
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]` |  46.000 μs (5%) |         |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`   |  27.700 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`      | 800.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`        | 800.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`      | 800.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`        |   2.100 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`     |   1.700 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`       | 141.501 μs (5%) |         | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

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
  uname: Linux 5.3.0-1032-azure #33~18.04.1-Ubuntu SMP Fri Jun 26 15:01:15 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      14182 s          0 s       1358 s       9814 s          0 s
       #2  2294 MHz       8320 s          0 s       1384 s      15951 s          0 s
       
  Memory: 6.764884948730469 GB (2847.10546875 MB free)
  Uptime: 273.0 sec
  Load Avg:  1.10595703125  0.7509765625  0.337890625
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
    Model:               79
    Model name:          Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz
    Stepping:            1
    CPU MHz:             2294.688
    BogoMIPS:            4589.37
    Hypervisor vendor:   Microsoft
    Virtualization type: full
    L1d cache:           32K
    L1i cache:           32K
    L2 cache:            256K
    L3 cache:            51200K
    NUMA node0 CPU(s):   0,1
    Flags:               fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology cpuid pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase bmi1 hle avx2 smep bmi2 erms invpcid rtm rdseed adx smap xsaveopt md_clear
    

| Cpu Property       | Value                                                   |
|:------------------ |:------------------------------------------------------- |
| Brand              | Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz               |
| Vendor             | :Intel                                                  |
| Architecture       | :Broadwell                                              |
| Model              | Family: 0x06, Model: 0x4f, Stepping: 0x01, Type: 0x00   |
| Cores              | 2 physical cores, 2 logical cores (on executing CPU)    |
|                    | No Hyperthreading detected                              |
| Clock Frequencies  | Not supported by CPU                                    |
| Data Cache         | Level 1:3 : (32, 256, 51200) kbytes                     |
|                    | 64 byte cache line size                                 |
| Address Size       | 48 bits virtual, 44 bits physical                       |
| SIMD               | 256 bit = 32 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

