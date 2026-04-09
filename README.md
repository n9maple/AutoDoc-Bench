# AutoDoc-Bench

[Website](https://n9maple.github.io/AutoDoc-Bench)
This is the repository of paper AutoDoc-Bench, including a comprehensive QA dataset designed to evaluate document understanding capabilities.

## QA_dataset

### Overview

QA_dataset contains a large-scale question-answering dataset specifically designed to evaluate the multi-dimensional cognitive capabilities of **automated document understanding systems**. The dataset covers **144 document samples** and contains **10,250 carefully designed questions**, aiming to comprehensively evaluate model performance under different reasoning difficulties and complexities.

### Data Structure

```
QA_dataset/
├── 1_Literal_Perceptual_Understanding/
├── 2_Relational_Comparison_Reasoning/
├── 3_Numerical_Computation_and_Trend_Reasoning/
└── 4_Causal_and_Hypothetical_Scenario_Reasoning/
```

Each category folder contains several numbered folders (0, 1, 2, ...), and each folder corresponds to a document sample, containing:

- **qa.jsonl** - Contains all question-answer pairs for the document, in JSONL format (one JSON object per line)
- **report.pdf** - The corresponding original document/report PDF file


### Question Formats and Types

#### Question Category Distribution

| Category | Count | Percentage |
|------|------|------|
| Multiple Choice (MCQ) | 3,613 | 35.2% |
| Open-ended (Open) | 3,537 | 34.5% |
| Yes/No (YesNo) | 3,100 | 30.2% |
| **Total** | **10,250** | **100%** |

#### JSONL Format Details

Each question-answer pair contains the following fields:

```
  "category": "MCQ|Open|YesNo",           // Question category
  "question_type": "string",              // Question type (e.g., Part-to-Whole, Comparison, etc.)
  "question": "string",                   // Question text
  "answer": "string|A|B|C|D",             // Answer (text for open-ended, option letter for MCQ)
  "choice": ["Option A", "Option B", "Option C", "Option D"],  // Only exists for MCQ category
  "question_group": "number"                // Optional: Question group ID, only exists for YesNo category}
```