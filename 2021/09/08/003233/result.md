# Benchmark result

* Pull request commit: [`7f9464c7b5dd8cdc0cc2be8f3fefe5673d4a81e6`](https://github.com/JuliaFolds/FLoops.jl/commit/7f9464c7b5dd8cdc0cc2be8f3fefe5673d4a81e6)
* Pull request: <https://github.com/JuliaFolds/FLoops.jl/pull/33> (Update */Manifest.toml)

# Judge result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmarks:
    - Target: 8 Sep 2021 - 00:28
    - Baseline: 8 Sep 2021 - 00:31
* Package commits:
    - Target: e7a9d7
    - Baseline: 23b562
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
| `["parallel_findminmax", "sequential"]`                           |                1.37 (5%) :x: |                   1.00 (1%)  |
| `["parallel_findminmax", "threaded"]`                             |                1.31 (5%) :x: | 0.47 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "sequential"]`                       |                   1.00 (5%)  |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded"]`                         |                   0.95 (5%)  |                1.01 (1%) :x: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` | 0.00 (5%) :white_check_mark: | 0.01 (1%) :white_check_mark: |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |                1.22 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |                1.14 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |                1.14 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |                1.30 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           | 0.75 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             | 0.86 (5%) :white_check_mark: |                   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |                1.16 (5%) :x: |                   1.00 (1%)  |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            |                1.21 (5%) :x: |                   1.00 (1%)  |

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
  uname: Linux 5.8.0-1040-azure #43~20.04.1-Ubuntu SMP Mon Aug 2 22:06:11 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      22451 s         13 s       1539 s      30311 s          0 s
       #2  2095 MHz      19283 s         10 s       1678 s      33487 s          0 s
       
  Memory: 6.790924072265625 GB (3200.70703125 MB free)
  Uptime: 549.0 sec
  Load Avg:  1.31298828125  0.8857421875  0.4091796875
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
  uname: Linux 5.8.0-1040-azure #43~20.04.1-Ubuntu SMP Mon Aug 2 22:06:11 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      36693 s         13 s       2003 s      34432 s          0 s
       #2  2095 MHz      26078 s         10 s       2006 s      45159 s          0 s
       
  Memory: 6.790924072265625 GB (2989.78515625 MB free)
  Uptime: 738.0 sec
  Load Avg:  1.37939453125  1.07958984375  0.576171875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Target result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 8 Sep 2021 - 0:28
* Package commit: e7a9d7
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
| `["parallel_findminmax", "sequential"]`                           | 704.004 μs (5%) |         |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 450.603 μs (5%) |         |   1.66 KiB (1%) |          36 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.660 ms (5%) |         |   9.48 MiB (1%) |      239314 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.720 ms (5%) |         |   9.48 MiB (1%) |      239383 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.397 ms (5%) |         |   9.53 MiB (1%) |      240204 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |   2.474 ms (5%) |         |   9.60 MiB (1%) |      240911 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   3.098 ms (5%) |         |   9.78 MiB (1%) |      243169 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   3.167 μs (5%) |         |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  34.300 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.250 μs (5%) |         |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.430 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   1.430 μs (5%) |         |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.411 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   3.025 μs (5%) |         |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 164.001 μs (5%) |         | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.8.0-1040-azure #43~20.04.1-Ubuntu SMP Mon Aug 2 22:06:11 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      22451 s         13 s       1539 s      30311 s          0 s
       #2  2095 MHz      19283 s         10 s       1678 s      33487 s          0 s
       
  Memory: 6.790924072265625 GB (3200.70703125 MB free)
  Uptime: 549.0 sec
  Load Avg:  1.31298828125  0.8857421875  0.4091796875
  WORD_SIZE: 64
  LIBM: libopenlibm
  LLVM: libLLVM-8.0.1 (ORCJIT, skylake)
```

---
# Baseline result
# Benchmark Report for */home/runner/work/FLoops.jl/FLoops.jl*

## Job Properties
* Time of benchmark: 8 Sep 2021 - 0:31
* Package commit: 23b562
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
| `["parallel_findminmax", "sequential"]`                           | 515.403 μs (5%) |            |                 |             |
| `["parallel_findminmax", "threaded"]`                             | 344.002 μs (5%) |            |   3.50 KiB (1%) |          76 |
| `["parallel_triangular_sum", "sequential"]`                       |   3.656 ms (5%) |            |   9.35 MiB (1%) |      231163 |
| `["parallel_triangular_sum", "threaded"]`                         |   3.910 ms (5%) |            |   9.36 MiB (1%) |      231233 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 1"]` |   2.324 ms (5%) |            |   9.44 MiB (1%) |      233021 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 2"]` |    5.955 s (5%) | 182.245 ms | 795.52 MiB (1%) |    12114978 |
| `["parallel_triangular_sum", "threaded_nest", ":nestlevel => 3"]` |   14.325 s (5%) | 449.363 ms |   1.86 GiB (1%) |    28447654 |
| `["sum", ":label => \"BlockVector\"", ":impl => \"floop\""]`      |   2.600 μs (5%) |            |                 |             |
| `["sum", ":label => \"BlockVector\"", ":impl => \"for\""]`        |  30.100 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"floop\""]`           |   1.100 μs (5%) |            |                 |             |
| `["sum", ":label => \"Vector\"", ":impl => \"for\""]`             |   1.100 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"floop\""]`           |   1.900 μs (5%) |            |                 |             |
| `["sum", ":label => \"filter\"", ":impl => \"for\""]`             |   2.800 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"floop\""]`          |   2.600 μs (5%) |            |                 |             |
| `["sum", ":label => \"flatten\"", ":impl => \"for\""]`            | 135.601 μs (5%) |            | 220.91 KiB (1%) |        8053 |

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
  uname: Linux 5.8.0-1040-azure #43~20.04.1-Ubuntu SMP Mon Aug 2 22:06:11 UTC 2021 x86_64 x86_64
  CPU: Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz: 
              speed         user         nice          sys         idle          irq
       #1  2095 MHz      36693 s         13 s       2003 s      34432 s          0 s
       #2  2095 MHz      26078 s         10 s       2006 s      45159 s          0 s
       
  Memory: 6.790924072265625 GB (2989.78515625 MB free)
  Uptime: 738.0 sec
  Load Avg:  1.37939453125  1.07958984375  0.576171875
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
    Model name:                      Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz
    Stepping:                        4
    CPU MHz:                         2095.076
    BogoMIPS:                        4190.15
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
| Brand              | Intel(R) Xeon(R) Platinum 8171M CPU @ 2.60GHz           |
| Vendor             | :Intel                                                  |
| Architecture       | :Skylake                                                |
| Model              | Family: 0x06, Model: 0x55, Stepping: 0x04, Type: 0x00   |
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

