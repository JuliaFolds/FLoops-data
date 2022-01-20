# Benchmark result

* Pull request commit: [`ec55e2e3abfdf06a27a59559faf7a7dcd3efc1bd`](https://github.com/JuliaFolds/FLoops.jl/commit/ec55e2e3abfdf06a27a59559faf7a7dcd3efc1bd)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/109> (Default to ThreadedEx)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 20 Jan 2022 - 01:50
    - Baseline: 20 Jan 2022 - 01:52
* Package commits:
    - Target: acf76c
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

| ID                                          | time ratio | memory ratio |
|---------------------------------------------|------------|--------------|

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
       #1  2593 MHz      15703 s          7 s       1697 s      43467 s          0 s
       #2  2593 MHz      23300 s         14 s       1634 s      36031 s          0 s
       
  Memory: 6.788978576660156 GB (2844.859375 MB free)
  Uptime: 615.0 sec
  Load Avg:  1.45654296875  0.94873046875  0.4560546875
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
       #1  2593 MHz      21760 s          7 s       1785 s      49181 s          0 s
       #2  2593 MHz      31417 s         14 s       1761 s      39638 s          0 s
       
  Memory: 6.788978576660156 GB (2759.9453125 MB free)
  Uptime: 734.0 sec
  Load Avg:  1.369140625  1.06982421875  0.56201171875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 20 Jan 2022 - 1:50
* Package commit: acf76c
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
| `["parallel_findminmax", "sequential"]`                            | 618.198 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 405.300 μs (5%) |         |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                        |   3.950 ms (5%) |         |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                          |   3.886 ms (5%) |         |   9.48 MiB (1%) |      239383 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.205 ms (5%) |         |   9.53 MiB (1%) |      240204 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   2.439 ms (5%) |         |   9.60 MiB (1%) |      240909 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   2.931 ms (5%) |         |   9.78 MiB (1%) |      243165 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   2.633 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  30.900 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.290 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.290 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   1.700 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.333 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   2.722 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 161.901 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
       #1  2593 MHz      15703 s          7 s       1697 s      43467 s          0 s
       #2  2593 MHz      23300 s         14 s       1634 s      36031 s          0 s
       
  Memory: 6.788978576660156 GB (2844.859375 MB free)
  Uptime: 615.0 sec
  Load Avg:  1.45654296875  0.94873046875  0.4560546875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 20 Jan 2022 - 1:52
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
| `["parallel_findminmax", "sequential"]`                            | 618.203 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 405.302 μs (5%) |            |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                        |   4.019 ms (5%) |            |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                          |   3.964 ms (5%) |            |   9.48 MiB (1%) |      239383 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.293 ms (5%) |            |   9.53 MiB (1%) |      240204 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |    4.735 s (5%) | 167.303 ms | 718.80 MiB (1%) |    11241680 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   12.008 s (5%) | 500.015 ms |   1.72 GiB (1%) |    26754235 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   2.700 μs (5%) |            |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  30.900 μs (5%) |            |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.300 μs (5%) |            |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.300 μs (5%) |            |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   1.700 μs (5%) |            |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.800 μs (5%) |            |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   2.700 μs (5%) |            |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 164.201 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
       #1  2593 MHz      21760 s          7 s       1785 s      49181 s          0 s
       #2  2593 MHz      31417 s         14 s       1761 s      39638 s          0 s
       
  Memory: 6.788978576660156 GB (2759.9453125 MB free)
  Uptime: 734.0 sec
  Load Avg:  1.369140625  1.06982421875  0.56201171875
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
    CPU MHz:                         2593.904
    BogoMIPS:                        5187.80
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

