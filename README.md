# TSN Scheduler Benchmarking Results
This dataset provides test results of multiple Time-Sensitive Networking (TSN) schedulers that were tested and compared in the following publication:
- E. Schweissguth, S. Mehner, D. Hellmanns, J. Falk, H. Parzyjegla, P. Danielis, O. Hohlfeld, G. Muehl, and D. Timmermann, "**TSN Scheduler Benchmarking.**" in *WFCS 2023*. IEEE.

Please refer to the paper for detailed background information. The results are based on the following scenarios (i.e., topologies and stream sets): (insert zenodo url here). Also check the linked GitHub repository for updates and for a good in-browser view (especially for markdown files).

This repository contains the full runtime data of our scheduler tests and all runtime/schedulability plots for all benchmarking test cases, whereas result plots in the paper are excerpts from the plots in this repository. See below for further details on the contents of the `runtimes` and `plots` directories.

# Runtimes

- contains scheduler runtimes from factor screening and benchmarking experiments as `.csv` files
- structured as follows (repetition left out in factor screening results):


| scheduler_name | configuration_name | runtime | successful | stream_set_comment                                        | t_id | s_id  | topology | node_count | stream_placement | stream_count | repetition | cycle_time_us | frame_size_b | latency_factor |
|----------------|--------------------|---------|------------|-----------------------------------------------------------|------|-------|----------|------------|------------------|--------------|------------|---------------|--------------|----------------|
| jssp           | jssp_default       | 8.24287 |        1.0 | benchmarking_line_24_t02_ss001-09_sss048_ct1000_fs0100_a6 |   63 |  9587 | line     |         24 |                1 |           48 |          9 |          1000 |          100 |              6 |
| nw-ilp         | nw-ilp_snf         | 124.565 |        0.0 | benchmarking_line_8_t00_ss072-06_sss130_ct0310_fs1500_a6  |   66 | 11205 | line     |          8 |               72 |          130 |          6 |           310 |         1500 |              6 |
| b-ilp          | b-ilp_sol          | 3.27021 |        1.0 | benchmarking_line_8_t00_ss048-12_sss100_ct0490_fs1500_a3  |   66 | 10879 | line     |          8 |               48 |          100 |         12 |           490 |         1500 |              3 |
| ...            | ...                | ...     |        ... |  ...                                                      | ...  |   ... | ...      |        ... |              ... |          ... |        ... |           ... |          ... |            ... |

# Plots

- contains runtime/schedulability plots of all test cases and topologies (excerpts are shown in the paper)
    - use `plots.md` for easy browsing of results
- the two plot variants (*all_schedulers/no_jssp*) plot different subsets of the five scheduler configurations, leading to different y-axis scaling better visual clarity for some plots
    - some schedulers can be missing in some plots, because we left out data points with zero schedulability
