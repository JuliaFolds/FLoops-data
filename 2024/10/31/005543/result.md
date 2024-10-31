# Benchmark result

* Pull request commit: [`3040d4870d72c44f547adc66145b8cd74e064ac8`](https://github.com/JuliaFolds/FLoops.jl/commit/3040d4870d72c44f547adc66145b8cd74e064ac8)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/121> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 31 Oct 2024 - 00:53
    - Baseline: 31 Oct 2024 - 00:55
* Package commits:
    - Target: dddee1
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

| ID                                          | time ratio                   | memory ratio                 |
|---------------------------------------------|------------------------------|------------------------------|
| `["parallel_findminmax", "sequential"]`     | 0.90 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["parallel_findminmax", "threaded"]`       |                   0.96 (5%)  | 0.97 (1%) :white_check_mark: |

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
      Ubuntu 22.04.5 LTS
  uname: Linux 6.5.0-1025-azure #26~22.04.1-Ubuntu SMP Thu Jul 11 22:33:04 UTC 2024 x86_64 x86_64
  CPU: AMD EPYC 7763 64-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2445 MHz        758 s          0 s         98 s       3312 s          0 s
       #2  2445 MHz        599 s          0 s        100 s       3461 s          0 s
       #3  3259 MHz        517 s          0 s        106 s       3549 s          0 s
       #4  3242 MHz       1024 s          0 s        127 s       3018 s          0 s
       
  Memory: 15.606491088867188 GB (12277.14453125 MB free)
  Uptime: 419.88 sec
  Load Avg:  1.3  0.8  0.34
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, generic)
```

### Baseline
```
Julia Version 1.6.7
Commit 3b76b25b64 (2022-07-19 15:11 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 22.04.5 LTS
  uname: Linux 6.5.0-1025-azure #26~22.04.1-Ubuntu SMP Thu Jul 11 22:33:04 UTC 2024 x86_64 x86_64
  CPU: AMD EPYC 7763 64-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2591 MHz       1103 s          0 s        118 s       3874 s          0 s
       #2  2445 MHz        870 s          0 s        125 s       4093 s          0 s
       #3  3242 MHz        803 s          0 s        132 s       4165 s          0 s
       #4  2445 MHz       1377 s          0 s        156 s       3564 s          0 s
       
  Memory: 15.606491088867188 GB (12316.625 MB free)
  Uptime: 512.86 sec
  Load Avg:  1.38  0.99  0.46
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, generic)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 31 Oct 2024 - 0:53
* Package commit: dddee1
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
| `["parallel_findminmax", "sequential"]`                            | 385.271 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 207.198 μs (5%) |         |   1.16 KiB (1%) |          29 |
| `["parallel_triangular_sum", "sequential"]`                        |   2.442 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   2.394 ms (5%) |         |   7.31 MiB (1%) |      205808 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   1.310 ms (5%) |         |   7.35 MiB (1%) |      206879 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   1.399 ms (5%) |         |   7.38 MiB (1%) |      207263 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   1.625 ms (5%) |         |   7.52 MiB (1%) |      209375 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   2.696 μs (5%) |         |  15.88 KiB (1%) |           2 |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  11.130 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              | 894.778 ns (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                | 894.778 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              | 891.234 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   1.970 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   1.834 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 153.408 μs (5%) |         | 456.84 KiB (1%) |       10068 |

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
      Ubuntu 22.04.5 LTS
  uname: Linux 6.5.0-1025-azure #26~22.04.1-Ubuntu SMP Thu Jul 11 22:33:04 UTC 2024 x86_64 x86_64
  CPU: AMD EPYC 7763 64-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2445 MHz        758 s          0 s         98 s       3312 s          0 s
       #2  2445 MHz        599 s          0 s        100 s       3461 s          0 s
       #3  3259 MHz        517 s          0 s        106 s       3549 s          0 s
       #4  3242 MHz       1024 s          0 s        127 s       3018 s          0 s
       
  Memory: 15.606491088867188 GB (12277.14453125 MB free)
  Uptime: 419.88 sec
  Load Avg:  1.3  0.8  0.34
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, generic)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 31 Oct 2024 - 0:55
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
| `["parallel_findminmax", "sequential"]`                            | 427.070 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 215.283 μs (5%) |         |   1.19 KiB (1%) |          30 |
| `["parallel_triangular_sum", "sequential"]`                        |   2.451 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   2.378 ms (5%) |         |   7.31 MiB (1%) |      205808 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   1.378 ms (5%) |         |   7.35 MiB (1%) |      206876 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   1.400 ms (5%) |         |   7.38 MiB (1%) |      207260 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   1.613 ms (5%) |         |   7.52 MiB (1%) |      209372 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   1.873 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  72.385 μs (5%) |         | 187.50 KiB (1%) |        6000 |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              | 941.000 ns (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                | 941.000 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              | 921.000 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   1.993 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   1.873 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 151.413 μs (5%) |         | 456.88 KiB (1%) |       10069 |

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
      Ubuntu 22.04.5 LTS
  uname: Linux 6.5.0-1025-azure #26~22.04.1-Ubuntu SMP Thu Jul 11 22:33:04 UTC 2024 x86_64 x86_64
  CPU: AMD EPYC 7763 64-Core Processor: 
              speed         user         nice          sys         idle          irq
       #1  2591 MHz       1103 s          0 s        118 s       3874 s          0 s
       #2  2445 MHz        870 s          0 s        125 s       4093 s          0 s
       #3  3242 MHz        803 s          0 s        132 s       4165 s          0 s
       #4  2445 MHz       1377 s          0 s        156 s       3564 s          0 s
       
  Memory: 15.606491088867188 GB (12316.625 MB free)
  Uptime: 512.86 sec
  Load Avg:  1.38  0.99  0.46
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, generic)
```

---
# Runtime information
| Runtime Info | |
|:--|:--|
| BLAS #threads | 4 |
| `BLAS.vendor()` | `openblas64` |
| `Sys.CPU_THREADS` | 4 |

`lscpu` output:

    Architecture:                       x86_64
    CPU op-mode(s):                     32-bit, 64-bit
    Address sizes:                      48 bits physical, 48 bits virtual
    Byte Order:                         Little Endian
    CPU(s):                             4
    On-line CPU(s) list:                0-3
    Vendor ID:                          AuthenticAMD
    Model name:                         AMD EPYC 7763 64-Core Processor
    CPU family:                         25
    Model:                              1
    Thread(s) per core:                 2
    Core(s) per socket:                 2
    Socket(s):                          1
    Stepping:                           1
    BogoMIPS:                           4890.86
    Flags:                              fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ht syscall nx mmxext fxsr_opt pdpe1gb rdtscp lm constant_tsc rep_good nopl tsc_reliable nonstop_tsc cpuid extd_apicid aperfmperf pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm cmp_legacy svm cr8_legacy abm sse4a misalignsse 3dnowprefetch osvw topoext invpcid_single vmmcall fsgsbase bmi1 avx2 smep bmi2 erms invpcid rdseed adx smap clflushopt clwb sha_ni xsaveopt xsavec xgetbv1 xsaves clzero xsaveerptr rdpru arat npt nrip_save tsc_scale vmcb_clean flushbyasid decodeassists pausefilter pfthreshold v_vmsave_vmload umip vaes vpclmulqdq rdpid fsrm
    Virtualization:                     AMD-V
    Hypervisor vendor:                  Microsoft
    Virtualization type:                full
    L1d cache:                          64 KiB (2 instances)
    L1i cache:                          64 KiB (2 instances)
    L2 cache:                           1 MiB (2 instances)
    L3 cache:                           32 MiB (1 instance)
    NUMA node(s):                       1
    NUMA node0 CPU(s):                  0-3
    Vulnerability Gather data sampling: Not affected
    Vulnerability Itlb multihit:        Not affected
    Vulnerability L1tf:                 Not affected
    Vulnerability Mds:                  Not affected
    Vulnerability Meltdown:             Not affected
    Vulnerability Mmio stale data:      Not affected
    Vulnerability Retbleed:             Not affected
    Vulnerability Spec rstack overflow: Vulnerable: Safe RET, no microcode
    Vulnerability Spec store bypass:    Vulnerable
    Vulnerability Spectre v1:           Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Vulnerability Spectre v2:           Mitigation; Retpolines; STIBP disabled; RSB filling; PBRSB-eIBRS Not affected; BHI Not affected
    Vulnerability Srbds:                Not affected
    Vulnerability Tsx async abort:      Not affected
    

| Cpu Property       | Value                                                      |
|:------------------ |:---------------------------------------------------------- |
| Brand              | AMD EPYC 7763 64-Core Processor                            |
| Vendor             | :AMD                                                       |
| Architecture       | :Unknown                                                   |
| Model              | Family: 0xaf, Model: 0x01, Stepping: 0x01, Type: 0x00      |
| Cores              | 16 physical cores, 16 logical cores (on executing CPU)     |
|                    | No Hyperthreading hardware capability detected             |
| Clock Frequencies  | Not supported by CPU                                       |
| Data Cache         | Level 1:3 : (32, 512, 32768) kbytes                        |
|                    | 64 byte cache line size                                    |
| Address Size       | 48 bits virtual, 48 bits physical                          |
| SIMD               | 256 bit = 32 byte max. SIMD vector size                    |
| Time Stamp Counter | TSC is accessible via `rdtsc`                              |
|                    | TSC runs at constant rate (invariant from clock frequency) |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported    |
| Hypervisor         | Yes, Microsoft                                             |

