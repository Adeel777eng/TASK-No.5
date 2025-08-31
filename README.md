# TASK-No.5
# 🏷️ Auto Tagging Support Tickets Using LLM

## 🎯 Objective
Automatically tag support tickets into categories using Large Language Models (LLMs).  
This project demonstrates how zero-shot, few-shot, and fine-tuned LLMs can be leveraged to classify unstructured support tickets into multiple categories.

---

## 📊 Dataset
- **Source**: Free-text Support Ticket Dataset (you can use a synthetic or real-world dataset).
- **Structure**:
  - `ticket_id`: Unique ID for each ticket
  - `description`: The text of the support ticket
  - `true_tags`: Ground truth tags (for evaluation)

---

## 🤖 Models Applied
1. **Zero-Shot Classification**
   - Uses `facebook/bart-large-mnli` for out-of-the-box classification.
   
2. **Few-Shot Classification**
   - Injects few-shot examples into the prompt to guide LLM prediction.

3. **Fine-Tuned LLM**
   - Fine-tuned `bert-base-uncased` (or any transformer) on labeled support tickets.
   - Outputs top-3 predicted tags per ticket.

---

## ⚙️ Steps Performed
1. **Data Preprocessing**
   - Cleaned text (lowercasing, removing special characters).
   - Split into train/test sets.

2. **Zero-Shot Classification**
   - Used Hugging Face `pipeline` with candidate tags.
   - Generated top-3 tags per ticket.

3. **Few-Shot Prompting**
   - Crafted prompts with 3–5 examples to improve classification accuracy.

4. **Fine-Tuning**
   - Tokenized dataset using Hugging Face `AutoTokenizer`.
   - Fine-tuned a transformer model with cross-entropy loss.

5. **Evaluation**
   - Metrics used:
     - Accuracy
     - Precision, Recall, F1-score
     - Coverage@3 (if true tag is in top-3 predictions)

---

## 📈 Key Results (Example)
| Method           | Accuracy | F1-score | Coverage@3 |
|------------------|----------|----------|------------|
| Zero-Shot        | 0.70     | 0.68     | 0.85       |
| Few-Shot         | 0.78     | 0.75     | 0.90       |
| Fine-Tuned Model | 0.85     | 0.83     | 0.95       |

---

## 🛠️ Skills Demonstrated
- Prompt engineering (zero-shot, few-shot)
- LLM fine-tuning with Hugging Face Transformers
- Multi-class and multi-label text classification
- Evaluation of classification models
- Practical ML pipeline design for NLP tasks

---

## 🚀 Future Improvements
- Add multilingual support for support tickets.
- Deploy fine-tuned model via FastAPI/Gradio for real-time tagging.
- Incorporate active learning for continuous improvement.
- Use larger instruction-tuned models (e.g., GPT, LLaMA).

---

## 📂 File Structure
