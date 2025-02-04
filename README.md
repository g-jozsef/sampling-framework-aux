# Sampling Framework Aux
Auxiliary repository for Sampling Framework

## Structure of this repository

    .
    ├── datasets                        # Contains the data streams, their metadata and the burst configurations
    │   ├── no_burst                    # Base dataset with no bursts
    │   ├── light_burst                 # Light burst configuration and the visualization of light burst
    │   └── heavy_burst                 # Heavy burst configuration and the visualization of heavy burst
    ├── state_of_the_art_measurement    # All of the metrics for state of the art algorithms
    │   ├── hellinger_distance          # Hellinger distance, time and memory metrics
    │   │   ├── no_burst                # Measurements with no burst
    │   │   ├── light_burst             # Measurements with light burst
    │   │   └── heavy_burst             # Measurements with heavy burst
    │   └── imbalance_error             # Imbalance error
    │       ├── no_burst                # Measurements with no burst
    │       ├── light_burst             # Measurements with light burst
    │       └── heavy_burst             # Measurements with heavy burst
    ├── our_algorithms_measurement      # All of the metrics for our algorithms
    │   ├── hellinger_distance          # Hellinger distance, time and memory metrics
    │   │   ├── no_burst                # Measurements with no burst
    │   │   ├── light_burst             # Measurements with light burst
    │   │   └── heavy_burst             # Measurements with heavy burst
    │   └── imbalance_error             # Imbalance error
    │       ├── no_burst                # Measurements with no burst
    │       ├── light_burst             # Measurements with light burst
    │       └── heavy_burst             # Measurements with heavy burst
    └── README.md

## Measurements

The measurements were made on a 6 core, 12 thread Ryzen 3600 CPU clocked at 3.6Ghz with 16GB of RAM.

We used concept drifts where the midpoint of the drift is at the midpoint of the data stream.
All data sets consist of 5 000 000 elements with a key set of size 100 000.
We used micro-batches of size 30 000 and a top-K value of 300.

We generated the main data set and results based on the following
parameters:

-   Metrics:

    -   *Hellinger distance*

    -   Memory usage

    -   Run time

    -   *Imbalance error* (with 5, 10, 20, 50 partitions)

-   Distribution: Zipfian distribution with
    exp of 0.8, 1, 1.5, 2

-   Data burst:

    -   no burst

    -   light burst (bsp = 0.2, kbp = 0.1, blmin = 3,
        blmax = 5)

    -   heavy burst (bsp = 0.3, kbp = 0.2, blmin = 2,
        blmax = 4)

-   Drift graduality: abrupt and gradual (len = 1 000 000)

-   Algorithm sets:

    -   state of the art: *Sticky Sampling*, *Lossy Counting*, *Space Saving*, *Landmark*
        and *Frequent*

    -   our algorithms: *Temporal Smoothed*, *Checkpoint Smoothed*, *Frequent* and
        *Lossy Counting*

## Algorithm configurations

-   Sticky Sampling: frequency = 0.0005, error = 0.00005, probability of failure = 0.0001

-   Lossy Counting: frequency = 0.0005, error = 0.00005

-   Space Saving: epsilon = 0.0001

-   Landmark: window size = 40000

-   Frequent: top-K=400, sliding window size=40000, basic window size=5000

-   Temporal Smoothed: threshold=40000, switch threshold=40000

-   Checkpoint Smoothed: checkpoint window=40000, check threshold=40000, error threshold=0.2
