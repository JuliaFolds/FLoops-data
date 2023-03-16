# Benchmark result

* Pull request commit: [`6f8bcc3fcbf8ffff65df975332f02922b21648be`](https://github.com/JuliaFolds/FLoops.jl/commit/6f8bcc3fcbf8ffff65df975332f02922b21648be)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/121> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 16 Mar 2023 - 00:48
    - Baseline: 16 Mar 2023 - 00:49
* Package commits:
    - Target: 10b4dc
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

| ID                                          | time ratio | memory ratio |
|---------------------------------------------|------------|--------------|

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
  uname: Linux 5.15.0-1034-azure #41-Ubuntu SMP Fri Feb 10 19:59:45 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  2793 MHz       1591 s          0 s        172 s       2472 s          0 s
       #2  2793 MHz       1233 s          0 s        158 s       2838 s          0 s
       
  Memory: 6.781219482421875 GB (3556.61328125 MB free)
  Uptime: 427.33 sec
  Load Avg:  1.42  0.89  0.41
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, icelake-server)
```

### Baseline
```
Julia Version 1.6.7
Commit 3b76b25b64 (2022-07-19 15:11 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 22.04.2 LTS
  uname: Linux 5.15.0-1034-azure #41-Ubuntu SMP Fri Feb 10 19:59:45 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  2793 MHz       2355 s          0 s        202 s       2774 s          0 s
       #2  2793 MHz       1842 s          0 s        190 s       3292 s          0 s
       
  Memory: 6.781219482421875 GB (3469.21875 MB free)
  Uptime: 536.97 sec
  Load Avg:  1.41  1.07  0.54
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, icelake-server)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 16 Mar 2023 - 0:48
* Package commit: 10b4dc
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
| `["parallel_findminmax", "sequential"]`                            | 854.900 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 364.000 μs (5%) |         |   1.19 KiB (1%) |          30 |
| `["parallel_triangular_sum", "sequential"]`                        |   3.495 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   3.347 ms (5%) |         |   7.31 MiB (1%) |      205807 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   1.891 ms (5%) |         |   7.35 MiB (1%) |      206879 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   2.003 ms (5%) |         |   7.38 MiB (1%) |      207263 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   2.259 ms (5%) |         |   7.52 MiB (1%) |      209375 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   3.138 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  16.500 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.520 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.520 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   2.522 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.578 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   3.200 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 202.300 μs (5%) |         | 456.84 KiB (1%) |       10068 |

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
  uname: Linux 5.15.0-1034-azure #41-Ubuntu SMP Fri Feb 10 19:59:45 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  2793 MHz       1591 s          0 s        172 s       2472 s          0 s
       #2  2793 MHz       1233 s          0 s        158 s       2838 s          0 s
       
  Memory: 6.781219482421875 GB (3556.61328125 MB free)
  Uptime: 427.33 sec
  Load Avg:  1.42  0.89  0.41
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, icelake-server)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 16 Mar 2023 - 0:49
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
| `["parallel_findminmax", "sequential"]`                            | 854.800 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 364.300 μs (5%) |         |   1.19 KiB (1%) |          30 |
| `["parallel_triangular_sum", "sequential"]`                        |   3.523 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   3.347 ms (5%) |         |   7.31 MiB (1%) |      205807 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   1.936 ms (5%) |         |   7.35 MiB (1%) |      206876 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   1.996 ms (5%) |         |   7.38 MiB (1%) |      207260 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   2.303 ms (5%) |         |   7.52 MiB (1%) |      209373 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   3.200 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  95.200 μs (5%) |         | 187.50 KiB (1%) |        6000 |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.600 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.600 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   2.500 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.600 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   3.200 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 198.400 μs (5%) |         | 456.88 KiB (1%) |       10069 |

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
  uname: Linux 5.15.0-1034-azure #41-Ubuntu SMP Fri Feb 10 19:59:45 UTC 2023 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  2793 MHz       2355 s          0 s        202 s       2774 s          0 s
       #2  2793 MHz       1842 s          0 s        190 s       3292 s          0 s
       
  Memory: 6.781219482421875 GB (3469.21875 MB free)
  Uptime: 536.97 sec
  Load Avg:  1.41  1.07  0.54
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, icelake-server)
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
    Model name:                      Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz
    CPU family:                      6
    Model:                           106
    Thread(s) per core:              1
    Core(s) per socket:              2
    Socket(s):                       1
    Stepping:                        6
    BogoMIPS:                        5586.88
    Flags:                           fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology cpuid pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch invpcid_single pti fsgsbase bmi1 hle avx2 smep bmi2 erms invpcid rtm avx512f avx512dq rdseed adx smap clflushopt avx512cd avx512bw avx512vl xsaveopt xsavec xsaves md_clear
    Hypervisor vendor:               Microsoft
    Virtualization type:             full
    L1d cache:                       96 KiB (2 instances)
    L1i cache:                       64 KiB (2 instances)
    L2 cache:                        2.5 MiB (2 instances)
    L3 cache:                        48 MiB (1 instance)
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
| Brand              | Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz           |
| Vendor             | :Intel                                                  |
| Architecture       | :UnknownIntel                                           |
| Model              | Family: 0x06, Model: 0x6a, Stepping: 0x06, Type: 0x00   |
| Cores              | 2 physical cores, 2 logical cores (on executing CPU)    |
|                    | No Hyperthreading hardware capability detected          |
| Clock Frequencies  | Not supported by CPU                                    |
| Data Cache         | Level 1:3 : (48, 1280, 49152) kbytes                    |
|                    | 64 byte cache line size                                 |
| Address Size       | 48 bits virtual, 46 bits physical                       |
| SIMD               | 512 bit = 64 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

