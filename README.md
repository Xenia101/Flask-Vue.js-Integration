# Flask Vue.js Integration

python Flask + Vue.js Intergration

## Execution / Test Environment

- Window 10
- Python **3.6**
- Vue.js **lastest version**

## Issue

When Flask + Vue intergration, confrict a Jinja2 delimiter and Vue.js delimiter

Add python code at app.py

```python
class CustomFlask(Flask):
    jinja_options = Flask.jinja_options.copy()
    jinja_options.update(dict(
        block_start_string='(%',
        block_end_string='%)',
        variable_start_string='((',
        variable_end_string='))',
        comment_start_string='(#',
        comment_end_string='#)',
    ))
    
app = CustomFlask(__name__)
```

and ADD in main function

```python
app.config['SEND_FILE_MAX_AGE_DEFAULT'] = 0
```

## References 

https://github.com/yymm/flask-vuejs
