# Cross-Cultural Emotional Co-Speech Facial Expression Generation Model

**Cue Weighting of Prosody and Facial Expressions in Japanese, Mandarin, and English**

> 🚧 **Pre-release** — shared for early feedback before IRB submission. Contents subject to revision.

---

## 🎧 [→ Live Demo Page with Audio Players](https://YOUR_USERNAME.github.io/YOUR_REPO_NAME/)

*(Enable GitHub Pages after pushing — see setup instructions below)*

---

## What is this?

This is the stimulus generation pipeline for a PhD research project in cross-cultural psychology and HCI. The central question: **how do people from different language backgrounds weight speech prosody vs. facial expressions when judging emotion?**

To study this, we generate stimuli that pair emotional speech (TTS) with 3D avatar facial animations in three configurations:
- **Congruent** — speech emotion = facial expression
- **Incongruent** — speech emotion ≠ facial expression

## Pipeline

```
Text (JP / ZH / EN)
    ↓
TTS Model  ──→  Audio (Happy, Angry, Sad, Fear, Neutral…)
    ↓
Speech-to-FacialExpression Model
    ↓
3D Avatar (Unreal Engine 5 MetaHuman)
  • Lip-sync (ARKit blendshapes)
  • Emotion expression (congruent / incongruent)
    ↓
Stimuli Clips → Perception Experiment → Analysis
```

## TTS Models Evaluated

| Model | Emotion Control | Language Transfer |
|-------|----------------|-------------------|
| **CosyVoice2** | Reference WAV + CFG | Cross-lingual ✓ |
| **IndexTTS2** | Emotion vector (8-dim) | Cross-lingual ✓ |
| **VoxCPM2** | CFG strength scaling | Cross-lingual ✓ |
| **OpenVoice v2** | Tone color transfer | Cross-lingual ✓ |
| **X-Voice** | Voice conversion | Cross-lingual ✓ |

## Samples in this repo

```
docs/
├── index.html              ← demo page (GitHub Pages)
├── audio/
│   ├── original/           ← 6 reference clips (JP female speaker)
│   │   ├── happy.wav
│   │   ├── anger.wav
│   │   ├── sad.wav
│   │   ├── fear.wav
│   │   ├── disgust.wav
│   │   └── surprise.wav
│   └── tts/                ← cross-lingual outputs (1 sample × 5 emotions × 5 models)
│       ├── cosyvoice2/
│       ├── indextts2/
│       ├── voxcpm2/
│       ├── openvoice_v2/
│       └── x_voice/
└── video/
    └── hap01.mp4           ← 3D avatar lip-sync sample (happy, congruent)
```

## Research Status

| Stage | Status |
|-------|--------|
| TTS pipeline (5 models) | ✅ Complete |
| 3D avatar + lip-sync | ✅ Complete |
| Emotion trajectory TTS (TED-TTS / DCFG) | 🔄 In progress |
| IRB submission | 📋 Planned |
| Perception experiment | 📋 Planned |
| Analysis & writing | 📋 Planned |

---

*Audio samples are for research evaluation only — not for public redistribution.*
