# 🎵 Lyrics Mood Analyser

An NLP-powered tool that analyses the emotional content of song lyrics using a pre-trained transformer model. Paste any song lyrics and get an instant breakdown of emotions — visualised as an interactive chart and a line-by-line heatmap.

---

## 🎯 What It Does

- Detects **7 emotions** in song lyrics: joy, sadness, anger, fear, surprise, disgust, and neutral
- Visualises the **overall emotional profile** of a song as an interactive bar chart
- Shows the **emotion journey** through the song line by line using a heatmap
- Generates a **written mood summary** with intensity scores

---

## 🧠 How It Works

The project uses a technique called **transfer learning** — instead of training a model from scratch, it uses a pre-trained transformer model (`j-hartmann/emotion-english-distilroberta-base`) from HuggingFace that has already been trained on thousands of labelled emotional sentences.

The pipeline works like this:

1. **Input** — paste raw song lyrics as a string
2. **Preprocessing** — split lyrics into individual lines for better model accuracy
3. **Emotion Classification** — run each line through the transformer model, which returns a confidence score (0–1) for each of the 7 emotions
4. **Aggregation** — average scores across all lines to get the song's overall emotional profile
5. **Visualisation** — plot results using Plotly as a bar chart and heatmap

---

## 📊 Example Results

### Whitney Houston — *I Wanna Dance With Somebody*
Despite being an upbeat dance anthem, the model detected **neutral (0.52)** and **sadness (0.20)** as the dominant signals — because the lyrics reference time passing ("clock strikes upon the hour", "sun begins to fade"). This highlights an interesting limitation: text-only models can't capture musical context like tempo, melody, or vocal delivery.

### Taylor Swift — *Daylight*
*(Add your findings here after testing!)*

---

## 🔍 Key Concepts

| Concept | What it means |
|---|---|
| **NLP** | Natural Language Processing — teaching computers to understand human language |
| **Transfer Learning** | Using a model pre-trained by researchers and applying it to your own task |
| **Transformer Model** | A type of neural network architecture that understands context in text |
| **Emotion Classification** | Predicting which emotion(s) are present in a piece of text |
| **Confidence Score** | A number from 0–1 showing how strongly an emotion is present |

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| `Python` | Core programming language |
| `transformers` (HuggingFace) | Loading and running the pre-trained emotion model |
| `torch` | Powers the model behind the scenes |
| `pandas` | Organising results into a DataFrame |
| `plotly` | Interactive bar chart and heatmap visualisations |
| `Google Colab` | Cloud-based notebook environment |

---

## 🚀 How to Run It

1. Open the notebook in **Google Colab**
2. Run the install cell: `!pip install transformers torch`
3. Paste your song lyrics into the `lyrics` variable
4. Run all cells — charts will appear inline

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)]([your-colab-link-here](https://colab.research.google.com/drive/15SHHpM3J_XGY3GDVAJfAVBFRFuTmsWpc#scrollTo=c1zLzqoGPPRX))

---

## ⚠️ Limitations & Future Ideas

- The model analyses **text only** — it can't detect musical context (tempo, melody, instrumentation)
- Works best with **English lyrics**
- A future version could combine **audio features** (e.g. from Spotify's API) with lyrics for a richer multimodal analysis
- Could be extended into a **Streamlit web app** so anyone can use it without coding

---

## 👩‍💻 Author
Built by Darshna as part of a Data/ML/AI learning portfolio.

