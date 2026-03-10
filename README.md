# Tea_Leaf_Disease_Dataset-

<img width="793" height="400" alt="image" src="https://github.com/user-attachments/assets/7e36c1f7-1c9e-4380-98a5-596edb9adab7" />

# 🍃 Tea Leaf Disease Classification Competition

**Goal:** Build the best tea leaf disease classifier and top the leaderboard!  
**Metric:** Accuracy + F1 (macro)  
**Classes:** 8 disease categories  
**Baseline accuracy:** ~70%  
**Live Leaderboard:** [leaderboard/README.md](leaderboard/README.md)

---

## 📁 Repository Structure
```
Tea_Leaf_Disease_Dataset/
├── .github/workflows/evaluate.yml   # Auto-evaluation — DO NOT TOUCH
├── baseline/model.py                # Baseline ResNet50 model
├── evaluation/score.py              # Scoring script — DO NOT TOUCH
├── leaderboard/
│   ├── README.md                    # Live rankings
│   └── update.py                    # Leaderboard updater — DO NOT TOUCH
├── submission/                      # PUT YOUR FILE HERE
├── scores.json                      # All scores database
├── .gitignore
└── README.md
```

---

## 🚀 How to Participate

### Step 1 — Open the Notebook

Click the link below to open the competition notebook in Google Colab:

👉 **[Open Competition Notebook](https://colab.research.google.com/#fileId=https%3A//storage.googleapis.com/kaggle-colab-exported-notebooks/joelnyong/tea-leaf-competition.fb3bf4f1-d0f8-4f03-92cf-4c14f8319001.ipynb%3FX-Goog-Algorithm%3DGOOG4-RSA-SHA256%26X-Goog-Credential%3Dgcp-kaggle-com%2540kaggle-161607.iam.gserviceaccount.com/20260310/auto/storage/goog4_request%26X-Goog-Date%3D20260310T220409Z%26X-Goog-Expires%3D259200%26X-Goog-SignedHeaders%3Dhost%26X-Goog-Signature%3D365ec060b0afb5b2e2658b9a47e73ba3251d4fe54c44e19f72da683778472bd1e02ce6be8320db4cf292082fa3d13273169e95d81e768fb8d8a1c016df283af1eaab14a48eebeae1f1a32cee261e88196673820e15537c9edbc5eb3da61f03406a14082b1377f5d657b4607db12fc3437dcfb87eb981972abdb6f9feee9fe1c171a48be61f6296c928a878b2ca329e49868c4f0eb7ab8fe2206629c968677973822f023c745e577dfa30bc76a1b3cb7f5f304ef347fad2a37fd75b3b8b4bf0b97bd9ef3012c339a2d79f50cf2451eaba336a626a69062e6fe9922eed7080421cc352770401a1c6697292b226ad4fccf882504e2999397b009d68f231d579f135)**

The notebook will:
- Download the tea leaf disease dataset automatically from Kaggle
- Train a baseline ResNet50 model (90% accuracy)
- Generate your `submission.csv`
- Give you a green download button for your predictions

---

### Step 2 — Run All Cells

Run every cell from top to bottom.  
In the last cell set your name:
```python
YOUR_NAME = "your_name_here"
```

Then click the green **⬇️ Download** button that appears.

---

### Step 3 — Submit to GitHub

1. Go to [submission/](https://github.com/JHARILOVA/Tea_Leaf_Disease_Dataset/tree/main/submission) folder
2. Click **Add file → Upload files**
3. Upload your `YOUR_NAME_submission.csv`
4. At the bottom select **"Create a new branch"** — NOT commit to main
5. Click **Propose changes**
6. Click **Create pull request**

GitHub automatically evaluates your submission and posts your score as a comment on the PR. Your rank updates on the leaderboard instantly.

---

## 🏆 Leaderboard

Rankings update automatically after every submission.

👉 [View Live Leaderboard](leaderboard/README.md)

---

## 🌿 About the Dataset

The Tea Leaf Disease Dataset contains **885 images** across **8 disease categories**.  
The data is split as follows:

| Split | Images | Purpose |
|-------|--------|---------|
| Train | 601 | Model training |
| Validation | 107 | Monitor training progress |
| Hidden test | 177 | Leaderboard scoring |

### Disease Classes

| Class | Description |
|-------|-------------|
| Anthracnose | Fungal disease causing dark lesions on leaves |
| Algal Leaf | Green or orange algal growth on leaf surface |
| Bird Eye Spot | Small circular spots with dark borders |
| Brown Blight | Brown discoloration of leaf tissue |
| Gray Light | Gray lesions caused by fungal infection |
| Healthy | No disease present |
| Red Leaf Spot | Red or purple spots on leaves |
| White Spot | White powdery spots on leaves |

---

## 📏 Evaluation

Your submission is scored on **177 hidden test images** using:

| Metric | Description |
|--------|-------------|
| Accuracy | Correct predictions / total predictions |
| F1 (macro) | Average F1 score across all 8 classes equally |

Your `submission.csv` must have:
- One disease name per row
- No header
- Exactly **177 predictions**
- Labels matching exactly one of the 8 class names below

### Valid Labels
```
Anthracnose
algal leaf
bird eye spot
brown blight
gray light
healthy
red leaf spot
white spot
```

### Example submission.csv
```
Anthracnose
healthy
bird eye spot
brown blight
algal leaf
...
```

---

## 💡 Ideas to Beat the Baseline

The baseline uses ResNet50 with only `layer4` unfrozen and targets ~70% accuracy.  
Here are strategies to improve it:

| Strategy | Expected Gain |
|----------|--------------|
| Unfreeze layer3 + layer4 | +5–10% |
| Add deeper head (512 → 256 → 8) | +3–5% |
| Add BatchNormalization to head | +2–4% |
| Switch to ResNet101 | +3–7% |
| Switch to EfficientNet B3/B4 | +5–10% |
| Train more epochs with early stopping | +3–7% |
| Stronger augmentation (RandomErasing, MixUp) | +2–5% |
| Lower learning rate with warmup scheduler | +2–5% |
| Ensemble multiple models | +5–10% |

---

## 📋 Competition Rules

1. One `.csv` file per Pull Request in `submission/`
2. File must be named `YOUR_NAME_submission.csv`
3. One predicted label per row — no header
4. Exactly **177 predictions**
5. Labels must match exactly the 8 class names listed above
6. Do not modify any files outside `submission/`
7. Do not share or attempt to access the hidden test labels
8. Multiple submissions allowed — your best score is shown on the leaderboard

---

## ❓ Common Issues

**My PR shows Checks 0 / workflow not running**  
→ Make sure your file is inside the `submission/` folder and you opened a PR — not a direct commit to main.

**Wrong number of predictions**  
→ Your file must have exactly 177 rows. Re-run Cell 12 and Cell 13 in the notebook.

**Invalid label names**  
→ Labels are case-sensitive. Check the valid labels list above and the sanity check output in Cell 12.

**Score is 0%**  
→ Your file may be empty or corrupted. Re-download from the notebook and resubmit.

---

## 📬 Contact

For questions or issues open a GitHub Issue in this repository.

---

*Competition hosted on GitHub. Leaderboard updates automatically after every valid submission.*

The Tea Leaf Disease Dataset provides a collection of high-quality images aimed at identifying and classifying various diseases in tea leaves.
