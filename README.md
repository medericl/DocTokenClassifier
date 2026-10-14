# DocTokenClassifier

Word-level labeling of scanned forms ([FUNSD](https://guillaumejaume.github.io/FUNSD/)): each word is classified as **question**, **answer**, **header** or **other**.

DLIM S4 lab, done with a compact BERT (`google/bert_uncased_L-4_H-256_A-4`) and three input variants:

- **text**: words only
- **tokens**: position written as `<X_..> <Y_..>` tokens
- **embeddings**: learned x/y vectors added to token embeddings (LayoutLM-style)

## Results (validation, 400 steps, seed 42)

```
Variant      macro-F1  accuracy
text         0.562     0.657
tokens       0.538     0.620
embeddings   0.573     0.655
```

## Run

Open `S4_encoders_student.ipynb` in Colab with a GPU runtime and run all cells. The notebook exports `predictions_test.json`.
