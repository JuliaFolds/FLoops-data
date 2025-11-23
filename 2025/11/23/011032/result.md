# Benchmark result

* Pull request commit: [`05fbc0afb082e811fa569b125876fe976866154b`](https://github.com/JuliaFolds/FLoops.jl/commit/05fbc0afb082e811fa569b125876fe976866154b)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/121> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 23 Nov 2025 - 01:08
    - Baseline: 23 Nov 2025 - 01:10
* Package commits:
    - Target: 030662e
    - Baseline: 0144a5b
* Julia commits:
    - Target: 3b76b25
    - Baseline: 3b76b25
* Julia command flags:
    - Target: None
    - Baseline: None
* Environment variables:
    - Target: `OMP_NUM_THREADS => 1` `JULIA_NUM_THREADS => 2`
    - Baseline: `OMP_NUM_THREADS => 1` `JULIA_NUM_THREADS => 2`

## Results
A ratio greater than `1.0` denotes a possible regression (marked with :x:), while a ratio less
than `1.0` denotes a possible improvement (marked with :white_check_mark:). Brackets display [tolerances](https://juliaci.github.io/BenchmarkTools.jl/stable/manual/#Benchmark-Parameters) for the benchmark estimates. Only significant results - results
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
      Ubuntu 24.04.3 LTS
  uname: Linux 6.11.0-1018-azure #18~24.04.1-Ubuntu SMP Sat Jun 28 04:46:03 UTC 2025 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  3491 MHz        719 s          0 s        112 s       1958 s          0 s
       #2  3485 MHz        864 s          0 s         84 s       1857 s          0 s
       #3  3491 MHz        446 s          0 s         83 s       2258 s          0 s
       #4  3497 MHz        665 s          0 s        100 s       2036 s          0 s
       
  Memory: 15.61971664428711 GB (7823.98828125 MB free)
  Uptime: 289.41 sec
  Load Avg:  1.26  0.8  0.35
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
      Ubuntu 24.04.3 LTS
  uname: Linux 6.11.0-1018-azure #18~24.04.1-Ubuntu SMP Sat Jun 28 04:46:03 UTC 2025 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  3491 MHz       1062 s          0 s        137 s       2593 s          0 s
       #2  3492 MHz       1075 s          0 s         98 s       2635 s          0 s
       #3  3493 MHz        842 s          0 s        102 s       2845 s          0 s
       #4  3491 MHz       1073 s          0 s        120 s       2611 s          0 s
       
  Memory: 15.61971664428711 GB (7867.5703125 MB free)
  Uptime: 389.85 sec
  Load Avg:  1.33  0.99  0.47
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, icelake-server)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 23 Nov 2025 - 01:08
* Package commit: 030662e
* Julia commit: 3b76b25
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
| `["parallel_findminmax", "sequential"]`                            | 610.740 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 262.311 μs (5%) |         |   1.19 KiB (1%) |          30 |
| `["parallel_triangular_sum", "sequential"]`                        |   2.577 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   2.484 ms (5%) |         |   7.31 MiB (1%) |      205808 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   1.407 ms (5%) |         |   7.35 MiB (1%) |      206879 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   1.504 ms (5%) |         |   7.38 MiB (1%) |      207263 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   1.725 ms (5%) |         |   7.52 MiB (1%) |      209375 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   3.057 μs (5%) |         |  15.88 KiB (1%) |           2 |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |   9.808 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.086 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.086 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   1.808 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   1.886 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   2.249 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 139.658 μs (5%) |         | 456.84 KiB (1%) |       10068 |

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
      Ubuntu 24.04.3 LTS
  uname: Linux 6.11.0-1018-azure #18~24.04.1-Ubuntu SMP Sat Jun 28 04:46:03 UTC 2025 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  3491 MHz        719 s          0 s        112 s       1958 s          0 s
       #2  3485 MHz        864 s          0 s         84 s       1857 s          0 s
       #3  3491 MHz        446 s          0 s         83 s       2258 s          0 s
       #4  3497 MHz        665 s          0 s        100 s       2036 s          0 s
       
  Memory: 15.61971664428711 GB (7823.98828125 MB free)
  Uptime: 289.41 sec
  Load Avg:  1.26  0.8  0.35
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, icelake-server)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 23 Nov 2025 - 01:10
* Package commit: 0144a5b
* Julia commit: 3b76b25
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
| `["parallel_findminmax", "sequential"]`                            | 610.636 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 262.476 μs (5%) |         |   1.19 KiB (1%) |          30 |
| `["parallel_triangular_sum", "sequential"]`                        |   2.577 ms (5%) |         |   7.31 MiB (1%) |      205799 |
| `["parallel_triangular_sum", "threaded"]`                          |   2.465 ms (5%) |         |   7.31 MiB (1%) |      205808 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   1.411 ms (5%) |         |   7.35 MiB (1%) |      206876 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   1.486 ms (5%) |         |   7.38 MiB (1%) |      207260 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   1.713 ms (5%) |         |   7.52 MiB (1%) |      209372 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   2.315 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  65.471 μs (5%) |         | 187.50 KiB (1%) |        6000 |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.159 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.160 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              |   1.833 μs (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   1.851 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   2.319 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 139.310 μs (5%) |         | 456.88 KiB (1%) |       10069 |

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
      Ubuntu 24.04.3 LTS
  uname: Linux 6.11.0-1018-azure #18~24.04.1-Ubuntu SMP Sat Jun 28 04:46:03 UTC 2025 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz: 
              speed         user         nice          sys         idle          irq
       #1  3491 MHz       1062 s          0 s        137 s       2593 s          0 s
       #2  3492 MHz       1075 s          0 s         98 s       2635 s          0 s
       #3  3493 MHz        842 s          0 s        102 s       2845 s          0 s
       #4  3491 MHz       1073 s          0 s        120 s       2611 s          0 s
       
  Memory: 15.61971664428711 GB (7867.5703125 MB free)
  Uptime: 389.85 sec
  Load Avg:  1.33  0.99  0.47
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-11.0.1 (ORCJIT, icelake-server)
```

---
# Runtime information
| Runtime Info | |
|:--|:--|
| BLAS #threads | 4 |
| `BLAS.vendor()` | `openblas64` |
| `Sys.CPU_THREADS` | 4 |

`lscpu` output:

    Architecture:                         x86_64
    CPU op-mode(s):                       32-bit, 64-bit
    Address sizes:                        46 bits physical, 57 bits virtual
    Byte Order:                           Little Endian
    CPU(s):                               4
    On-line CPU(s) list:                  0-3
    Vendor ID:                            GenuineIntel
    Model name:                           Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz
    CPU family:                           6
    Model:                                106
    Thread(s) per core:                   2
    Core(s) per socket:                   2
    Socket(s):                            1
    Stepping:                             6
    CPU(s) scaling MHz:                   112%
    CPU max MHz:                          2800.0000
    CPU min MHz:                          800.0000
    BogoMIPS:                             5586.87
    Flags:                                fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology tsc_reliable nonstop_tsc cpuid aperfmperf tsc_known_freq pni pclmulqdq vmx ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand hypervisor lahf_lm abm 3dnowprefetch tpr_shadow ept vpid ept_ad fsgsbase tsc_adjust bmi1 hle avx2 smep bmi2 erms invpcid rtm avx512f avx512dq rdseed adx smap avx512ifma clflushopt clwb avx512cd sha_ni avx512bw avx512vl xsaveopt xsavec xgetbv1 xsaves vnmi avx512vbmi umip avx512_vbmi2 gfni vaes vpclmulqdq avx512_vnni avx512_bitalg avx512_vpopcntdq la57 rdpid fsrm arch_capabilities
    Virtualization:                       VT-x
    Hypervisor vendor:                    Microsoft
    Virtualization type:                  full
    L1d cache:                            96 KiB (2 instances)
    L1i cache:                            64 KiB (2 instances)
    L2 cache:                             2.5 MiB (2 instances)
    L3 cache:                             48 MiB (1 instance)
    NUMA node(s):                         1
    NUMA node0 CPU(s):                    0-3
    Vulnerability Gather data sampling:   Not affected
    Vulnerability Itlb multihit:          Not affected
    Vulnerability L1tf:                   Not affected
    Vulnerability Mds:                    Not affected
    Vulnerability Meltdown:               Not affected
    Vulnerability Mmio stale data:        Vulnerable: Clear CPU buffers attempted, no microcode; SMT Host state unknown
    Vulnerability Reg file data sampling: Not affected
    Vulnerability Retbleed:               Vulnerable
    Vulnerability Spec rstack overflow:   Not affected
    Vulnerability Spec store bypass:      Vulnerable
    Vulnerability Spectre v1:             Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Vulnerability Spectre v2:             Mitigation; Retpolines; STIBP disabled; RSB filling; PBRSB-eIBRS Not affected; BHI Retpoline
    Vulnerability Srbds:                  Not affected
    Vulnerability Tsx async abort:        Not affected
    

| Cpu Property       | Value                                                      |
|:------------------ |:---------------------------------------------------------- |
| Brand              | Intel(R) Xeon(R) Platinum 8370C CPU @ 2.80GHz              |
| Vendor             | :Intel                                                     |
| Architecture       | :UnknownIntel                                              |
| Model              | Family: 0x06, Model: 0x6a, Stepping: 0x06, Type: 0x00      |
| Cores              | 2 physical cores, 4 logical cores (on executing CPU)       |
|                    | Hyperthreading hardware capability detected                |
| Clock Frequencies  | Not supported by CPU                                       |
| Data Cache         | Level 1:3 : (48, 1280, 49152) kbytes                       |
|                    | 64 byte cache line size                                    |
| Address Size       | 57 bits virtual, 46 bits physical                          |
| SIMD               | 512 bit = 64 byte max. SIMD vector size                    |
| Time Stamp Counter | TSC is accessible via `rdtsc`                              |
|                    | TSC runs at constant rate (invariant from clock frequency) |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported    |
| Hypervisor         | Yes, Microsoft                                             |

