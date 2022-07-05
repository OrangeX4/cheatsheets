---
title: python
categories: language
---

## get started

### Flask Server

```python
from flask import Flask, request, Response
import json

app = Flask(__name__)


@app.after_request
def after_request(resp):
    resp.headers['Access-Control-Allow-Origin'] = '*'
    resp.headers['Access-Control-Allow-Method'] = '*'
    resp.headers['Access-Control-Allow-Headers'] = 'x-requested-with,content-type'
    return resp


@app.route("/")
def hello_world():
  return "<p>hello world</p>"


@app.route("/api", methods=['POST'])
def predict_api():
  data = request.json
  result = data
  return Response(json.dumps(result), mimetype='application/json')



if __name__ == '__main__':
  app.run(debug=False, port=7685, host='0.0.0.0')
```
