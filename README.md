# MediTranscribe: AI-Powered Multilingual OPD Prescription Transcription

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

MediTranscribe is a project developed for the **BHASHINI Domain Innovation Challenge 1.0**. It aims to solve transcription inefficiencies in hospital Out-Patient Departments (OPDs) by providing a seamless, AI-powered multilingual transcription service.

## 📝 Problem Statement

In many Indian healthcare settings, the process of documenting patient prescriptions is inefficient and prone to errors due to:

* [cite_start]**Manual Errors:** Manual transcription of spoken prescriptions leads to significant inaccuracies and delays. [cite: 5, 6]
* [cite_start]**Language Barriers:** Doctors and patients communicate in a wide variety of Indian languages and dialects, which are often not supported by standard transcription software. [cite: 7]
* [cite_start]**Fragmented Records:** The lack of a standardized, digital system results in fragmented and unstructured medical records, hindering data-driven healthcare. [cite: 8, 9]

## ✨ Core Features

Our vision is to enable seamless digital prescriptions with the following features:

* [cite_start]**Accurate Transcription:** AI-powered speech-to-text to capture spoken prescriptions with high accuracy. [cite: 19, 21]
* [cite_start]**Multilingual Support:** Natively supports various Indian languages and dialects, breaking down communication barriers. [cite: 22, 24]
* [cite_start]**Standardized Data Output:** Generates structured medical data compliant with the **FHIR standard** for easy integration with hospital information systems (HIS) and the Ayushman Bharat Digital Mission (ABDM) ecosystem. [cite: 25, 26]

## ⚙️ Technology Stack

The project leverages a modern stack of AI and web technologies:

| Component        | Technology / Tool                                     |
| ---------------- | ----------------------------------------------------- |
| **Backend API** | Python (FastAPI / Flask)                              |
| **Speech-to-Text** | Bhashini API                          |
| **NLP & NER** | spaCy, BERT / IndicBERT                               |
| **Translation** | Bhashini IndicTrans2 API                              |
| **Data Format** | FHIR Standard                                         |
| **Language Data** | Udyat API                                             |

[cite_start][cite: 92, 93, 94, 95, 96, 97]

## 🚀 Project Workflow

The application follows a robust pipeline to process audio from input to structured output:

1.  [cite_start]**Audio Input:** A doctor's spoken prescription is captured via a microphone or file upload. [cite: 46, 47]
2.  [cite_start]**Multilingual Speech Recognition:** The audio is fed into a Speech-to-Text model (like Whisper) to generate a raw text transcription. [cite: 35, 62, 64]
3.  [cite_start]**Medical Term Extraction (NER):** The transcribed text is processed by a Named Entity Recognition (NER) model to identify and extract key medical entities like `DRUG`, `STRENGTH`, `FREQUENCY`, and `DIAGNOSIS`. [cite: 37, 65, 67]
4.  [cite_start]**Contextual Correction:** (Future Scope) The system will perform corrections on identified terms based on medical context. [cite: 68, 70]
5.  [cite_start]**Translation & Normalization:** The extracted entities are translated and normalized using the **Bhashini API**, ensuring standardization across languages. [cite: 41, 71, 73]
6.  [cite_start]**Structured FHIR Output:** The final, processed information is structured into a FHIR-compliant JSON object, specifically a `MedicationRequest` resource, ready for system integration. [cite: 42, 54, 56]
7.  [cite_start]**System Integration:** The FHIR data can be seamlessly integrated with any ABDM-compliant Hospital Information System or EMR. [cite: 50, 52, 53]

## 🛠️ Setup and Installation

To get the project running locally, follow these steps:

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd meditranscribe
    ```

2.  **Create and activate a Python virtual environment:**
    ```bash
    # For macOS/Linux
    python3 -m venv venv
    source venv/bin/activate

    # For Windows
    python -m venv venv
    venv\Scripts\activate
    ```

3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    *(Note: We will create the `requirements.txt` file in a later step).*

## ▶️ How to Run

Once the setup is complete, run the FastAPI server with the following command:

```bash
uvicorn main:app --reload
