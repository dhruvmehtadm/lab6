# geostats

[geostats](http://www.intermezzo-coop.eu/mapping/geostats/) is a tiny standalone JS library for classification released by [Simon Georget](http://www.intermezzo-coop.eu/) under MIT license.

Other contributors : [Doug Curl](http://kgs.uky.edu/kgsmap/ukengage/) (Jenks2 algorithm), [Casey Thomas](http://cpt.ph/), [Dreamind](https://github.com/dreamind), [cricri](https://github.com/cricri)

## It currently supports

- equal intervals
- quantiles
- standard deviation
- arithmetic progression
- geometric progression
- jenks (natural breaks) - 2 methods
- uniques values
- user defined classification

and **few statistical methods**

To use it, just download the geostats package and include the following line into your html page :

```html
<script type="text/javascript" src="path/to/lib/geostats.min.js"></script>
```

**Please see the samples page to understand how it works!**

# API

## Attributes :

- _serie_ : contains the statistic population. Default : empty.
- _separator_ : used to separate ranges values, by default : ' - '
- _legendSeparator_ : by default, equals to _separator_ value
- _method_ : give information regarding the classification method used. Default : empty.
- _bounds_ : classification bounds
- _ranges_ : classification ranges
- _colors_ : classification colors
- _debug_ : default value `false`. When set to `true` , provide useful debug message regarding objects and properties.
- _silent_ : default value `false`. If silent, do no trigger alert() message when inputs are incorrects but display console.log() messages

## Methods :

**Statistics :**

- _min()_ : return the min value
- _max()_ : return the max value
- _sum()_ : return the sum of the population
- _pop()_ : return the number of individuals
- _mean()_ : return the mean
- _median()_ : return the median
- _variance()_ : return the variance
- _stddev()_ : return the standard deviation
- _cov()_ : return the coefficient of variation

**Classification :**

- _getClassEqInterval(nbClass)_ : Perform an equal interval classification and return bounds into an array. Alias : _getEqInterval(nbClass)_
- _getClassStdDeviation(nbClass)_ : Perform a standard deviation classification and return bounds into an array. Alias : _getStdDeviation(nbClass)_
- _getClassArithmeticProgression(nbClass)_ : Perform an arithmetic progression classification and return bounds into an array. Alias : _getArithmeticProgression(nbClass)_
- _getClassGeometricProgression(nbClass)_ : Perform a geometric progression classification and return bounds into an array. Alias : _getGeometricProgression(nbClass)_
- _getClassQuantile(nbClass)_ : Perform a quantile classification and return bounds into an array. Alias : _getQuantile(nbClass)_
- _getClassJenks(nbClass)_ : Perform a Jenks classification and return bounds into an array. Alias : _getJenks(nbClass)_ - optimised version / see #49
- _getClassJenks2(nbClass)_ : Perform a Jenks classification and return bounds into an array. Alias : _getJenks2(nbClass)_ - older version
- _getClassUniqueValues()_ : Perform a unique values classification and return bounds (values) into an array. Alias : _getUniqueValues()_
- _setClassManually()_ : Set a user defined classification based on passed array (Same array is returned). Useful to automatically set bounds/ranges and generate legend.

**Constructor methods :**

- _setSerie()_ : fill up the _serie_ attribute
- _setColors()_ : fill up the _colors_ attribute
- _setPrecision()_ : set precision on serie - only useful for float series. Can take no value (for automatic precision), or an integer between 0-20. By default, the precision will be computed automatically by _geostats_.

**Getters methods :**

- _getRanges(array)_ : return an array of classes range (_ranges_ value)
- _getRangeNum()_ : return the number/index of this.ranges that value falls into
- _getHtmlLegend(colors, legend, callback, mode, order)_ : return a legend in html format.<br>`colors` defines an array of colors; `legend` is used for giving the legend a different title; with `counter`, a particular counter value can be displayed; a function which should be applied to the legend boundaries is used in place of `callback`; `mode` is for different display modes of the value ranges; `order` refers to the sort order of values. For further details, please refer [to the code comment](https://github.com/simogeo/geostats/blob/master/lib/geostats.js#L1054) which accompanies the getHtmlLegend method.
- _getSortedlist()_ : return the sorted serie in text format
- _getClass()_ : return a given value class

**Internals methods :**

- _\_nodata()_ : check if _serie_ attribute if not empty
- _\_hasNegativeValue()_ : check if the serie contains any negative values
- _\_hasZeroValue()_ : check if the serie contains zero values
- _sorted()_ : return the sorted (asc) serie
- _info()_ : return information about the population in text format
- _setRanges()_ : fill up the _ranges_ attribute (array of classes range)
- _doCount()_ : perform count feature by classes, used to display count feature in legend

_Note : If you are looking for a nice JS library to format numbers for displaying, just rely on [numeraljs](http://numeraljs.com/)._

# MIT LICENSE

Copyright (c) 2011 Simon Georget

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
