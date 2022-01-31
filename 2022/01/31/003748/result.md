# Benchmark result

* Pull request commit: [`9ab1a3b16b93df5a067429791fabef1dbc0bf970`](https://github.com/JuliaFolds/FLoops.jl/commit/9ab1a3b16b93df5a067429791fabef1dbc0bf970)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/33> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 31 Jan 2022 - 00:34
    - Baseline: 31 Jan 2022 - 00:37
* Package commits:
    - Target: cd99d0
    - Baseline: 047b17
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
  uname: Linux 5.11.0-1027-azure #30~20.04.1-Ubuntu SMP Wed Jan 12 20:56:50 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v3 @ 2.40GHz: 
              speed         user         nice          sys         idle          irq
       #1  2394 MHz      23446 s         17 s       1826 s      16846 s          0 s
       #2  2394 MHz      22022 s          9 s       1961 s      18403 s          0 s
       
  Memory: 6.788978576660156 GB (3073.73828125 MB free)
  Uptime: 430.0 sec
  Load Avg:  1.3876953125  1.0498046875  0.53076171875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, haswell)
```

### Baseline
```
Julia Version 1.4.2
Commit 44fa15b150* (2020-05-23 18:35 UTC)
Platform Info:
  OS: Linux (x86_64-pc-linux-gnu)
      Ubuntu 20.04.3 LTS
  uname: Linux 5.11.0-1027-azure #30~20.04.1-Ubuntu SMP Wed Jan 12 20:56:50 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v3 @ 2.40GHz: 
              speed         user         nice          sys         idle          irq
       #1  2394 MHz      29668 s         17 s       1954 s      25177 s          0 s
       #2  2394 MHz      33268 s          9 s       2139 s      21684 s          0 s
       
  Memory: 6.788978576660156 GB (3046.42578125 MB free)
  Uptime: 577.0 sec
  Load Avg:  1.21533203125  1.0966796875  0.6337890625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, haswell)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 31 Jan 2022 - 0:34
* Package commit: cd99d0
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
| `["parallel_findminmax", "sequential"]`                            | 495.606 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 297.103 μs (5%) |         |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                        |   4.707 ms (5%) |         |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                          |   4.531 ms (5%) |         |   9.48 MiB (1%) |      239382 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.552 ms (5%) |         |   9.53 MiB (1%) |      240205 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |   2.891 ms (5%) |         |   9.60 MiB (1%) |      240911 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   3.591 ms (5%) |         |   9.78 MiB (1%) |      243168 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   1.930 μs (5%) |         |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  36.800 μs (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              | 952.174 ns (5%) |         |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                | 952.174 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              | 948.000 ns (5%) |         |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.563 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   2.090 μs (5%) |         |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 180.402 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.11.0-1027-azure #30~20.04.1-Ubuntu SMP Wed Jan 12 20:56:50 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v3 @ 2.40GHz: 
              speed         user         nice          sys         idle          irq
       #1  2394 MHz      23446 s         17 s       1826 s      16846 s          0 s
       #2  2394 MHz      22022 s          9 s       1961 s      18403 s          0 s
       
  Memory: 6.788978576660156 GB (3073.73828125 MB free)
  Uptime: 430.0 sec
  Load Avg:  1.3876953125  1.0498046875  0.53076171875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, haswell)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 31 Jan 2022 - 0:37
* Package commit: 047b17
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
| `["parallel_findminmax", "sequential"]`                            | 495.606 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                              | 295.103 μs (5%) |            |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                        |   4.766 ms (5%) |            |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                          |   4.372 ms (5%) |            |   9.48 MiB (1%) |      239383 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 1)]` |   2.846 ms (5%) |            |   9.53 MiB (1%) |      240205 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 2)]` |    6.557 s (5%) | 194.579 ms | 718.80 MiB (1%) |    11241681 |
| `["parallel_triangular_sum", "threaded_nest", :(:nestlevel => 3)]` |   16.669 s (5%) | 561.664 ms |   1.72 GiB (1%) |    26754235 |
| `["sum", :(:label => "BlockVector"), :(:impl => "floop")]`         |   2.100 μs (5%) |            |                 |             |
| `["sum", :(:label => "BlockVector"), :(:impl => "for")]`           |  35.900 μs (5%) |            |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "floop")]`              |   1.000 μs (5%) |            |                 |             |
| `["sum", :(:label => "Vector"), :(:impl => "for")]`                |   1.000 μs (5%) |            |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "floop")]`              | 900.000 ns (5%) |            |                 |             |
| `["sum", :(:label => "filter"), :(:impl => "for")]`                |   2.400 μs (5%) |            |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "floop")]`             |   1.900 μs (5%) |            |                 |             |
| `["sum", :(:label => "flatten"), :(:impl => "for")]`               | 176.502 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.11.0-1027-azure #30~20.04.1-Ubuntu SMP Wed Jan 12 20:56:50 UTC 2022 x86_64 x86_64
  CPU: Intel(R) Xeon(R) CPU E5-2673 v3 @ 2.40GHz: 
              speed         user         nice          sys         idle          irq
       #1  2394 MHz      29668 s         17 s       1954 s      25177 s          0 s
       #2  2394 MHz      33268 s          9 s       2139 s      21684 s          0 s
       
  Memory: 6.788978576660156 GB (3046.42578125 MB free)
  Uptime: 577.0 sec
  Load Avg:  1.21533203125  1.0966796875  0.6337890625
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, haswell)
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
    Model:                           63
    Model name:                      Intel(R) Xeon(R) CPU E5-2673 v3 @ 2.40GHz
    Stepping:                        2
    CPU MHz:                         2394.458
    BogoMIPS:                        4788.91
    Hypervisor vendor:               Microsoft
    Virtualization type:             full
    L1d cache:                       64 KiB
    L1i cache:                       64 KiB
    L2 cache:                        512 KiB
    L3 cache:                        30 MiB
    NUMA node0 CPU(s):               0,1
    Vulnerability Itlb multihit:     KVM: Mitigation: VMX unsupported
    Vulnerability L1tf:              Mitigation; PTE Inversion
    Vulnerability Mds:               Mitigation; Clear CPU buffers; SMT Host state unknown
    Vulnerability Meltdown:          Mitigation; PTI
    Vulnerability Spec store bypass: Vulnerable
    Vulnerability Spectre v1:        Mitigation; usercopy/swapgs barriers and __user pointer sanitization
    Vulnerability Spectre v2:        Mitigation; Full generic retpoline, STIBP disabled, RSB filling
    Vulnerability Srbds:             Not affected
    Vulnerability Tsx async abort:   Not affected
    Flags:                           fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush mmx fxsr sse sse2 ss ht syscall nx pdpe1gb rdtscp lm constant_tsc rep_good nopl xtopology cpuid pni pclmulqdq ssse3 fma cx16 pcid sse4_1 sse4_2 movbe popcnt aes xsave avx f16c rdrand hypervisor lahf_lm abm invpcid_single pti fsgsbase bmi1 avx2 smep bmi2 erms invpcid xsaveopt md_clear
    

| Cpu Property       | Value                                                   |
|:------------------ |:------------------------------------------------------- |
| Brand              | Intel(R) Xeon(R) CPU E5-2673 v3 @ 2.40GHz               |
| Vendor             | :Intel                                                  |
| Architecture       | :Haswell                                                |
| Model              | Family: 0x06, Model: 0x3f, Stepping: 0x02, Type: 0x00   |
| Cores              | 2 physical cores, 2 logical cores (on executing CPU)    |
|                    | No Hyperthreading hardware capability detected          |
| Clock Frequencies  | Not supported by CPU                                    |
| Data Cache         | Level 1:3 : (32, 256, 30720) kbytes                     |
|                    | 64 byte cache line size                                 |
| Address Size       | 48 bits virtual, 46 bits physical                       |
| SIMD               | 256 bit = 32 byte max. SIMD vector size                 |
| Time Stamp Counter | TSC is accessible via `rdtsc`                           |
|                    | TSC increased at every clock cycle (non-invariant TSC)  |
| Perf. Monitoring   | Performance Monitoring Counters (PMC) are not supported |
| Hypervisor         | Yes, Microsoft                                          |

