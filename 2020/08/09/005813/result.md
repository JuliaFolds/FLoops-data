# Benchmark result

* Pull request commit: [`b243bf43a013e6c83b7e6d70f583640e0098f587`](https://github.com/JuliaFolds/FLoops.jl/commit/b243bf43a013e6c83b7e6d70f583640e0098f587)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/32> (Benchmark with nestlevel)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 9 Aug 2020 - 00:56
    - Baseline: 9 Aug 2020 - 00:57
* Package commits:
    - Target: 6012c8
    - Baseline: 079fdb
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

| ID                                                           | time ratio    | memory ratio |
|--------------------------------------------------------------|---------------|--------------|
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`   | 1.05 (5%) :x: |   1.00 (1%)  |

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
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      11884 s          0 s       1217 s      18607 s          0 s
       #2  2294 MHz      19526 s          0 s       1566 s      10200 s          0 s
       
  Memory: 6.764881134033203 GB (2875.7734375 MB free)
  Uptime: 332.0 sec
  Load Avg:  1.3134765625  0.86181640625  0.39404296875
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
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      17014 s          0 s       1303 s      20025 s          0 s
       #2  2294 MHz      21177 s          0 s       1647 s      15123 s          0 s
       
  Memory: 6.764881134033203 GB (2813.41015625 MB free)
  Uptime: 399.0 sec
  Load Avg:  1.18408203125  0.908203125  0.44384765625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 9 Aug 2020 - 0:56
* Package commit: 6012c8
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

| ID                                                                | time            | GC time  | memory          | allocations |
|-------------------------------------------------------------------|----------------:|---------:|----------------:|------------:|
| `["parallel_findminmax", "sequential"]`                           | 411.704 μs (5%) |          |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 252.702 μs (5%) |          |   3.52 KiB (1%) |          77 |
| `["parallel_triangular_sum", "sequential"]`                       | 111.631 ms (5%) | 5.986 ms |  86.33 MiB (1%) |     2680131 |
| `["parallel_triangular_sum", "threaded"]`                         | 105.725 ms (5%) | 5.149 ms |  86.34 MiB (1%) |     2680176 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |  70.556 ms (5%) | 8.588 ms |  86.42 MiB (1%) |     2681967 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |  65.944 ms (5%) | 7.659 ms |  86.64 MiB (1%) |     2686194 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |  67.037 ms (5%) | 8.622 ms |  87.19 MiB (1%) |     2696824 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |  38.500 μs (5%) |          |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  29.100 μs (5%) |          |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 823.457 ns (5%) |          |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 822.892 ns (5%) |          |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 811.494 ns (5%) |          |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.089 μs (5%) |          |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   1.660 μs (5%) |          |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 145.801 μs (5%) |          | 220.91 KiB (1%) |        8053 |

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
      Ubuntu 18.04.4 LTS
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      11884 s          0 s       1217 s      18607 s          0 s
       #2  2294 MHz      19526 s          0 s       1566 s      10200 s          0 s
       
  Memory: 6.764881134033203 GB (2875.7734375 MB free)
  Uptime: 332.0 sec
  Load Avg:  1.3134765625  0.86181640625  0.39404296875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 9 Aug 2020 - 0:57
* Package commit: 079fdb
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
| `["parallel_findminmax", "sequential"]`                      | 411.803 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                        | 247.302 μs (5%) |         |   3.52 KiB (1%) |          77 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]` |  38.400 μs (5%) |         |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`   |  27.700 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`      | 800.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`        | 800.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`      | 800.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`        |   2.100 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`     |   1.700 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`       | 144.401 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      17014 s          0 s       1303 s      20025 s          0 s
       #2  2294 MHz      21177 s          0 s       1647 s      15123 s          0 s
       
  Memory: 6.764881134033203 GB (2813.41015625 MB free)
  Uptime: 399.0 sec
  Load Avg:  1.18408203125  0.908203125  0.44384765625
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
    CPU MHz:             2294.686
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

