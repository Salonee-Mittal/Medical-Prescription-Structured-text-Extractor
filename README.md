# 🧠 Medical Prescription Structured text Extractor using Gemini (Multimodal LLM)

## 📌 Project Overview
This project demonstrates how to extract **structured information** from **handwritten medical prescriptions** using **Gemini 2.0 Flash**, a multimodal large language model (LLM) by Google.

We extract key medical details like patient name, doctor name, medications (including dosage, frequency, duration), and evaluate the accuracy using **Word Error Rate (WER)** and **Character Error Rate (CER)**.

---

## 📷 Pipeline Overview
Prescription Image → Gemini Prompt + Vision → Text Output → Accuracy Evaluation

---

## 📦 Folder Structure
- data: prescription images + GroundTruth.csv
- output: extracted_text.csv, Evaluation_results.png
- scripts: Medical_Prescription(1).ipynb

---

## 🧠 Model: Google Gemini Flash 2.0

We use Gemini's vision capabilities to extract structured data from prescription images via prompts.

### Prompt Used and it's Structure:
-```You are an AI assistant that extracts structured data from a handwritten medical prescription. Please return the output in valid JSON format with the following schema:
{
  "date": str,
  "patient_name": str,
  "patient_age": str,
  "patient_gender": str,
  "patient_address": str,
  "doctor_name": str,
  "doctor_address": str,
  "doctor_specialty": str,
  "medicine_name": str,
  "medicine_dosage": str,
  "medicine_frequency": str,
  "medicine_duration": str,
  "diagnosis": str,
  "other_instructions": str
}

Notes:
- If any value is not found, return it as an empty string.
- Extract only the most important or first-mentioned medicine from the prescription.
- Use full forms for abbreviations if possible.
'''*

---

## Evaluation Strategy
We compare Gemini’s text output with manually annotated ground truth text using:
✅ Word Error Rate (WER): % of word-level errors
✅ Character Error Rate (CER): % of character-level errors
Both are computed using the Hugging Face evaluate library.

---

## How to Run
- Upload your images into data.
- Add your Gemini API key into the script
- Run Medical_Prescriptions(1).ipynb

View output in extracted_text.csv and evaluation results in Evaluation_results.png
