# Benchmark result

* Pull request commit: [`8f096a0b3e6d074403279d34cc68bd6e48381e0c`](https://github.com/JuliaFolds/FLoops.jl/commit/8f096a0b3e6d074403279d34cc68bd6e48381e0c)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/121> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 29 Jun 2023 - 00:54
    - Baseline: 29 Jun 2023 - 00:56
* Package commits:
    - Target: 6b0f98
    - Baseline: 0144a5
* Julia commits:
    - Target: 3b76b2
    - Baseline: 3b76b2
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

| ID                                          | time ratio                   | memory ratio  |
|---------------------------------------------|------------------------------|---------------|
| `["parallel_findminmax", "threaded"]`       | 0.87 (5%) :white_check_mark: | 1.03 (1%) :x: |
| `["parallel_triangular_sum", "sequential"]` | 0.92 (5%) :white_check_mark: |    1.00 (1%)  |
| `["parallel_triangular_sum", "threaded"]`   | 0.93 (5%) :white_check_mark: |    1.00 (1%)  |

## Benchmark Group List
Here's a list of all the benchmark groups executed by this job:

- `["parallel_findminmax"]`
- `["parallel_triangular_sum"]`

## Julia versioninfo

### Target
```
Julia Version 1.6.7
Commit 3b76b25b64 (2022-07-19 15:11 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 22.04.2 LTS
  uname: Linux 5.15.0-1040-azure #47-Ubuntu SMP Thu Jun 1 19:38:24 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz       1426 s          0 s        193 s       1485 s          0 s
       #2  2294 MHz       1941 s          0 s        218 s        931 s          0 s
       
  Memory: 6.7694854736328125 GB (3591.62109375 MB free)
  Uptime: 315.92 sec
  Load Avg:  1.2  1.0  0.48
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, broadwell)
```

### Baseline
```
Julia Version 1.6.7
Commit 3b76b25b64 (2022-07-19 15:11 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 22.04.2 LTS
  uname: Linux 5.15.0-1040-azure #47-Ubuntu SMP Thu Jun 1 19:38:24 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz       2220 s          0 s        235 s       2041 s          0 s
       #2  2294 MHz       2854 s          0 s        257 s       1371 s          0 s
       
  Memory: 6.7694854736328125 GB (3476.1171875 MB free)
  Uptime: 455.51 sec
  Load Avg:  1.3  1.14  0.61
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, broadwell)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 29 Jun 2023 - 0:54
* Package commit: 6b0f98
* Julia commit: 3b76b2
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
| `["parallel_findminmax", "sequential"]`                            | 438.201 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 262.200 μs (5%) |         |   1.19 KiB (1%) |          30 |
| `["parallel_triangular_sum", "sequential"]`                        |   3.539 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   4.001 ms (5%) |         |   7.31 MiB (1%) |      205807 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.207 ms (5%) |         |   7.35 MiB (1%) |      206879 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   2.543 ms (5%) |         |   7.38 MiB (1%) |      207263 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   3.234 ms (5%) |         |   7.52 MiB (1%) |      209376 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   1.880 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  14.600 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              | 829.630 ns (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                | 830.488 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              | 866.667 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.389 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   1.680 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 194.400 μs (5%) |         | 456.84 KiB (1%) |       10068 |

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
Julia Version 1.6.7
Commit 3b76b25b64 (2022-07-19 15:11 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 22.04.2 LTS
  uname: Linux 5.15.0-1040-azure #47-Ubuntu SMP Thu Jun 1 19:38:24 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz       1426 s          0 s        193 s       1485 s          0 s
       #2  2294 MHz       1941 s          0 s        218 s        931 s          0 s
       
  Memory: 6.7694854736328125 GB (3591.62109375 MB free)
  Uptime: 315.92 sec
  Load Avg:  1.2  1.0  0.48
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, broadwell)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 29 Jun 2023 - 0:56
* Package commit: 0144a5
* Julia commit: 3b76b2
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
| `["parallel_findminmax", "sequential"]`                            | 458.801 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 300.101 μs (5%) |         |   1.16 KiB (1%) |          29 |
| `["parallel_triangular_sum", "sequential"]`                        |   3.846 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   4.305 ms (5%) |         |   7.31 MiB (1%) |      205808 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.681 ms (5%) |         |   7.35 MiB (1%) |      206876 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   2.828 ms (5%) |         |   7.38 MiB (1%) |      207260 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   3.434 ms (5%) |         |   7.52 MiB (1%) |      209373 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   1.900 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  99.000 μs (5%) |         | 187.50 KiB (1%) |        6000 |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              | 900.000 ns (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.000 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   1.000 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.400 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   1.900 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 216.300 μs (5%) |         | 456.88 KiB (1%) |       10069 |

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
Julia Version 1.6.7
Commit 3b76b25b64 (2022-07-19 15:11 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 22.04.2 LTS
  uname: Linux 5.15.0-1040-azure #47-Ubuntu SMP Thu Jun 1 19:38:24 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz: 
              speed         user         nice          sys         idle          irq
       #1  2294 MHz       2220 s          0 s        235 s       2041 s          0 s
       #2  2294 MHz       2854 s          0 s        257 s       1371 s          0 s
       
  Memory: 6.7694854736328125 GB (3476.1171875 MB free)
  Uptime: 455.51 sec
  Load Avg:  1.3  1.14  0.61
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, broadwell)
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
    Address sizes:                   46 bits physical, 48 bits virtual
    Byte Order:                      Little Endian
    CPU(s):                          2
    On-line CPU(s) list:             0,1
    Vendor ID:                       GenuineIntel
    Model name:                      Intel(R) Xeon(R) CPU E5-2673 v4 @ 2.30GHz
    CPU family:                      6
    Model:                           79
    Thread(s) per core:              1
    Core(s) per socket:              2
    Socket(s):                       1
    Stepping:                        1
    BogoMIPS:                        4589.37
    Flags:                           fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology cpuid pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase bmi1 hle avx2 smep bmi2 erms invpcid rtm rdseed adx smap xsaveopt md_clear
    Hypervisor vendor:               Microsoft
    Virtualization type:             full
    L1d cache:                       64 KiB (2 instances)
    L1i cache:                       64 KiB (2 instances)
    L2 cache:                        512 KiB (2 instances)
    L3 cache:                        50 MiB (1 instance)
    NUMA node(s):                    1
    NUMA node0 CPU(s):               0,1
    Vulnerability Itlb multihit:     KVM: Mitigation: VMX unsupported
    Vulnerability L1tf:              Mitigation; PTE Inversion
    Vulnerability Mds:               Mitigation; Clear CPU buffers; SMT Host state unknown
    Vulnerability Meltdown:          Mitigation; PTI
    Vulnerability Mmio stale data:   Vulnerable: Clear CPU buffers attempted, no microcode; SMT Host state unknown
    Vulnerability Retbleed:          Not affected
    Vulnerability Spec store bypass: Vulnerable
    Vulnerability Spectre v1:        Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Vulnerability Spectre v2:        Mitigation; Retpolines, STIBP disabled, RSB filling, PBRSB-eIBRS Not affected
    Vulnerability Srbds:             Not affected
    Vulnerability Tsx async abort:   Mitigation; Clear CPU buffers; SMT Host state unknown
    

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

