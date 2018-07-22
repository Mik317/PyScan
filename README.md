# PyScan

This Vulnerability Scanner is written in Python, and combines injection of payloads with `AI` for the recognition of vulnerable sites.
It provide a very beautiful Web-based panel only for visualization of the data (written with `CherryPy`+`Jinja2`)

The console tool reports all the data as `session`:

Every `session` is characterized by the title, the date, the author and a simple description, and will be memorized in a `SQLite` db.
You can use sessions for see infos from the web-panel.

# Console Python Vuln

Included with the tool, there is a very simple an useful tool like `msf` : `cpv.py`, that you can use for see the sessions and some infos about them.

# Modules

Now, the scanner supports all the most important vulnerabilities, and test them using some modules that inject payloads.
The payloads are very simple and are utilized for see how the web application interact with the given input, while the last payload, is an `out of band` payload, that use a request to a simple web server that you launch (`CherryPy` powered) for obtain the assurrance that the web application is vuln to the chosen attack.

A simple example of this technique is shown in the following code section:
```html 
<img src="https://our-server.hostname.com/?token=SGkgTWlr&attack=html_inj" /> 
``` 

will send a GET request to our server for obtain the given resource, and so, our server will log the request, giving us the almost absolute certainty that the web application is vuln (in this case to HTML Injection).

Another simple example:
```html 
<script src="https://our-server.hostname.com/?token=SGkgTWlr&attack=xss"></script> (XSS Reflected)
or
<script>new Image("https://our-server.hostname.com/?token=SGkgTWlr&attack=xss")</script> (XSS DOM)
``` 

These payloads show the same technique, but testing the web application for XSS Vulnerability.

# AI (Artificial Intelligence)

The scanner provide a very simple and useful algorithm of machine learning, that using the collected data, search new ways for find vulnerable targets and escape WAFs.

The model, for now, is in developing, and must do some practice, but is a good function that I want implement.

# Utilities

In the utilities, you can find all the tools that are used for recon, data collecting, session manipulation, server out-of-band, DNS mapper and more.

In particular, the Out-Of-Band Server is a single tool that you must start apart.
For the server forwarding (without fight versus port forwarding), I recomend you to use `ngrok`, that provide a tunnel from your machine and the internet. The server and the entire platform, are developed using this tool for the forwarding of the service.

# Web Application
