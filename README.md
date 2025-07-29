# 5G NR TBS Calculator
online calculate: https://dustinchen26.github.io/TBS

## Example Input
```
Number of PRBs (nPRB):4
Number of Symbols (Nsymb):13
Number of REs for DMRS per PRB:12
xOverhead (REs per PRB):0
MCS Table:256-QAM
MCS Index (0~27):20
Number of Layers (v):4
Calculate TBS
```

## Example Output
```
Result:
TBS = 12296 bits
TBS = 1537.00 bytes
Throughput = 23.45 Mbps
Calculation Details:
Resolved MCS: Qm = 8, R = 0.6665, SE = 5.3320
NRE' = 12 * 13 - 12 - 0 = 144
NRĒ = min(156, 144) = 144
NRE = 144 * 4 = 576
Ninfo = 576 * 0.6665 * 8 * 4 = 12285.00
Ninfo > 3824 → LDPC-based block segmentation
n = floor(log2(12285 - 24)) - 5 = 8
Ninfo' = 2^8 * round((12285 - 24)/2^8) = 12288
C = 2
TBS = 8 * 2 * ceil((12288 + 24) / (8 * 2)) - 24 = 12296 bits
TBS = 12296 bits = 1537.00 bytes
Throughput = 12296 * 20 * 100 = 24592000 bps = 23.45 Mbps
```
