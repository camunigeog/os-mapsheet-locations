# OS map sheet locations

This dataset contains the grid references for the two OS map sheet systems:

 * New popular edition 7th edition ("7th edition"):  One-inch to the mile maps. 1952-1961. As listed here: http://maps.nls.uk/os/one-inch-seventh-series/ . The sheet numbers will be the same in earlier editions, e.g. 6th, 5th, etc. (See picture). The scale (the amount of zooming in) is one inch to the mile, but the grid lines themselves are 10km (10,000m). (Kilometres had been used on the continent for a long time.)
 * 1:50,000 scale series (i.e. metric) edition.
 

## Understanding OS map sheets and grid squares

There are two sets of squares: Grid squares (constant through all types of maps) and Map sheets (which changed positions in the 1970s).


### Grid squares

Each main grid square (e.g. TL) is consistent across the two types, and represents 100km - this corresponds to e.g. 381 006:

Example of TL 381006:

TL is the grid square as a whole, which is 100km.  
'3' represents 10km  
'8' represents 1km  
'1' represents 100m.

Thus the resolution is 100m.

The grid squares (100km x 100km) are shown divided into 100 boxes (i.e. 10x10), which are 10km x 1-km squares. Within that one could image further subdivision into another 100 squares, i.e. 1km x 1km, and again into another 100 squares, i.e. 100m x 100m. At this fine level, that would correspond to e.g. 538100 200600. 

So, we can express TL 381006 as a 6+6 reference, which theoretically gives us 1m resolution, i.e. the two extra digits (00) give us 10m then 1m resolution.


### Map sheets

The map sheets are an independent set of squares that overlay (and overlap) the grid. They have their own number, e.g. 161 (7th edition).

A particular map sheet can contain parts of several grid squares.

An overview of the editions at: http://maps.nls.uk/os/ .

 * New popular edition 7th edition ("7th edition"):  One-inch to the mile maps. 1952-1961. As listed here: http://maps.nls.uk/os/one-inch-seventh-series/ . The sheet numbers will be the same in earlier editions, e.g. 6th, 5th, etc.. The scale (the amount of zooming in) is one inch to the mile, but the grid lines themselves are 10km (10,000m). (Kilometres had been used on the continent for a long time.)
 * 1:50,000 scale series (i.e. metric) edition.

The one-inch maps continued to be produced until the 1970s, when they were superseded by the 1:50000-scale series.


### Example conversion of a location with a known grid square (e.g. TL)

Grid square letters can be converted to a grid number. The letter<>number conversion is constant between the different series. As noted above, a whole grid square is 100k.

In this example we have TL 381006 (this is an example which does have the grid square letters. The transformation from 6-digit reference to full 6+6 reference is as follows:

 1. Take TL, and lookup in the grid<>number conversion list, which is 5 (eastings, x, relates to longitude), and 2 (northings, y, relates to latitude).
 2. Break the 6 digit figure into two, i.e. 381 006
 3. Add two digits to each block, to add in the 10m then 1m resolution i.e. 38100 00600
 4. Add the 52 (i.e. TL) to the start of the blocks, i.e. 538100 200600.
 5. At this stage, we can now use standard grid<>latlon conversion algorithm.

Ultimately, if we have the TL (i.e. 52) which is the grid square, then we can get a latlon.


### Number of squares

 * 7th series: 45 squares x 40 squares
 * 1:50,000 series: 40 squares x 40 squares

These facts mean that, knowing the northing/easting values in the bottom-left, we can generate the top-right northing/easting values, and thus have a range for each map.
 

### Generation of the lookup spreadsheets

 * 7th series: Looked up manually by looking at the bottom-right corner of http://maps.nls.uk/os/one-inch-seventh-series/
 * 1:50,000 series: Copied from https://github.com/TimSC/ostn02python/blob/master/OSGB.py#L213

 
