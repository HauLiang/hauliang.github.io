---
title: 'Summary Table of Differential Privacy for Wireless Federated Learning (2026)'
date: 2026-04-09
excerpt: "Summary table for <b>differential privacy for wireless federated learning</b>."
permalink: /read-list/2026/differential-privacy-wireless-federated-learning-table/
tags:
  - Differential Privacy
  - Federated Learning
  - Aircomp Federated Learning (AirFL)
---


| #Num | References                                                   | Wide/narrow band           | MAC model    | Convergence (assumption)                                     | Optimization variable                                        |
| ---- | ------------------------------------------------------------ | -------------------------- | ------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| 1    | "Wireless federated learning with local differential privacy", ISIT, 2020 | time-invariant flat-fading | NOMA         | smooth, strongly convex, bounded sample-wise gradient        | n/a                                                          |
| 2    | "Differentially private aircomp federated learning with power adaptation harnessing receiver noise", Globecom, 2020 | time-invariant flat-fading | NOMA         | analysis SNR-privacy trade-off                               | power-scaling factor                                         |
| 3    | "Privacy for free: Wireless federated learning via uncoded transmission with adaptive power control", JSAC, 2020 | block flat-fading          | OMA and NOMA | smooth, PL                                                   | power-scaling factor, artificial noise scale                 |
| 4    | "Privacy amplification for federated learning via user sampling and wireless aggregation" | block flat-fading          | NOMA         | smooth, strongly convex, bounded sample-wise gradient        |                                                              |
| 5    | "Private wireless federated learning with anonymous over-the-air computation",             ICASSP, 2021 | block flat-fading          | NOMA         | n/a                                                          | n/a                                                          |
| 6    | "Device scheduling for over-the-air federated learning with differential privacy", ICC, 2023time-invariant flat-fading | time-invariant flat-fading | NOMA         | smooth, PL, bounded sample-wise gradient                     | #scheduled devices set, alignment coefficient                |
| 7    | "Device Scheduling for Secure Aggregation in Wireless Federated Learning", IOTJ, 2024 | block flat-fading          | NOMA         | smooth, strongly convex, bounded sample-wise gradient        | device scheduling  strategty (joint training or send noise)  |
| 8    | "Towards differentially private over-the-air federated learning via device sampling", Globecom, 2023 | time-invariant flat-fading | NOMA         | not a standard convergence result, convex, smooth            | #sampling devices set, transceiver design factor             |
| 9    | "Communication-learning co-design for differentially private over-the-air federated learning with device sampling", TWC, 2024 | time-invariant flat-fading | NOMA         | not a standard convergence result, convex, smooth (also non-convex and multiple local iterations cases) | #sampling devices set, transceiver design factor, #iterations |
| 10   | "On the differential privacy in federated learning based on over-the-air computation", TWC, 2023 | block flat-fading          | NOMA         | smooth                                                       | n/a, need parameter estimation                               |
| 11   | "On the privacy leakage of over-the-air federated learning over MIMO fading channels", Globecom, 2023 | time-invariant flat-fading | NOMA, MIMO   | n/a                                                          | private information extraction optimization through receiver beamformer |
| 12   | "Differentially private over-the-air federated learning over MIMO fading channels", TWC, 2024 | time-invariant flat-fading | NOMA, MIMO   | smooth, strongly convex, bounded sample-wise gradient        | (1) use $M$ parallel linear estimateors to extract private information; (2) receive combiner, normalizing factor, power fraction factors |
|      |                                                              |                            |              |                                                              |                                                              |

