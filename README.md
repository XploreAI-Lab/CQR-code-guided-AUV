# CQR-code-guided-AUV
基于彩色二维码通信的水下潜航器
# README for CQR-UC Project

## Project Title
**CQR-UC: A Color QR Code-based Underwater Wireless Communication Method with GAN-based Image Enhancement**

## Description
This repository contains the implementation of CQR-UC, a novel underwater wireless communication method that utilizes Color QR (CQR) codes for short-range data transmission. The system addresses challenges in underwater environments by employing a GAN-based image enhancement model (CQR-GAN) to improve CQR code recognition and a lightweight communication protocol (CUP) for reliable bidirectional data transmission.

Key features:
- Low-cost, low-power underwater communication solution
- CQR-GAN model for enhancing underwater CQR code images
- CUP protocol for continuous and reliable data transmission
- Compatible with resource-constrained devices (e.g., Raspberry Pi)

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/XploreAI-Lab/CQR-UC.git
   cd CQR-UC
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage
### 1. Training CQR-GAN
To train the CQR-GAN model:
```bash
python train_cqr_gan.py --dataset_path /path/to/dataset --epochs 200 --batch_size 16
```

### 2. Running CQR-UC Communication
For sender (transmitter):
```bash
python sender.py --data_file input.txt --output_dir output_cqr_codes --protocol CUP
```

For receiver:
```bash
python receiver.py --input_dir received_images --output_file output.txt --protocol CUP
```

### 3. Testing Under Different Conditions
The system can be tested with various parameters:
```bash
python test_system.py --environment seawater --distance 0.2 --angle 0 --qr_version 9
```

## Dataset
The dataset includes:
- 3,000 images of monochrome QR codes and CQR codes
- Underwater images captured in seawater, lake water, and purified water
- Training/validation/test split (80%/10%/10%)

## Results
Performance metrics from our experiments:
- Best transmission rate: 619.54 Bytes/s (RG 2-channel CQR codes)
- Power consumption: <15W
- Cost: <$40 for Raspberry Pi implementation
- Recognition accuracy improvement: >60% with CQR-GAN

## File Structure
```
CQR-UC/
├── data/                   # Sample datasets
├── models/                 # Pretrained models
│   ├── cqr_gan/            # CQR-GAN model
│   └── yolo_lite/          # QR code detection model
├── protocols/              # Communication protocol implementations
├── src/                    # Main source code
│   ├── cqr_code/           # CQR code generation/decoding
│   ├── enhancement/        # Image enhancement modules
│   ├── communication/      # Communication system
│   └── utils/              # Utility functions
├── experiments/            # Experiment scripts
├── requirements.txt        # Python dependencies
└── README.md               # This file
```

## Citation
If you use this work in your research, please cite our paper:
```bibtex
@article{zhao2025cqr,
  title={CQR-UC: A Color QR Code-based Underwater Wireless Communication Method with GAN-based Image Enhancement},
  author={Zhao, Zheng and Feng, Yufan and Li, Shangxin and Mao, Qian and Chen, Tingwei and Zhao, Qi and Fan, Xiaoya},
  journal={Nuclear Physics B},
  year={2025}
}
```

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact
For questions or collaborations, please contact:
- Zheng Zhao: zhaozheng@dlmu.edu.cn
- Xiaoya Fan: xiaoyafan@dlut.edu.cn

## Acknowledgments
This research was supported by grants from the National Natural Science Foundation of China (62002056) and the Fundamental Research Funds for Public Universities in Liaoning.
