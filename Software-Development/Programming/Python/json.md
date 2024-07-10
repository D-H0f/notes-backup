Name: json
Description:
	JSON (JavaScript Object Notation) is a subset of JavaScript syntax used as a
	lightweight data interchange format. The json module allows python code to
	interact with and manipulate JSON data.
Classes:
```python
JSONDecoder(
			*,
			object_hook=None,
			parse_float=None,
			parse_constant=None,
			strict=True,
			object_pairs_hook=None)
```
```
	simple json decoder. Performs the following translations in decoding by
	default:
     |  +---------------+-------------------+
     |  | JSON          | Python            |
     |  +===============+===================+
     |  | object        | dict              |
     |  +---------------+-------------------+
     |  | array         | list              |
     |  +---------------+-------------------+
     |  | string        | str               |
     |  +---------------+-------------------+
     |  | number (int)  | int               |
     |  +---------------+-------------------+
     |  | number (real) | float             |
     |  +---------------+-------------------+
     |  | true          | True              |
     |  +---------------+-------------------+
     |  | false         | False             |
     |  +---------------+-------------------+
     |  | null          | None              |
     |  +---------------+-------------------+
```
Methods:
```python
dumps(obj, *, skipkeys=False, ensure_ascii=True, check_circular=True,
	  allow_nan=True, cls=None, indent=None, separators=None, default=None,
	  sort_keys=False, **kw)
```
```
	Serialize 'obj' to a JSON formattid string.
```
```python
loads(s, *, cls=None, object_hook=None, parse_float=None, parse_int=None,
	 parse_constant=None, object_pairs_hook=None, **kw)
```
```
	Deserialize 's' (a string, bytes, or bytearray instance containing a JSON
	document) to a Python object.
	Example:
```
```python
	with open('filename.json') as file
		contents = file.readline()
	json_data = json.loads(contents)
```