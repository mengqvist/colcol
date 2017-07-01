# description of colcol project


## installation
```
pip3 install colcol
```

## color manipulations
First generate a color object.
```
from colcol import convert

#create from hex
x = convert.Color('#dd5f32')

#create from rgb
y = convert.Color((221,95,50))

#create from named color
z = convert.Color('darksalmon')
```


This object can be used to convert between different color representations.
```
#get rgb color
x.rgb()

#get hex color
x.hex()

#get hsl color (in where h, s and l are between 0 and 1)
x.hsl()
```

It can also be used for color manipulations. All these functions return a list of colors.
```
#get complementary color
x.complementary()

#get split complementary colors
x.split_complementary()

#get triadic colors
x.triadic()

#get square colors
x.square()

#get tetradic colors
x.tetradic()

#get analagous colors
x.analagous()

#get tins in equidistant steps to white
x.tints()

#get shades in equidistant steps to black
x.shades()

#get saturated versions of color in equidistant steps to complete saturation
x.saturate()

#get de-saturated versions of color in equidistant steps to complete de-saturation (grey)
x.desaturate()

#get split complementary color
x.next_color()
```

The generated colors can be visualized
```
convert.visualize(x.split_complementary())
```

## generating color scales


```
from colcol import scales
s = scales.rainbow()
```

```
#sequential scale to represent continuous variables, with two defined colors
s = scales.sequential(colors=['#543005', '#f6ee88'], step_num=5)

#with three defined colors
s = scales.sequential(colors=['#8c510a', '#d73027', '#ffffff'], step_num=5)

#with four defined colors
s = scales.sequential(colors=['#000099', '#990000', '#990099', '#ffffff'], step_num=5)
```

```
#diverging scale to represent continuous variables with a defined midpoint, with two defined colors. The mid color defaults to white.
s = scales.diverging(colors=['#8c510a', '#01665e'], step_num=5)

#with three defined colors. Used when one wants to define a mid color other than white.
s = scales.diverging(colors=['#8c510a', '#f6e8c3', '#01665e'], step_num=5)

#with four defined colors. The mid color defaults to white.
s = scales.diverging(colors=['#', '#', '#', '#'], step_num=5)

#with five defined colors. Used when one wants to define a mid color other than white.
s = scales.diverging(colors=['#', '#', '#', '#', '#'], step_num=5)
```


```
#qualitative scale to represent categories, factors etc.
s = scales.qualitative(scale=1, num_steps=5)
```
