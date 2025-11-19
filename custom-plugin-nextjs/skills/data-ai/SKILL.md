---
name: data-ai-skills
description: Master machine learning, data engineering, AI engineering, LLMs, prompt engineering, and MLOps. Build intelligent systems with Python.
---

# Data & AI Engineering Skills

## Python Fundamentals

```python
import numpy as np
import pandas as pd

# NumPy arrays
arr = np.array([1, 2, 3, 4, 5])
arr_2d = np.zeros((3, 3))

# Pandas DataFrames
df = pd.DataFrame({
  'name': ['Alice', 'Bob'],
  'age': [25, 30]
})

df.describe()
df[df['age'] > 25]
```

## Machine Learning with Scikit-Learn

```python
from sklearn.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import accuracy_score

# Load and split data
X_train, X_test, y_train, y_test = train_test_split(
  X, y, test_size=0.2, random_state=42
)

# Train model
model = RandomForestClassifier(n_estimators=100)
model.fit(X_train, y_train)

# Evaluate
predictions = model.predict(X_test)
accuracy = accuracy_score(y_test, predictions)
```

## Deep Learning with PyTorch

```python
import torch
import torch.nn as nn

class SimpleNet(nn.Module):
  def __init__(self):
    super().__init__()
    self.fc1 = nn.Linear(10, 64)
    self.fc2 = nn.Linear(64, 1)
    self.relu = nn.ReLU()

  def forward(self, x):
    x = self.relu(self.fc1(x))
    return self.fc2(x)

model = SimpleNet()
optimizer = torch.optim.Adam(model.parameters())
loss_fn = nn.BCELoss()

# Training loop
for epoch in range(100):
  logits = model(X_train)
  loss = loss_fn(logits, y_train)
  loss.backward()
  optimizer.step()
```

## LLM Applications

```python
import openai

# OpenAI API
response = openai.ChatCompletion.create(
  model="gpt-4",
  messages=[
    {"role": "system", "content": "You are helpful assistant"},
    {"role": "user", "content": "Explain machine learning"}
  ]
)

print(response.choices[0].message.content)
```

## LangChain Framework

```python
from langchain.llms import OpenAI
from langchain.chains import LLMChain
from langchain.prompts import PromptTemplate

llm = OpenAI(temperature=0.7)

template = "Explain {topic} in simple terms."
prompt = PromptTemplate(template=template, input_variables=["topic"])

chain = LLMChain(llm=llm, prompt=prompt)
result = chain.run(topic="Machine Learning")
```

## Data Pipeline with Pandas

```python
# ETL Pattern
def load_data(path):
  return pd.read_csv(path)

def transform_data(df):
  df['date'] = pd.to_datetime(df['date'])
  df = df.dropna()
  return df

def load_to_db(df, connection):
  df.to_sql('table_name', connection, if_exists='append')

# Usage
df = load_data('data.csv')
df = transform_data(df)
load_to_db(df, conn)
```

## MLOps with MLflow

```python
import mlflow
import mlflow.sklearn

mlflow.set_experiment("my-experiment")

with mlflow.start_run():
  mlflow.log_param("n_estimators", 100)
  model = RandomForestClassifier(n_estimators=100)
  model.fit(X_train, y_train)
  accuracy = model.score(X_test, y_test)
  mlflow.log_metric("accuracy", accuracy)
  mlflow.sklearn.log_model(model, "model")
```

## Model Evaluation Metrics

```python
from sklearn.metrics import (
  accuracy_score, precision_score, recall_score, f1_score,
  roc_auc_score, confusion_matrix
)

accuracy = accuracy_score(y_test, y_pred)
precision = precision_score(y_test, y_pred)
recall = recall_score(y_test, y_pred)
f1 = f1_score(y_test, y_pred)
auc = roc_auc_score(y_test, y_pred_proba)
```

## Time Complexity in ML

- **Training**: O(n * m) where n=samples, m=features
- **Prediction**: O(m) per sample
- **Data Loading**: O(n) full scan
- **Inference**: Optimize with batching

## Key Concepts Checklist

- [ ] Python basics and NumPy
- [ ] Pandas data manipulation
- [ ] Data visualization (Matplotlib, Seaborn)
- [ ] Supervised learning (classification, regression)
- [ ] Unsupervised learning (clustering)
- [ ] Feature engineering
- [ ] Model evaluation and metrics
- [ ] Hyperparameter tuning
- [ ] Cross-validation
- [ ] Handling imbalanced data
- [ ] Deep learning basics
- [ ] LLM fine-tuning
- [ ] Prompt engineering
- [ ] MLOps pipeline setup

---

**Source**: https://roadmap.sh
