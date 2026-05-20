# ECCE AskDesk Uganda — Data-Embedded Render Build

This version fixes the issue where Render shows:

```json
{"chunks":0,"faqs":0,"compliance_items":0}
```

The data is now embedded inside `app.py` as a fallback, while the normal `data/` folder is also retained.

## Deploy steps

Upload the contents of this unzipped folder to GitHub.

When you open GitHub, you must immediately see:

```text
app.py
frontend
data
requirements.txt
render.yaml
runtime.txt
Procfile
```

## Render settings

Build Command:

```bash
python -m pip install --upgrade pip setuptools wheel && pip install -r requirements.txt
```

Start Command:

```bash
python -m uvicorn app:app --host 0.0.0.0 --port $PORT
```

Pre-deploy Command: leave empty.

Root Directory: leave empty.

After deployment, open:

```text
https://YOUR-RENDER-LINK.onrender.com/api/status
```

You should see chunks, FAQs and compliance items above zero.
