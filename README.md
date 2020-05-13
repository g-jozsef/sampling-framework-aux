# sampling-framework-aux
Auxiliary repository for Sampling Framework

The measurements were made on a 6 core, 12 thread Ryzen 3600 CPU clocked at 3.6Ghz with 16GB of RAM.

We used concept drifts where the midpoint of the drift is at the midpoint of the data stream.
All data sets consist of 5 000 000 elements with a key set of size 100 000.
We used micro-batches of size 30 000 and a top-K value of 300.

We generated the main data set and results based on the following
parameters:

-   metrics:

    -   *Hellinger distance*

    -   Memory usage

    -   Run time

    -   *Imbalance error*

-   distribution: Zipfian distribution with
    exp of 0.8, 1, 1.5, 2

-   data burst:

    -   no burst

    -   light burst (bsp = 0.2, kbp = 0.1, blmin = 3,
        blmax = 5)

    -   heavy burst (bsp = 0.3, kbp = 0.2, blmin = 2,
        blmax = 4)

-   drift graduality: abrupt and gradual (len = 1 000 000)

-   algorithm sets:

    -   *Sticky Sampling*, *Lossy Counting*, *Space Saving*, *Landmark*
        and *Frequent*

    -   *Temporal Smoothed*, *Checkpoint Smoothed*, *Frequent* and
        *Lossy Counting*



