# Benchmark result

* Pull request commit: [`e113bbf721b7b79de8bc1a06ca651fd07aa54bf4`](https://github.com/JuliaFolds/FLoops.jl/commit/e113bbf721b7b79de8bc1a06ca651fd07aa54bf4)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/59> (Move executors to Transducers.jl)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 5 Jan 2021 - 06:47
    - Baseline: 5 Jan 2021 - 06:48
* Package commits:
    - Target: 31c2f1
    - Baseline: 4a061e
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
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` | 0.91 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |                1.08 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |                1.24 (5%) :x: |                   1.00 (1%)  |

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
  uname: Linux 5.4.0-1032-azure #33~18.04.1-Ubuntu SMP Tue Nov 17 11:40:52 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      19430 s          0 s       1405 s      15250 s          0 s
       #2  2593 MHz      15663 s          0 s       1554 s      19376 s          0 s
       
  Memory: 6.7913970947265625 GB (3454.0859375 MB free)
  Uptime: 379.0 sec
  Load Avg:  1.3349609375  0.962890625  0.46875
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
  uname: Linux 5.4.0-1032-azure #33~18.04.1-Ubuntu SMP Tue Nov 17 11:40:52 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      25240 s          0 s       1529 s      20206 s          0 s
       #2  2593 MHz      23053 s          0 s       1799 s      22651 s          0 s
       
  Memory: 6.7913970947265625 GB (3396.5234375 MB free)
  Uptime: 488.0 sec
  Load Avg:  1.41064453125  1.103515625  0.578125
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 5 Jan 2021 - 6:47
* Package commit: 31c2f1
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
| `["parallel_findminmax", "sequential"]`                           | 564.705 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 360.103 μs (5%) |         |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.384 ms (5%) |         |   8.80 MiB (1%) |      223019 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.204 ms (5%) |         |   8.81 MiB (1%) |      223072 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   1.915 ms (5%) |         |   8.89 MiB (1%) |      224867 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   2.372 ms (5%) |         |   9.10 MiB (1%) |      228681 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   3.245 ms (5%) |         |   9.63 MiB (1%) |      238729 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   2.322 μs (5%) |         |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  31.600 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.140 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.140 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   1.520 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.600 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.367 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 152.102 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.4.0-1032-azure #33~18.04.1-Ubuntu SMP Tue Nov 17 11:40:52 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      19430 s          0 s       1405 s      15250 s          0 s
       #2  2593 MHz      15663 s          0 s       1554 s      19376 s          0 s
       
  Memory: 6.7913970947265625 GB (3454.0859375 MB free)
  Uptime: 379.0 sec
  Load Avg:  1.3349609375  0.962890625  0.46875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 5 Jan 2021 - 6:48
* Package commit: 4a061e
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
| `["parallel_findminmax", "sequential"]`                           | 561.104 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 370.908 μs (5%) |            |   3.52 KiB (1%) |          77 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.303 ms (5%) |            |   8.80 MiB (1%) |      223020 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.260 ms (5%) |            |   8.81 MiB (1%) |      223074 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.098 ms (5%) |            |   8.89 MiB (1%) |      224871 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |    5.151 s (5%) | 170.566 ms | 773.60 MiB (1%) |    11775665 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   12.140 s (5%) | 432.955 ms |   1.83 GiB (1%) |    27974577 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   2.300 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  29.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.200 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   1.500 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.100 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.400 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 145.401 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.4.0-1032-azure #33~18.04.1-Ubuntu SMP Tue Nov 17 11:40:52 UTC 2020 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      25240 s          0 s       1529 s      20206 s          0 s
       #2  2593 MHz      23053 s          0 s       1799 s      22651 s          0 s
       
  Memory: 6.7913970947265625 GB (3396.5234375 MB free)
  Uptime: 488.0 sec
  Load Avg:  1.41064453125  1.103515625  0.578125
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
    Model name:          Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz
    Stepping:            7
    CPU MHz:             2593.908
    BogoMIPS:            5187.81
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
| Brand              | Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz          |
| Vendor             | :Intel                                                  |
| Architecture       | :Skylake                                                |
| Model              | Family: 0x06, Model: 0x55, Stepping: 0x07, Type: 0x00   |
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

