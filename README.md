# hjson-py

[![Build Status](https://img.shields.io/travis/hjson/hjson-py.svg?style=flat-square)](http://travis-ci.org/hjson/hjson-py)
[![PyPI version](https://img.shields.io/pypi/v/hjson.svg?style=flat-square)](https://pypi.python.org/pypi/hjson)

[Hjson](http://hjson.org), the Human JSON. A configuration file format for humans. Relaxed syntax, fewer mistakes, more comments.

![Hjson Intro](http://hjson.org/hjson1.gif)

Hjson works with Python 2.5+ and Python 3.3+

The Python implementation of Hjson is based on [simplejson](https://github.com/simplejson/simplejson). For other platforms see [hjson.org](http://hjson.org).

# Installation

- `pip install hjson`

- or download from https://pypi.python.org/pypi/hjson

## Commandline

```
Usage:
  hjson [options]
  hjson [options] <input>
  hjson (-h | --help)
  hjson (-V | --version)

Options:
  -h --help     Show this screen.
  -j            Output as formatted JSON.
  -c            Output as JSON.
  -V --version  Show version.
```

E.g. `echo '{"json":"obj"}' | hjson`

# Usage

```python
import hjson
```

## Decoding Hjson

```python
text = """{
  foo: a
  bar: 1
}"""

hjson.loads(text)
```

Result:
```python
OrderedDict([('foo', 'a'), ('bar', 1)])
```

## Encoding Python object hierarchies

```python
hjson.dumps({'foo': 'text', 'bar': (1, 2)})
```

Result:
```
{
  foo: text
  bar:
  [
    1
    2
  ]
}
```

## Encoding as JSON

Note that this is probably not as performant as the simplejson version.

```python
hjson.dumpsJSON(['foo', {'bar': ('baz', None, 1.0, 2)}])
```

Result:
`'["foo", {"bar": ["baz", null, 1.0, 2]}]'`



# API

[hjson-py documentation](http://hjson.github.io/hjson-py/)

# History

[see history.md](history.md)
