# SplitFed with HE: When Federated Learning Meets Split Learning and Homomorphic Encryption

## Overview

**Applying CKKS scheme to the SplitFed System Model**

<p align="center"><img src="https://github.com/thoongee/SplitFed-With-CKKS/assets/94193480/dc076b41-e5d0-45c1-a8a6-26a667cdb5c7" width="40%">

**Overall Structure**
1. Encrypt information about the client's local model before transmitting it to the main server.
2. Perform aggregation at the Fed server using homomorphic encryption.
3. Transmit the completed computation results back to the client.
4. Decrypt at the client to verify information about the model.

**Addressing SplitFed's Drawbacks with Homomorphic Encryption**

- **Mitigating the risk of data and model information leakage through the server:**
    - Generate a global model in an encrypted state within the server.
- **Defending against data injection attacks:**
    - Manage client key pairs through a key manager entity.
- **Utilizing only one main server:**
    - Decrease physical costs as only one server is needed.
    - Efficiently use server resources.
- **Similar accuracy to conventional SFL methods:**
    - SFLV1 (76.39%), HE-SFLV1(76.78%), SFLV2(78.5%), HE-SFLV2(78.4%)

## Description

- Our work is based on "SplitFed: When Federated Learning Meets Split Learning."
- We have one version of SplitFed programs : without using socket and no DP+PixelDP
- This repository contains the implementation of Centralized Learning (baseline), Federated Learning, Split Learning, SplitFedV1 Learning, SplitFedV2 Learning, SplitFedV1 Learning with HE and SplitFedV2 Learning with HE.
- Dataset: HAM10000
- Model: ResNet18

## Environment

- Please notice that we assume that you are using 'PyTorch' and device type as 'cpu'.
- You need to download docker image and you can run this code in your docker container
    - https://hub.docker.com/r/cryptolabinc/heaan-stat
- All programs are written in python 3.7.2 using the PyTorch library (PyTorch 1.2.0).

## **Installation**

- Create a 'data' folder and move the image files within the 'HAM10000_images_part_1' and 'HAM10000_images_part_2' folders, along with the metadata CSV, into the 'data' folder.
- HAM10000 dataset: https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/DBW86T
- Metadata : https://www.kaggle.com/datasets/kiaskhoshdast/ham10000-metadatacsv

## Usage

In docker container,

```bash
$ python3 HE_SFLV1_ResNet_HAM10000.py
$ python3 HE_SFLV2_ResNet_HAM10000.py
$ python3 SFLV1_ResNet_HAM10000.py
$ python3 SFLV2_ResNet_HAM10000.py
```

## Reference

- Thapa, Chandra, et al. "Splitfed: When federated learning meets split learning." Proceedings of the AAAI Conference on Artificial Intelligence. Vol. 36. No. 8. 2022.
- Sanon, Sogo Pierre, et al. "Secure Federated Learning: An Evaluation of Homomorphic Encrypted Network Traffic Prediction." 2023 IEEE 20th Consumer Communications & Networking Conference (CCNC). IEEE, 2023.
- Yang, Ziyuan, et al. "Dynamic Corrected Split Federated Learning with Homomorphic Encryption for U-shaped Medical Image Networks." IEEE Journal of Biomedical and Health Informatics (2023).
- Park, Jaehyoung, and Hyuk Lim. "Privacy-preserving federated learning using homomorphic encryption." Applied Sciences 12.2 (2022): 734.
- Han, Boyoung, et al. "Fully Homomorphic Privacy-Preserving Naive Bayes Machine Learning and Classification." Proceedings of the 11th Workshop on Encrypted Computing & Applied Homomorphic Cryptography. 2023.
