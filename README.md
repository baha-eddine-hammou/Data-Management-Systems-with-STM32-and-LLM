# STM32 with Edge AI: Temperature Management System  

This repository documents my journey of integrating a Machine Learning model into an **STM32F407VG** microcontroller for a real-time temperature management system, as part of the **"EDGE IA POUR LE DIAGNOSTIC" PFE** subject proposed by **Actia** and supervised by **Mrs. Ibtissem Malouche**.

---

## Overview  

The project integrates:  
- **Hardware:**  
  - STM32F407VG Microcontroller  
  - DS1621 Temperature Sensor  
  - 2x16 LCD Display  
- **Software:**  
  - TensorFlow Lite for Microcontrollers  
  - STM32CubeMX and STM32Cube.AI  

The model provides real-time temperature recommendations:  
- **Cool (<0.3)**: Recommend cooling.  
- **Acceptable (0.3–0.7)**: Temperature is fine.  
- **Heat (>0.7)**: Recommend heating.  

---

## Attempts at Model Compression  

### 1. T5-Small with Knowledge Distillation  
- Shrunk using TensorFlow Lite with Knowledge Distillation and dataset augmentation.  
- **Outcome:** Still too large for STM32F4 memory.  

### 2. MobileBERT with Quantization  
- Applied quantization for size reduction.  
- **Outcome:** Good results, but size still exceeded memory limits.  

### 3. Custom Sequence-to-Sequence Model  
- Designed a lightweight sequence-to-sequence model tailored to the use case.  
- **Outcome:** Successfully achieved a small-enough size (~900KB).  

---

## Results  

- Successfully deployed the **custom sequence-to-sequence model** on the STM32F407VG.  
- Encountered challenges with TensorFlow Lite integration, STM32 header files, and evolving tools.  
- Gained valuable experience in Edge AI and embedded systems.  

---

## File Structure  

- **`t5small_distilled.tflite`**: First attempt with T5-Small and Knowledge Distillation.  
- **`mobilebert_quantized.tflite`**: Second attempt with MobileBERT and Quantization.  
- **`custom_seq2seq.tflite`**: Final successful model for STM32 integration.  

---

