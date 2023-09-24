# numastat

FreeBSD NUMA domain memory monitor

## Synopsis

```
$ numastat
DOMAIN      ACTIVE  INACTIVE   LAUNDRY      FREE
--------  --------  --------  --------  --------
0            1.91G    18.93G     4.91G    42.92G
1            1.76G   521.39M     5.24G     9.90G
--------  --------  --------  --------  --------
0            1.90G    18.93G     4.91G    42.91G
1            1.76G   521.50M     5.24G     2.20G
```

## Description

To quote [Wikipedia](https://en.wikipedia.org/wiki/Non-uniform_memory_access):

> Non-uniform memory access (NUMA) is a computer memory design used in
> multiprocessing, where the memory access time depends on the memory
> location relative to the processor

Operating systems usually make some effort to allocate resources in a
NUMA-aware fashion in order to maximise performance, and FreeBSD is no
different.

`numastat` formats and displays the size of per-NUMA-domain page queues
exported through the `vm.domain` sysctl hierarchy so you can monitor how
memory allocations are balanced (or unbalanced, as in the above example)
across domains.
