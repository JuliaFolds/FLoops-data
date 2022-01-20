# Benchmark result

* Pull request commit: [`ea458e9adaef3802d47ce038fb397cbdccec5f01`](https://github.com/JuliaFolds/FLoops.jl/commit/ea458e9adaef3802d47ce038fb397cbdccec5f01)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/109> (Default to ThreadedEx)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 20 Jan 2022 - 01:45
    - Baseline: 20 Jan 2022 - 01:46
* Package commits:
    - Target: 01feab
    - Baseline: 956368
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

| ID                                          | time ratio                   | memory ratio |
|---------------------------------------------|------------------------------|--------------|
| `["parallel_findminmax", "sequential"]`     | 0.89 (5%) :white_check_mark: |   1.00 (1%)  |
| `["parallel_findminmax", "threaded"]`       | 0.91 (5%) :white_check_mark: |   1.00 (1%)  |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
- `["parallel_triangular_sum"]`

## Julia versioninfo

### Target
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.3 LTS
  uname: Linux 5.11.0-1025-azure #27~20.04.1-Ubuntu SMP Fri Jan 7 15:02:06 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      16586 s         17 s       1540 s      26031 s          0 s
       #2  2593 MHz      21391 s          4 s       1432 s      22069 s          0 s
       
  Memory: 6.788978576660156 GB (2829.10546875 MB free)
  Uptime: 452.0 sec
  Load Avg:  1.4453125  0.99853515625  0.4765625
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
      Ubuntu 20.04.3 LTS
  uname: Linux 5.11.0-1025-azure #27~20.04.1-Ubuntu SMP Fri Jan 7 15:02:06 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      25296 s         17 s       1658 s      28456 s          0 s
       #2  2593 MHz      26253 s          4 s       1523 s      28356 s          0 s
       
  Memory: 6.788978576660156 GB (2781.2421875 MB free)
  Uptime: 565.0 sec
  Load Avg:  1.32177734375  1.07421875  0.5654296875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 20 Jan 2022 - 1:45
* Package commit: 01feab
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

| ID                                                                 | time            | GC time | memory          | allocations |
|--------------------------------------------------------------------|----------------:|--------:|----------------:|------------:|
| `["parallel_findminmax", "sequential"]`                            | 548.904 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 369.302 μs (5%) |         |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                        |   3.613 ms (5%) |         |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                          |   3.615 ms (5%) |         |   9.48 MiB (1%) |      239383 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.061 ms (5%) |         |   9.53 MiB (1%) |      240204 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   2.381 ms (5%) |         |   9.60 MiB (1%) |      240910 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   2.853 ms (5%) |         |   9.78 MiB (1%) |      243170 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   2.322 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  27.200 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.140 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.140 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   1.500 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.078 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   2.400 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 143.502 μs (5%) |         | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
- `["parallel_triangular_sum"]`
- `["parallel_triangular_sum", "threaded_nest"]`
- `["sum", :(:label => "BlockVector")]`
- `["sum", :(:label => "Vector")]`
- `["sum", :(:label => "filter")]`
- `["sum", :(:label => "flatten")]`

## Julia versioninfo
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.3 LTS
  uname: Linux 5.11.0-1025-azure #27~20.04.1-Ubuntu SMP Fri Jan 7 15:02:06 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      16586 s         17 s       1540 s      26031 s          0 s
       #2  2593 MHz      21391 s          4 s       1432 s      22069 s          0 s
       
  Memory: 6.788978576660156 GB (2829.10546875 MB free)
  Uptime: 452.0 sec
  Load Avg:  1.4453125  0.99853515625  0.4765625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 20 Jan 2022 - 1:46
* Package commit: 956368
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

| ID                                                                 | time            | GC time    | memory          | allocations |
|--------------------------------------------------------------------|----------------:|-----------:|----------------:|------------:|
| `["parallel_findminmax", "sequential"]`                            | 618.204 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 405.403 μs (5%) |            |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                        |   3.714 ms (5%) |            |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                          |   3.634 ms (5%) |            |   9.48 MiB (1%) |      239383 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.073 ms (5%) |            |   9.53 MiB (1%) |      240205 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   2.333 ms (5%) |            |   9.60 MiB (1%) |      240914 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   11.425 s (5%) | 427.551 ms |   1.72 GiB (1%) |    26754250 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   2.300 μs (5%) |            |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  33.100 μs (5%) |            |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.200 μs (5%) |            |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.200 μs (5%) |            |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   1.700 μs (5%) |            |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.900 μs (5%) |            |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   2.400 μs (5%) |            |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 143.800 μs (5%) |            | 220.91 KiB (1%) |        8053 |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
- `["parallel_triangular_sum"]`
- `["parallel_triangular_sum", "threaded_nest"]`
- `["sum", :(:label => "BlockVector")]`
- `["sum", :(:label => "Vector")]`
- `["sum", :(:label => "filter")]`
- `["sum", :(:label => "flatten")]`

## Julia versioninfo
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.3 LTS
  uname: Linux 5.11.0-1025-azure #27~20.04.1-Ubuntu SMP Fri Jan 7 15:02:06 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8272CL CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2593 MHz      25296 s         17 s       1658 s      28456 s          0 s
       #2  2593 MHz      26253 s          4 s       1523 s      28356 s          0 s
       
  Memory: 6.788978576660156 GB (2781.2421875 MB free)
  Uptime: 565.0 sec
  Load Avg:  1.32177734375  1.07421875  0.5654296875
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
    CPU MHz:                         2593.908
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

