# sampling-framework-aux
Auxiliary repository for Sampling Framework

We generate the main data set and results based on the following
parameters:

-   metrics:

    -   *Hellinger distance*;

    -   memory usage;

    -   run time;

    -   *Imbalance error*;

-   distribution: Zipfian distribution with
    exp of 0.8, 1, 1.5, 2

-   data burst:

    -   no burst;

    -   light burst (bsp = 0.2, kbp = 0.1, blmin = 3,
        blmax = 5);

    -   heavy burst (bsp = 0.3, kbp = 0.2, blmin = 2,
        blmax = 4)

-   drift graduality: abrupt and gradual (len = 1 000 000);

-   algorithm sets:

    -   *Sticky Sampling*, *Lossy Counting*, *Space Saving*, *Landmark*
        and *Frequent*

    -   *Temporal Smoothed*, *Checkpoint Smoothed*, *Frequent* and
        *Lossy Counting*



