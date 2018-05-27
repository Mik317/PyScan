# PyScan

This Vulnerability Scanner is written in Python, and combines injection of payloads with `AI` for the recognition of vulnerable sites.
It provide a very beautiful Web-based panel only for visualization of the data (written with `CherryPy`+`Jinja2`)

The console tool reports all the data as `session`:

Every `session` is characterized by the title, the date, the author and a simple description, and will be memorized in a `SQLite` db.
You can use sessions for see infos from the web-panel.
