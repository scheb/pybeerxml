# pybeerxml

A simple BeerXML parser for Python


[![Build Status](https://img.shields.io/travis/hotzenklotz/pybeerxml.svg?style=flat-square)](https://travis-ci.org/hotzenklotz/pybeerxml)
[![PyPi Version](https://img.shields.io/pypi/v/pybeerxml.svg?style=flat-square)](https://pypi.python.org/pypi?:action=display&name=pybeerxml&version=1.0)

Parses all recipes within a BeerXML file and returns <Recipe> object containing all ingredients, style information and metadata.
OG, FG, ABV and IBU are calculated from the ingredient list. (your milage may vary)

## Installation

```
pip install pybeerxml
```

## Usage

```
from pybeerxml import Parser

path_to_beerxml_file = "/tmp/SimcoeIPA.beerxml"

parser = Parser()
recipes = parser.parse(path_to_beerxml_file)

for recipe in recipes:

    # some general recipe properties
    print recipe.name
    print recipe.brewer

    # calculated properties
    print recipe.og
    print recipe.fg
    print recipe.ibu
    print recipe.abv

    # iterate over the ingredients
    for hop in hops:
        print hop.name

    for fermentable in fermentables:
        print fermentable.name

    for yeast in yeasts:
        print yeast.name
```

## Testing

Unit test can be run with PyTest:
```
py.test tests
```

## License

MIT