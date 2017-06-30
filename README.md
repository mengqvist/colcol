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
