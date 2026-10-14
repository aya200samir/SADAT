# SADAT Student Streamlit

Student-only complaint experience: free-text entry → original trained classifier → original compression-decision model + conservative extraction rules → review → save → track → submission-experience rating.

## Run

Python 3.11 or 3.12 recommended:

```bash
python -m pip install -r requirements.txt
streamlit run app.py
```

The local SQLite database starts empty and is created on first run. The model artifacts are copied unchanged from the supplied training notebooks. `assets/design_reference.html` is the original supplied design reference; Streamlit recreates its visual identity using native Streamlit components and CSS rather than rendering the original HTML pixel-for-pixel.

**Limitations:** four research categories, synthetic training data, no institutional routing integration, no staff workflow, no genuine resolution updates, no resolution satisfaction rating. The rating is for submission experience only. The compression model predicts whether to apply the exact conservative extraction algorithm from the research script; it is not a generative summarizer. Keep personal complaints local; do not publish this version publicly with real student data without authentication, privacy/security review and production persistence.

## GitHub upload and Streamlit Cloud

Upload the **contents of this folder** to the repository root (not the ZIP itself).

On Streamlit Community Cloud, connect the repository, set the entrypoint to `app.py`, and deploy. `requirements.txt` will install dependencies. The two `.joblib` model files are included.

**Important:** This student-only prototype stores complaints in a local SQLite file. On typical hosted Streamlit instances, local storage is ephemeral and may be reset; the app does **not** provide secure, persistent student accounts or institution-grade access controls. Do not accept real identifiable student complaints or deploy as an official institutional service without production storage, authentication, access controls, and privacy/security review.
