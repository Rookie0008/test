# Average Checkpoints Script

This repository provides scripts and instructions for averaging specific checkpoints of a model trained with Fairseq. Averaging checkpoints can improve model performance by stabilizing predictions and reducing variance.

## Features
- **Average last N checkpoints:** Use Fairseq's built-in `scripts/average_checkpoints.py` script to average the last N checkpoints.
- **Average specific checkpoints:** Provide a list of checkpoint file names to average custom checkpoints.

---

## Getting Started

### Prerequisites
- Python 3.7+
- PyTorch 1.8+
- Fairseq (latest version)

### Files
- `scripts/average_checkpoints.py`: Fairseq's built-in script for checkpoint averaging.
- `average_specific_checkpoints.py`: Custom script to average specific checkpoints (e.g., checkpoints 105–115).

---

## Usage

### 1. Average Last N Checkpoints
Run the following command to average the last 10 checkpoints in a specified directory:

```bash
SAVE="checkpoints/son3_model_1206"
OUTPUT="${SAVE}/checkpoint_last10_avg.pt"

python scripts/average_checkpoints.py \
    --inputs $SAVE \
    --num-epoch-checkpoints 10 \
    --output $OUTPUT
