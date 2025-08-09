# Assembly Instruction Generation

This repository contains the implementation of **Furniture Assembly Instruction Generation** using a fine-tuned **T5 Transformer** model. The system takes a structured **Bill of Materials (BoM)** for a furniture item and generates coherent, step-by-step natural language assembly instructions.

---

## Repository Structure

- `100k_Training_Furniture_Dataset.zip` – Training dataset (100,000 furniture examples)  
- `10K_Furniture_Testing_Data.zip` – Testing dataset (10,000 furniture examples)  
- `Furniture100K_Model_Train_Test.ipynb` – Main training and testing notebook  
- `Furniture_Assembly_Model_Training.ipynb` – Additional model training notebook  
- `TRAINING MODEL/` – Contains a Google Drive link to the trained model  
- `additionNN.ipynb` – Addition neural network implementation  

---

## How to Use

1. **Open** `Furniture100K_Model_Train_Test.ipynb` in Jupyter Notebook or Google Colab.

**Update the dataset paths** in `Furniture100K_Model_Train_Test.ipynb` to point to the extracted folders:
```python
train_data_path = "100k_Training_Furniture_Dataset/"
test_data_path = "10K_Furniture_Testing_Data/"
```

3. **Run all cells** to train and/or test the model.

---

## Model Overview

- **Architecture**: T5-small, fine-tuned for sequence-to-sequence instruction generation
- **Training Data**: 100,000 BoM–instruction pairs
- **Evaluation Metrics**:
- **BLEU**: 80.38
- **ROUGE-L**: 0.927

---

## Example

**Input (BoM):**
(Bedside_table (Tabletop) (Legs) (Drawers) (Fasteners))

**Generated Output:**
Combine Tabletop + Legs -> Tabletop_Legs_assembly
Combine Tabletop_Legs_assembly + Drawers -> Tabletop_Legs_assembly_Drawers_assembly
Combine Tabletop_Legs_assembly_Drawers_assembly + Fasteners -> Finished_Tabletop_Legs_assembly_Drawers_assembly_Fasteners_assembly

---

## Key Features

- **Automatically converts** structured BoMs into detailed, step-by-step assembly instructions
- **Large-scale dataset** with 100K (BoM, instruction) pairs
- **High BLEU and ROUGE scores**, indicating strong performance
- **Flexible and extendable** to other instruction-generation domains
