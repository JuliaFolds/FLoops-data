# Benchmark result

* Pull request commit: [`5e4686483f764b26a35a47b030798990dc35b5be`](https://github.com/JuliaFolds/FLoops.jl/commit/5e4686483f764b26a35a47b030798990dc35b5be)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/44> (Setup examples-to-documentation conversion using Literate)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 27 Aug 2020 - 03:12
    - Baseline: 27 Aug 2020 - 03:14
* Package commits:
    - Target: 315952
    - Baseline: 512d84
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

| ID                                                                | time ratio    | memory ratio |
|-------------------------------------------------------------------|---------------|--------------|
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        | 1.08 (5%) :x: |   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             | 1.24 (5%) :x: |   1.00 (1%)  |

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
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      17612 s          0 s       1685 s      16096 s          0 s
       #2  2095 MHz      18062 s          0 s       1558 s      15932 s          0 s
       
  Memory: 6.7913818359375 GB (2905.6484375 MB free)
  Uptime: 372.0 sec
  Load Avg:  1.30078125  0.974609375  0.474609375
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
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      26102 s          0 s       1832 s      18471 s          0 s
       #2  2095 MHz      22273 s          0 s       1726 s      22550 s          0 s
       
  Memory: 6.7913818359375 GB (2880.296875 MB free)
  Uptime: 482.0 sec
  Load Avg:  1.27001953125  1.05712890625  0.5634765625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 27 Aug 2020 - 3:12
* Package commit: 315952
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
| `["parallel_findminmax", "sequential"]`                           | 738.316 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 490.411 μs (5%) |         |   3.52 KiB (1%) |          77 |
| `["parallel_triangular_sum", "sequential"]`                       |  16.652 ms (5%) |         |   9.86 MiB (1%) |      284463 |
| `["parallel_triangular_sum", "threaded"]`                         |  16.290 ms (5%) |         |   9.86 MiB (1%) |      284508 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   9.579 ms (5%) |         |   9.95 MiB (1%) |      286297 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   9.838 ms (5%) |         |  10.16 MiB (1%) |      290520 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |  10.767 ms (5%) |         |  10.71 MiB (1%) |      301153 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |  53.701 μs (5%) |         |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  42.900 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.550 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.550 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   2.078 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   3.475 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   3.212 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 193.005 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      17612 s          0 s       1685 s      16096 s          0 s
       #2  2095 MHz      18062 s          0 s       1558 s      15932 s          0 s
       
  Memory: 6.7913818359375 GB (2905.6484375 MB free)
  Uptime: 372.0 sec
  Load Avg:  1.30078125  0.974609375  0.474609375
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 27 Aug 2020 - 3:14
* Package commit: 512d84
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
| `["parallel_findminmax", "sequential"]`                           | 738.316 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 490.411 μs (5%) |         |   3.52 KiB (1%) |          77 |
| `["parallel_triangular_sum", "sequential"]`                       |  16.468 ms (5%) |         |   9.86 MiB (1%) |      284463 |
| `["parallel_triangular_sum", "threaded"]`                         |  16.188 ms (5%) |         |   9.86 MiB (1%) |      284508 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   9.515 ms (5%) |         |   9.95 MiB (1%) |      286299 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   9.796 ms (5%) |         |  10.16 MiB (1%) |      290522 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |  10.695 ms (5%) |         |  10.71 MiB (1%) |      301152 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |  52.901 μs (5%) |         |  62.52 KiB (1%) |        4001 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  39.700 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.600 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.600 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   2.000 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.800 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   3.300 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 199.904 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.3.0-1034-azure #35~18.04.1-Ubuntu SMP Mon Jul 13 12:54:45 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      26102 s          0 s       1832 s      18471 s          0 s
       #2  2095 MHz      22273 s          0 s       1726 s      22550 s          0 s
       
  Memory: 6.7913818359375 GB (2880.296875 MB free)
  Uptime: 482.0 sec
  Load Avg:  1.27001953125  1.05712890625  0.5634765625
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
    CPU MHz:             2095.111
    BogoMIPS:            4190.22
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

