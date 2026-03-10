# 🍃 Tea Leaf Disease Classification Leaderboard

*No submissions yet. Be the first!*

**Total submissions:** 0 &nbsp;|&nbsp; **Participants:** 0

| Rank | Participant | Accuracy | F1 (macro) | Date |
|------|-------------|----------|------------|------|

---

## 🏆 About the Competition

**Goal:** Build the best tea leaf disease classifier  
**Classes:** 8 disease categories  
**Baseline accuracy:** ~70%  
**Metric:** Accuracy + F1 (macro)  

| Class | Description |
|-------|-------------|
| Anthracnose | Fungal disease causing dark lesions |
| Algal Leaf | Green/orange algal growth on leaves |
| Bird Eye Spot | Small circular spots with dark borders |
| Brown Blight | Brown discoloration of leaf tissue |
| Gray Light | Gray lesions from fungal infection |
| Healthy | No disease present |
| Red Leaf Spot | Red/purple spots on leaves |
| White Spot | White powdery spots on leaves |

---

## 📤 How to Submit

1. Open the Colab notebook and run all cells
2. Set `YOUR_NAME` in the last cell
3. Click the green **Download** button
4. Go to [submissions/](../submissions/) → **Add file → Upload files**
5. Select **Create a new branch** at the bottom — NOT commit to main
6. Click **Propose changes → Create pull request**
7. Your score appears here automatically

---

## 💡 Ideas to Beat the Baseline

| Strategy | Expected Gain |
|----------|--------------|
| Unfreeze layer3 + layer4 | +5–10% |
| Deeper head (512 → 256) | +3–5% |
| Add BatchNormalization | +2–4% |
| Try ResNet101 or EfficientNet | +5–10% |
| More epochs + early stopping | +3–7% |
| Stronger augmentation | +2–5% |
| Lower LR with warmup | +2–5% |
| Ensemble multiple models | +5–10% |

---

## 📋 Submission Rules

1. One `.csv` file per Pull Request in `submissions/`
2. One predicted label per row — no header
3. Exactly **177 predictions**
4. Labels must exactly match one of the 8 class names
5. Do not modify any files outside `submissions/`

### Valid class names
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

---

*⭐ = best score per participant. Updates automatically after every submission.*
