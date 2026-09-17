# Literature Survey
## Robustness to Noisy Telemetry: A Feature-Corruption Stress Test of Quantum Classifiers on IoT Intrusion Data
---
## 1. Introduction

The rapid growth of Internet of Things (IoT) networks has increased the
need for effective network security and intrusion detection. IoT devices
continuously generate network traffic that can be analyzed to identify
malicious or anomalous activity.

Machine Learning (ML) has been widely investigated for Network Intrusion
Detection Systems (NIDS). More recently, Quantum Machine Learning (QML)
has emerged as a research direction for cybersecurity, with studies
exploring quantum support vector methods, variational quantum models,
and quantum neural networks for intrusion detection.

However, the reliability of these models when the input network
telemetry itself is corrupted remains an important question.

This literature survey examines existing work related to QML-based
intrusion detection, quantum noise, and IoT security in order to
identify the research gap addressed by this project.

---

# 2. Review of Related Work

## 2.1 Quantum Machine Learning for Network Intrusion Detection Systems:
## A Systematic Literature Review

**Nicesio, O. K., Leal, A. G., & Gava, V. L. (2023)**  
*2023 IEEE 2nd International Conference on AI in Cybersecurity (ICAIC)*  
DOI: 10.1109/ICAIC57335.2023.10044125

### Overview

Nicesio et al. present a systematic literature review of research
applying Quantum Machine Learning to Network Intrusion Detection
Systems. The review examines studies published between 2017 and 2022
and identifies, analyzes, and compares QML approaches used for
intrusion detection. [1]

The review identifies several important approaches, including
variational hybrid quantum-classical models, quantum support vector
machine approaches, and quantum neural networks. [1]

### Key Findings

The study demonstrates that QML has already been investigated as an
approach for network intrusion detection and that multiple quantum and
hybrid quantum-classical models have been proposed.

The review provides an important overview of the existing QML-IDS
research landscape and identifies the main algorithmic approaches used
in previous studies. [1]

### Relevance to This Project

This work establishes the foundation for investigating QML-based
intrusion detection.

However, its primary purpose is to review existing QML-IDS approaches.
It does not provide the specific controlled feature-corruption stress
test proposed in this project.

Therefore, it helps establish the existing research landscape from
which the present robustness study is developed.

---

## 2.2 Network Anomaly Detection Using Quantum Neural Networks on Noisy
## Quantum Computers

**Kukliansky, A., Orescanin, M., Bollmann, C., & Huffmire, T. (2024)**  
*IEEE Transactions on Quantum Engineering*  
DOI: 10.1109/TQE.2024.3359574

### Overview

Kukliansky et al. investigate Quantum Neural Networks (QNNs) for
network anomaly and intrusion detection while considering the
limitations of contemporary noisy quantum computers.

The study investigates efficient classical feature encoding, QNN
classifier selection, and performance tuning within current quantum
computational constraints. A smaller version of the proposed
architecture was also implemented on IonQ's Aria-1 quantum computer.
[2]

### Key Findings

The study reports an F1-score of 0.86 for its implementation using the
NF-UNSW-NB15 dataset. It also introduces a certainty-factor metric for
providing additional information about uncertainty in quantum
classification outputs and investigates noise susceptibility in the
quantum classification system. [2]

### Relevance to This Project

This paper is particularly important because it explicitly considers
noise in the context of quantum-based intrusion detection.

However, the focus is primarily on noise and limitations associated
with the quantum-computing environment.

The present project considers a different source of degradation:

> **corruption of the input network features before they are provided
> to the classifier.**

This distinction between quantum-system noise and input-data
corruption forms an important part of the proposed research gap.

---

## 2.3 QML-IDS: Quantum Machine Learning Intrusion Detection System

**Abreu, D. M., Rothenberg, C. E., & Abelém, A. J. G. (2024)**  
*2024 IEEE Symposium on Computers and Communications (ISCC)*  
DOI: 10.1109/ISCC61673.2024.10733655

### Overview

Abreu et al. propose QML-IDS, a Quantum Machine Learning-based
Intrusion Detection System that combines quantum and classical
computing techniques to analyze network patterns and detect attack
activity. [3]

The study evaluates the proposed approach using publicly available
datasets and investigates both binary and multiclass classification
tasks. [3]

### Key Findings

The authors report that QML-IDS can be applied to attack detection in
both binary and multiclass settings and present experimental
comparisons with classical machine-learning approaches. [3]

### Relevance to This Project

QML-IDS provides a direct example of applying QML techniques to
network intrusion detection.

The present project differs in its experimental objective. Instead of
evaluating intrusion detection only under standard data conditions, it
will deliberately introduce controlled corruption into the input
features and examine how model performance changes as corruption
increases.

---

## 2.4 From Pre-Quantum to Post-Quantum IoT Security: A Survey on
## Quantum-Resistant Cryptosystems for the Internet of Things

**Fernández-Caramés, T. M. (2020)**  
*IEEE Internet of Things Journal, 7(7), 6457–6480*  
DOI: 10.1109/JIOT.2019.2958788

### Overview

Fernández-Caramés presents a broad survey of security considerations
for Internet of Things systems in the context of quantum computing.
The work reviews post-quantum cryptographic approaches, IoT
architectures, associated challenges, and future directions. [4]

### Key Findings

The paper provides a broad perspective on securing IoT systems against
the emerging threats associated with quantum computing and discusses
the challenges involved in deploying security mechanisms within IoT
environments. [4]

### Relevance to This Project

This work does not directly investigate QML-based intrusion detection.
Instead, it provides the broader IoT security context for the present
research.

Its relevance is therefore complementary: it establishes the
importance of security in IoT environments, while the other reviewed
papers provide the QML and intrusion-detection foundation.

---

# 3. Comparative Analysis of Existing Work

The reviewed literature covers several closely related research
directions:

| Study | Primary Focus | Relevance to This Project |
|---|---|---|
| Nicesio et al. [1] | QML for network intrusion detection | Establishes the QML-IDS research landscape |
| Kukliansky et al. [2] | QNN-based network anomaly detection | Investigates QNNs and quantum-computing noise |
| Abreu et al. [3] | QML-based intrusion detection | Demonstrates QML-based IDS using network datasets |
| Fernández-Caramés [4] | IoT and post-quantum security | Provides broader IoT security context |

Together, these studies establish that:

1. QML has been investigated for network intrusion detection.
2. QSVM/QSVC-related approaches, variational models, and QNNs are
   established research directions.
3. Quantum-computing noise is an important consideration for QML
   systems.
4. IoT environments present important security challenges.

---

# 4. Research Gap

The reviewed literature demonstrates substantial research activity in
Quantum Machine Learning for intrusion detection and in understanding
the effects of noise within quantum-computing systems.

However, the reviewed studies do not directly provide a systematic
comparison of multiple QML intrusion-detection classifiers under
**progressively increasing corruption of the input network features**.

In particular, the distinction is:

### Existing noise-focused research

```text
Network Data
     ↓
Quantum Classifier
     ↓
Quantum Circuit / Hardware
     ↓
Quantum Noise
     ↓
Prediction
