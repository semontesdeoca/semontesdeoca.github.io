All studio.coop tools are open sourced through the [MIT license](#MIT-License) and have been developed in the spirit of a cooperation

* Table of Contents
{:toc}

## Shelves

### Animation Shelf (ANIM)

### Rigging Shelf (RIG)

### Development Shelf (DEV)

## Tools

## Plugins
The plugins

### coopMathNode
This node performs a custom mathematical expression. Inspired by the [asdkMathNode](https://apps.autodesk.com/MAYA/en/Detail/Index?id=212304226072872821&appLang=en&os=Win64), this node harnesses the power of the Maya Python Api 2.0 to crunch numbers within your node network - offering a faster alternative to normal expressions within Maya.

With support of up to three different inputs (a, b, c), this node allows you to calculate any type of expression, for example:

`(abs(a * b) * 10) / c`

and even with custom logic

`(b - 0.5 * c * a) if b - 0.5 * c * a >= 0 else 0`

Supports Python's mathematical [built-in functions](https://docs.python.org/2/library/functions.html) (e.g. abs(), max(), round()) and Python's [math package](https://docs.python.org/2/library/math.html) (e.g. pow(), cos(), pi), together with more additional functions, documented below:

#### clamp
`clamp(min, max, value)`

Clamps a _value_ between a _min_ and _max_ range.

#### saturate
`saturate(value)`

Saturates (clamps) a _value_ between 0 and 1.

#### lerp
`lerp(value1, value2, parameter)`

Linearly interpolates between _value1_ and _value2_ according to a _parameter_.

#### linstep
`linstep(min, max, value)`

Returns the percentage [between 0 and 1] of the distance between _min_ and _max_ (e.g. linstep(1, 3, 2.5) -> 0.75).

### coopPoseWeight
This node calculates the weight of a corrective blendshape by interpolating within poses. It takes into account a source and a target transform nodes, relative to a rotating pivot. Calculates the  difference between each vector and applies the weight of the blendshape accordingly. It also supports the possibility of setting the target twist, so that the node works with all 6 degrees of freedom.

#### setup



## MIT License

```
Copyright (c) 2017 studio.coop

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in all
    copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.
```
