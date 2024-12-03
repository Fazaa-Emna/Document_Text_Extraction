# 📝 **Intelligent Legal Document Parsing for French Text**

---

## 🚀 **Project Overview**
This project is dedicated to building an intelligent pipeline for parsing and extracting information from legal French documents. Legal documents often come with complex layouts and language, making accurate data extraction a challenging task. Our solution integrates state-of-the-art technologies to tackle this challenge, ensuring high accuracy in text extraction, structure, and summarization.

The pipeline is divided into three main notebooks, each addressing a critical stage of the document parsing workflow.

---

## 📂 **Project Structure**

### **1️⃣ Notebook 1: Image Preprocessing and Segmentation**
- **Goal**: Enhance document images for accurate OCR and segmentation into logical sections.
- **Tasks**:
  - Preprocess images using **OpenCV** for noise reduction and layout adjustment.
  - Segment documents into main sections:
    - **Title**
    - **Advice**
    - **General Information about the Complaint**
    - **Complaint Objective**
    - **Main Content of the Letter**
    - **Footer**
- **Technologies**:
  - 🖼️ **OpenCV**: Image preprocessing and segmentation.
  - 🗺️ **LayoutLMv3**: Layout-based document understanding for structured segmentation.
  - 🖊️ **Tesseract**: OCR testing for initial results.
  - 📄 **PDFPlumber**: PDF Manipulation and conversion to .png.

---

### **2️⃣ Notebook 2: OCR Text Processing and Structuring**
- **Goal**: Clean and structure OCR-extracted text into meaningful and actionable insights.
- **Tasks**:
  1. **OCR Extraction**:
     - Extract text using **PaddleOCR** for robust multi-language support.
  2. **Post-OCR Text Cleaning**:
     - Normalize text.
     - Correct OCR errors (e.g., spelling mistakes, punctuation issues) using **Hunspell** (French spell checker).
     - Ensure consistent formatting.
  3. **NER and POS Tagging**:
     - Apply **SpaCy** for Named Entity Recognition (NER) and Part-of-Speech (POS) tagging to enrich the extracted data.
  4. **Summarization and Structuring**:
     - Leverage **Falcon-7B-Instruct**, a powerful LLM, to summarize and structure cleaned text into JSON format.
- **Technologies**:
  - 📖 **PaddleOCR**: OCR engine for French legal text.
  - 🔤 **Hunspell**: French spelling correction.
  - 🧠 **SpaCy**: NER and POS tagging.
  - 🤖 **Falcon-7B-Instruct**: Summarization and structuring via state-of-the-art LLMs.

---

### **3️⃣ Notebook 3: Fine-Tuning YOLOv9 for Hand Signature Detection**
- **Goal**: Train a custom YOLOv9 model to detect hand signatures in scanned complaint documents.
- **Tasks**:
  - **Dataset Preparation**:
    - Collected and labeled a dataset of **1950 images** containing hand signatures using **Roboflow**.
    - Applied **data augmentation** to simulate real-world scanned conditions:
      - **Scaling**, **rotation**, **shearing**, **grayscale conversion**, **blur**, and **noise addition**.
    - Final dataset size after augmentation: **4980 images**, split into:
      - **Training Set**: 4545 images (91%)
      - **Validation Set**: 184 images (4%)
      - **Test Set**: 251 images (5%).
    - [View the collected dataset on Roboflow](https://app.roboflow.com/smart-conseil-lvw6i/signature_detector/browse?queryText=&pageSize=50&startingIndex=0&browseQuery=true).
  - **Model Fine-Tuning**:
    - Fine-tuned the YOLOv9 model on this dataset to detect hand signatures.
    - Optimized hyperparameters to achieve high precision and recall.
  - **Evaluation**:
    - The model was evaluated on metrics such as **mAP@0.5** (90%+) and **mAP@0.5:0.95** (80%).
    - Demonstrated robustness in detecting signatures under various conditions, including complex document layouts.

- **Technologies**:
  - ⚙️ **YOLOv9**: Object detection model for hand signature identification.
  - 🖼️ **Roboflow**: Dataset preparation and augmentation.
  - 📊 **Matplotlib**: Visualization of training metrics and evaluation results.

---

## 🎯 **Key Objectives**
1. **High OCR Accuracy**:
   - Ensure precise text extraction, especially for complex French legal language.
2. **Text Structuring**:
   - Convert raw extracted text into structured JSON for easy consumption by downstream systems.
3. **Enhanced Readability**:
   - Normalize and clean text to improve readability and accuracy.
4. **Scalable Pipeline**:
   - Design a robust pipeline capable of handling various legal document formats.
5. **Signature Detection**:
   - Enable accurate detection of hand signatures within scanned complaint documents.

---

## 🛠️ **Technologies Used**
| **Technology**         | **Purpose**                                      |
|------------------------|--------------------------------------------------|
| **LayoutLMv3**         | Document layout analysis and segmentation.       |
| **OpenCV**             | Image preprocessing and noise reduction.         |
| **Tesseract**          | Initial OCR testing.                             |
| **PaddleOCR**          | Final OCR engine for accurate text extraction.   |
| **Hunspell**           | French spelling correction.                      |
| **Falcon-7B-Instruct** | Summarization and data structuring.              |
| **SpaCy**              | NER and POS tagging.                             |
| **PDFPlumber**         | PDF Manipulation and type conversion.            |
| **YOLOv9**             | Fine-tuned for hand signature detection.         |
| **Roboflow**           | Dataset preparation and augmentation.            |
| **Matplotlib**         | Visualization of training metrics.               |

---

## 🌟 **Why This Project Matters**
Legal documents are critical and often densely formatted with complex language. Automating the extraction and structuring of data from such documents can:
- **Save Time**: Replace manual data entry with automation.
- **Reduce Errors**: Ensure accuracy in extracting sensitive legal information.
- **Enable Scalability**: Process large volumes of documents quickly and efficiently.
- **Unlock Insights**: Enable downstream applications such as legal analytics and decision-making systems.
- **Improve Signature Detection**: Simplify validation of document authenticity by detecting hand signatures with high accuracy.
