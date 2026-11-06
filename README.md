# Balochi Sentiment Studio

[**Open the live Streamlit interface**](https://sangatbaloch-balochi-sentiment.streamlit.app/)

Analyze Balochi text in its original script with positive, neutral and negative sentiment predictions.

## Features

- Sentence and paragraph analysis, with a separate prediction for each sentence.
- Black theme toggle and right-to-left text input.
- Download sentence predictions as CSV.
- Dataset statistics, evaluation results and a label-review workspace.

## Data and model

Training source: **Sir Uzair's data set**, supplied by the project owner, who reports that its labels were verified by the teacher. This verification has not been independently audited. The retained dataset contains 1,999 rows: 1,056 positive, 718 neutral and 225 negative.

The model is a character-trigram multinomial Naive Bayes research baseline. Reported held-out accuracy is 64.34%, macro F1 is 56.28%, and negative-class recall is 44.44%. The dataset remains imbalanced; predictions on new text are suggestions, not verified labels. Related examples from the same source may share wording, limiting generalization estimates.

The separate 30-row external review batch contains unverified sentiment suggestions and is **not included in training**. See [DATA_LICENSE.md](DATA_LICENSE.md) for source attribution and licensing. Fluent Balochi review is required before adding new training labels.

## Deployment

Streamlit Community Cloud runs `streamlit_app.py` on the `main` branch. The trained model and metrics are embedded in that file. Dependencies are pinned in `requirements.txt`.

## Run locally (optional)

```bash
python -m pip install -r requirements.txt
python -m streamlit run streamlit_app.py
```

Use the hosted interface link above for access without running a local server. Input is processed on the app server; this app does not write entered text to disk.
