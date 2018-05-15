# PyScan

This Vulnerability Scanner is written in Python, and combines injection of payloads with `AI` for the recognition of vulnerable sites.
It provide a very beautiful Web-based panel (written with `CherryPy`+`Jinja2` that report all the `data` as `sessions`).

Every session is characterized by a title, the date, the author and a simple description, and will be memorized in a `SQLite` db.
You can use sessions from the Web panel or from the Console tool.
