PostgreSQL
=========

Brief introduction to the theory 
----------
Minerva structure its data in a PostgreSQL database. PostgreSQL is an open source object-relational database system. 
----------

Example
----------
.. code-include :: :func:`os.path.join`


```python
def kelvin_to_celsius(temp_k):
    """
    Converts temperature in Kelvin
    to Celsius.
    """
    assert temp_k >= 0.0, "ERROR: negative T_K"
    temp_c = temp_k + 273.15
    return temp_c
```

