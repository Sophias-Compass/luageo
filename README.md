luageo  
A ConTeXt module for drawing globes  
by Gavin Polhemus  
version: 2025.12.18  
License: GNU GENERAL PUBLIC LICENSE ver. 3, or any later version

# luageo
luageo is a simple [ConTeXt](https://wiki.contextgarden.net) [module](https://wiki.contextgarden.net/Input_and_compilation/Modules)
which provides a single MetaPost macro, `globe(<latitude>,<longitude>)`, for drawing globes in diagrams.
The arguments set the location which will appear centered on the globe.
The macro returns the boundaries of all visible countries and islands as a single MetaPost path.
This path can be drawn, filled, scaled, rotated and transformed like any MetaPost path.

ConTeXt LMTX is required for luageo.

## Installation

It is my hope that – by the time you are reading this – luageo is included in the ConTeXt distributions. If you want to install luageo yourself, follow the [module installation instructions](https://wiki.contextgarden.net/Input_and_compilation/Modules#Installation) at the ConTeXt Garden. 

## Example

```
\usemodule [luageo]
\startMPpage
   GlobeDiameter := 5cm ;
   fill fullcircle scaled GlobeDiameter withcolor .9white ;         % Fill a circle with the water color.
   fill globe(40, -108) scaled .5GlobeDiameter withcolor .75white ; % Draw the land.
   draw fullcircle scaled GlobeDiameter withcolor black ;           % Add a border, if you like.
\stopMPpage
```

## Documentation

A more detailed example can be found in the source file `t-luageo.mkxl`. Full documentation for luageo users is in `luageo-manual.pdf`, distributed with the module.

## Contribute to luageo

You can improve luageo by joining the conversation and contributing code at [luageo's GitHub repository](https://github.com/Sophias-Compass/luageo).
The [wiki](https://github.com/Sophias-Compass/luageo/wiki) contains information about the inner workings of luageo.
This information is intended at help contributers, but may also entertain some users.

## Data source 
The map data is adapted from the [CIA World DataBank II](http://www.evl.uic.edu/pape/data/WDB/).
At some point, this data was available at GLOBE Binaries DECODING : World Public Domain Dbase : F.Pospeschil, A.Rivera (1999), ftp://ftp.blm.gov/pub/gis/wdbprg.zip
(according to the [pst-geo maual](https://ctan.math.washington.edu/tex-archive/graphics/pstricks/contrib/pst-geo/doc/pst-geo-doc.pdf), p.4).

The luageo module was inspired by the MetaPost extension [mp-geo](https://melusine.eu.org/syracuse/G/git/?p=mp-geo.git;a=summary) by Christophe Poulain.
No code from mp-geo is used in luageo, but the map data came from the mp-geo extension.
