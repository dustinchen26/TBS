# 5G NR TBS Calculator
online calculate: https://dustinchen26.github.io/TBS

## wireshark
```
MCS for TB1: 9●
TBS for TB1: 43047●
Number of Virtual Resource Block: 273●
Number of OFDM Symbols: 13●
Number of Layers: 4●
MCS-Table-PDSCH: 1 (qam256)●
MCS index for TB1: 9●
RE Overhead Within a PRB: 0●
DMRS Configuration Type: 0 (Configuration type 1)●
PDSCH Mapping Type: 0 (PDSCH mapping type A)●
DMRS Maximum Length: 1●
DMRS Additional Symbol: 1●
First DMRS Position: 2 (PDSCH mapping type A)●
這代表：
👉 Mapping Type A 時，第一個 DMRS 位置是 symbol 2 ●
👉 AdditionalPosition = 1 表示額外使用 symbol 3	●
👉 共使用 2 個 symbol 當作 DMRS（symbol 2 與 3）●
👉 DMRS 的 RE 分佈在全 PRB 的 12 個子載波上, 共使用 2 個 symbol 當作 DMRS●
```

## Input
```
Number of PRBs (nPRB):273●
Number of Symbols (Nsymb):13●
Number of REs for DMRS per PRB:24=12*2●
xOverhead (REs per PRB):0●
MCS Table:256-QAM●
MCS Index (0~27):9●
Number of Layers (v):4●
Calculate TBS
```

## Output
```
Calculate TBS
Result:
TBS = 344376 bits
TBS = 43047.00 bytes●
Throughput = 656.85 Mbps

Calculation Details:
Resolved MCS: Qm = 4, R = 0.6016, SE = 2.4063
NRE' = 12 * 13 - 24 - 0 = 132
NRĒ = min(156, 132) = 132
NRE = 132 * 273 = 36036
Ninfo = 36036 * 0.6016 * 4 * 4 = 346846.50
Ninfo > 3824 → LDPC-based block segmentation
n = floor(log2(346846.5 - 24)) - 5 = 13
Ninfo' = 2^13 * round((346846.5 - 24)/2^13) = 344064
C = 41
TBS = 8 * 41 * ceil((344064 + 24) / (8 * 41)) - 24 = 344376 bits
TBS = 344376 bits = 43047.00 bytes
Throughput = 344376 * 20 * 100 = 688752000 bps = 656.85 Mbps
```
