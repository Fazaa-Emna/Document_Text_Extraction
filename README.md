# 📝 **Intelligent Legal Document Parsing for French Text**

---

## 🚀 **Project Overview**
This project is dedicated to building an intelligent pipeline for parsing and extracting information from legal French documents. Legal documents often come with complex layouts and language, making accurate data extraction a challenging task. Our solution integrates state-of-the-art technologies to tackle this challenge, ensuring high accuracy in text extraction, structure, and summarization.

The pipeline is divided into two main notebooks, each addressing a critical stage of the document parsing workflow.

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

## 🎯 **Key Objectives**
1. **High OCR Accuracy**:
   - Ensure precise text extraction, especially for complex French legal language.
2. **Text Structuring**:
   - Convert raw extracted text into structured JSON for easy consumption by downstream systems.
3. **Enhanced Readability**:
   - Normalize and clean text to improve readability and accuracy.
4. **Scalable Pipeline**:
   - Design a robust pipeline capable of handling various legal document formats.

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
| **PDFPlumber**         | PDF Manipulation and type conversion             |

---

## 🌟 **Why This Project Matters**
Legal documents are critical and often densely formatted with complex language. Automating the extraction and structuring of data from such documents can:
- **Save Time**: Replace manual data entry with automation.
- **Reduce Errors**: Ensure accuracy in extracting sensitive legal information.
- **Enable Scalability**: Process large volumes of documents quickly and efficiently.
- **Unlock Insights**: Enable downstream applications such as legal analytics and decision-making systems.

