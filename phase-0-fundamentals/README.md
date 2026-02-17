
# Phase 0: Fundamentals (Weeks 1-2)

Foundation phase covering essential ML concepts and LLM fundamentals. These are the building blocks you need before tackling RAG systems and agentic AI.

## Week 1: ML Core - The Essentials (22 hours)

### Day 1-2: Minimal Math You Need (6h)

**Why This Matters**: You cannot build effective RAG systems without understanding vectors and embeddings. When you use sentence-transformers to create embeddings, you need to understand what those 768 or 1536 dimensional vectors actually represent and why cosine similarity measures semantic closeness.

**Topics**:
- Vectors and embeddings: what a vector is, why a 1536-dimensional embedding represents meaning
- Cosine similarity: how you measure "closeness" between two texts (used daily in RAG)
- Basic probability: distributions, Bayes theorem (intuition, not formulas)
- Gradient descent: visual intuition of how a model "learns"

**Resources**:
- 3Blue1Brown "Essence of Linear Algebra" (YouTube, first 5 videos)
- StatQuest "Gradient Descent" and "Bayes Theorem"
- Jay Alammar "The Illustrated Word2Vec"

**Deliverable**: Jupyter notebook generating embeddings of spare parts descriptions, calculating cosine similarity, and showing which parts are "semantically similar"

### Day 3-4: Classical Models You Must Know (6h)

**Why This Matters**: While LLMs get all the attention, production systems still use XGBoost and Random Forest extensively for structured data. Knowing when to use an LLM versus when to use XGBoost is a critical skill.

**Topics**:
- Supervised vs Unsupervised: classification, regression, clustering
- Logistic Regression: your baseline for classification
- Random Forest and XGBoost: most used in production for tabular data
- K-Means: for segmentation and clustering
- Evaluation metrics: accuracy, precision, recall, F1, AUC-ROC (COMES UP IN INTERVIEWS)
- Overfitting: what it is, why it happens, how to prevent it

**Resources**:
- Scikit-learn User Guide tutorials
- StatQuest ML playlist (Random Forest, XGBoost, Cross Validation)
- "Hands-On ML" by Géron, chapters 1-4

**Deliverable**: Notebook comparing three models (Logistic Regression, Random Forest, XGBoost) on inventory data predicting "Will this part run out of stock in the next 7 days?"

### Day 5: Basic Feature Engineering (3h)

**Why This Matters**: Feature engineering is the skill that matters most in applied ML. How you transform raw data into features often determines success more than which model you choose.

**Topics**:
- Encoding: one-hot, label encoding, when to use each
- Feature creation: derived variables from existing data
- sklearn Pipeline and ColumnTransformer for production

**Deliverable**: Pipeline that takes raw movement data and generates features like rotation per item, consumption velocity, days until stockout, weekday patterns

### Weekend: Review + Practice (7h)

- Review everything learned, take notes for interviews
- Solve 2 LeetCode problems (Easy/Medium)
- Clean commits to GitHub with descriptive messages

## Week 2: LLMs - How They Work

[Details to be added when Week 2 begins]

## Skills After Phase 0

After completing this phase you will understand:
- How embeddings work and why they enable semantic search
- When to use classical ML vs when to use LLMs
- How to evaluate model performance with appropriate metrics
- How to build feature engineering pipelines for production
- How LLMs tokenize, process context, and generate text
- How to effectively prompt engineer and structure outputs
EOF