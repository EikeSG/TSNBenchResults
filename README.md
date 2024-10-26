# TSN Scheduler Benchmarking Results
This dataset provides test results of multiple Time-Sensitive Networking (TSN) schedulers that were tested and compared in the following PhD thesis (to be published):
- E. Schweissguth, "**Routing and Scheduling of Time-Triggered Ethernet Networks: ILP Models and Scheduler Benchmarking.**". University of Rostock.

An earlier version of this repository contained results from the following publication:
- E. Schweissguth, S. Mehner, D. Hellmanns, J. Falk, H. Parzyjegla, P. Danielis, O. Hohlfeld, G. Muehl, and D. Timmermann, "**TSN Scheduler Benchmarking.**" in *WFCS 2023*. IEEE.

These results are still available in the history (see releases).

Please refer to the thesis for detailed background information. The results are based on the following scenarios (i.e., topologies and stream sets): "**TSN Scheduler Benchmarking: Scenarios v2.0.0**" (see https://doi.org/10.5281/zenodo.13993512 or https://github.com/EikeSG/TSNBenchScenarios/releases/tag/v2.0.0). When accessing this dataset through Zenodo, also check the corresponding GitHub repository (https://github.com/EikeSG/TSNBenchResults) for updates and for a good in-browser view (especially for markdown files).

This repository contains all runtime/schedulability/latency plots for all benchmarking tests run throughout the thesis, whereas result plots in the thesis are excerpts from the plots in this repository.
A mapping between thesis chapters and subdirectories of the `plots` directory is given in the following table.

| thesis chapter | related subdir |
|----------------|----------------|
| 4.2.3/4.2.4    | `testcases`            |
| 4.3.2          | `threadbench`          |
| 6.4.5          | `uc/moobj`             |
| 6.4.7          | `uc/sras`              |
| 6.5.4          | `mc/nonopt` + `mc/opt` |
| 6.5.5          | `mc/uc`                |
| 7.1.2          | `enh/mcs`              |
| 7.1.4          | `enh/rc/mod`           |
| 7.1.6          | `enh/erpp/*`           |
| 7.2.3          | `qfi/*`                |
| 8.1            | `benchmc/*`            |
| 8.2.1          | `progress/o1`          |
| 8.2.2          | `progress/enh`         |
| 8.3            | `progress/final`       |
| 10.2.2         | `reduct/*`             |

Each subdirectory contains `.md` files for easier browsing.
An archive of actual result files (i.e., schedules created by the respective schedulers) can be found as binary for the github release. Due to size, it is not tracked in the repo and additionally split into three files (`resultsaa`, `resultsab`, `resultsac`).
**Attention:** The unpacked archive is roughly 41 GiB and contains almost 1 million files (1 per solved problem instance).
Use `cat resultsaa resultsab resultsac >results.tar.gz` to recreate the archive, verify checksum with `sha256sum results.tar.gz` (should be `7abd86369b9597d685156cb8072d6d9d12a7ba013af969eb16bcde5ef56b2091`), and unpack to get **json**-encoded result files.
Note that the result files use slightly different scheduler names than used in the plots; a mapping between scheduler names of results files and plots is given in the respective `*_mapping_summary.log`-files.
