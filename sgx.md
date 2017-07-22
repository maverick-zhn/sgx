# SGX

```
cat /proc/cpuinfo
```

```
processor	: 7
vendor_id	: GenuineIntel
cpu family	: 6
model		: 94
model name	: Intel(R) Core(TM) i7-6700K CPU @ 4.00GHz
stepping	: 3
microcode	: 0x8a
cpu MHz		: 3799.804
cache size	: 8192 KB
physical id	: 0
siblings	: 8
core id		: 3
cpu cores	: 4
apicid		: 7
initial apicid	: 7
fpu		: yes
fpu_exception	: yes
cpuid level	: 22
wp		: yes
flags		: fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx pdpe1gb rdtscp lm constant_tsc art arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc aperfmperf eagerfpu pni pclmulqdq dtes64 monitor ds_cpl vmx est tm2 ssse3 sdbg fma cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm abm 3dnowprefetch epb intel_pt tpr_shadow vnmi flexpriority ept vpid fsgsbase tsc_adjust bmi1 hle avx2 smep bmi2 erms invpcid rtm mpx rdseed adx smap clflushopt xsaveopt xsavec xgetbv1 xsaves dtherm ida arat pln pts hwp hwp_notify hwp_act_window hwp_epp
bugs		:
bogomips	: 8016.94
clflush size	: 64
cache_alignment	: 64
address sizes	: 39 bits physical, 48 bits virtual
power management:
```

```
servio@melon:~$ free -m
              total        used        free      shared  buff/cache   available
Mem:          64209         375       54959         192        8874       62812
Swap:         65350           0       65350
```

```
servio@melon:~$ cat /proc/meminfo
MemTotal:       65750328 kB
MemFree:        55834208 kB
MemAvailable:   64058456 kB
Buffers:         1052364 kB
Cached:          7270768 kB
SwapCached:            0 kB
Active:          4383720 kB
Inactive:        4387076 kB
Active(anon):     546988 kB
Inactive(anon):    99952 kB
Active(file):    3836732 kB
Inactive(file):  4287124 kB
Unevictable:        3640 kB
Mlocked:            3656 kB
SwapTotal:      66919420 kB
SwapFree:       66919420 kB
Dirty:             89612 kB
Writeback:             0 kB
AnonPages:        440984 kB
Mapped:           169704 kB
Shmem:            196724 kB
Slab:             947172 kB
SReclaimable:     830724 kB
SUnreclaim:       116448 kB
KernelStack:        6176 kB
PageTables:        16912 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:    99794584 kB
Committed_AS:    1883628 kB
VmallocTotal:   34359738367 kB
VmallocUsed:           0 kB
VmallocChunk:          0 kB
HardwareCorrupted:     0 kB
AnonHugePages:     57344 kB
ShmemHugePages:        0 kB
ShmemPmdMapped:        0 kB
CmaTotal:              0 kB
CmaFree:               0 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
DirectMap4k:      236120 kB
DirectMap2M:     8972288 kB
DirectMap1G:    57671680 kB
```
