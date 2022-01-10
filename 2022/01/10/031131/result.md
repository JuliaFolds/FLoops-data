# Benchmark result

* Pull request commit: [`567866755d4b5559f78a9c8f7c9fe18467c84a53`](https://github.com/JuliaFolds/FLoops.jl/commit/567866755d4b5559f78a9c8f7c9fe18467c84a53)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/96> (Refactor ReduceOpSpec processing)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 10 Jan 2022 - 03:08
    - Baseline: 10 Jan 2022 - 03:10
* Package commits:
    - Target: 0c939a
    - Baseline: 0abb15
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
| `["parallel_findminmax", "sequential"]`                           |                1.06 (5%) :x: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` | 0.90 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |                1.10 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             | 0.88 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          | 0.89 (5%) :white_check_mark: |                   1.00 (1%)  |

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
  uname: Linux 5.11.0-1022-azure #23~20.04.1-Ubuntu SMP Fri Nov 19 10:20:52 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      21545 s         14 s       1647 s      23184 s          0 s
       #2  2294 MHz      26621 s         14 s       2265 s      17729 s          0 s
       
  Memory: 6.788982391357422 GB (2955.1015625 MB free)
  Uptime: 473.0 sec
  Load Avg:  1.279296875  1.0166015625  0.5263671875
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
  uname: Linux 5.11.0-1022-azure #23~20.04.1-Ubuntu SMP Fri Nov 19 10:20:52 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      33311 s         14 s       1828 s      25478 s          0 s
       #2  2294 MHz      32211 s         14 s       2391 s      26243 s          0 s
       
  Memory: 6.788982391357422 GB (2775.23828125 MB free)
  Uptime: 616.0 sec
  Load Avg:  1.216796875  1.087890625  0.6328125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 10 Jan 2022 - 3:8
* Package commit: 0c939a
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
| `["parallel_findminmax", "sequential"]`                           | 465.902 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 279.901 μs (5%) |         |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   4.729 ms (5%) |         |   9.35 MiB (1%) |      231163 |
| `["parallel_triangular_sum", "threaded"]`                         |   4.355 ms (5%) |         |   9.36 MiB (1%) |      231233 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.759 ms (5%) |         |   9.44 MiB (1%) |      233021 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   3.407 ms (5%) |         |   9.64 MiB (1%) |      236657 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   4.822 ms (5%) |         |  10.16 MiB (1%) |      246305 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   1.820 μs (5%) |         |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  31.100 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 992.308 ns (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 923.077 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 860.000 ns (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.211 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   1.870 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 183.301 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.11.0-1022-azure #23~20.04.1-Ubuntu SMP Fri Nov 19 10:20:52 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      21545 s         14 s       1647 s      23184 s          0 s
       #2  2294 MHz      26621 s         14 s       2265 s      17729 s          0 s
       
  Memory: 6.788982391357422 GB (2955.1015625 MB free)
  Uptime: 473.0 sec
  Load Avg:  1.279296875  1.0166015625  0.5263671875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, broadwell)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 10 Jan 2022 - 3:10
* Package commit: 0abb15
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
| `["parallel_findminmax", "sequential"]`                           | 438.603 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 271.701 μs (5%) |            |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   4.844 ms (5%) |            |   9.35 MiB (1%) |      231163 |
| `["parallel_triangular_sum", "threaded"]`                         |   4.372 ms (5%) |            |   9.36 MiB (1%) |      231233 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   3.070 ms (5%) |            |   9.44 MiB (1%) |      233020 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |    7.154 s (5%) | 231.923 ms | 785.25 MiB (1%) |    11963119 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   17.565 s (5%) | 571.306 ms |   1.86 GiB (1%) |    28447616 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   1.900 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  31.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 900.000 ns (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.100 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 180.101 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.11.0-1022-azure #23~20.04.1-Ubuntu SMP Fri Nov 19 10:20:52 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz      33311 s         14 s       1828 s      25478 s          0 s
       #2  2294 MHz      32211 s         14 s       2391 s      26243 s          0 s
       
  Memory: 6.788982391357422 GB (2775.23828125 MB free)
  Uptime: 616.0 sec
  Load Avg:  1.216796875  1.087890625  0.6328125
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

