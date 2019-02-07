Level Format
===========================
| Type Of Objects|Bytes| 
| ------------- |:-------------:|
| Floors     | Beginning Bytes |
|Data Separator | 0x00 |
|Exit Door Coordinates| 2 Bytes (x,y)|
| Cat Flap #1 Coordinates | 2 Bytes (x,y)      |  
|Cat Flap #2 Coordinates | 2 Bytes (x,y)
|Special Background Decoration (Red Mirror in level 1)| 2 Bytes(x,y)
|Number of Normal Background Decorations (Yellow Mirrors in level 1)|1 Byte
|Normal Background Decoriation Coordinates | Previous byte value * 2 (x,y)
|Number of Bonus Background Decorations (Train in level 1)| 1 Byte
|Bonus Background Decoration Coordinates | Previous byte value * 2 Bytes (x,y)
|Bonus Background Decoration Attribute (?TODO CONFIRM?)| 1 Byte
|Data Separator | 0x00|
|Throwing Weapons 1-6 | 12 Bytes (x,y)
|Number of Normal Chirpy | 1 Byte
|Normal Chirpy Coordinates | Previous byte value * 2 (x,y)
|Number of Sunglasses Chirpy | 1 Byte
|Sunglasses Chirpy Coordinates | Previous byte value *2 (x,y)
|End of Level Separator | 0x00

**This is definitely subject to change as more poking about is done.**


By setting the coordinates to -1,-1 (0xFF,0xFF) the objects do not get created. 

i.e. Setting a Cat flap bytes to 0xFF 0xFF results in one less cat spawner in level.


Some bytes can be ommited all together, if the number of X byte is set to 0. 

i.e. If number of normal background decorations is 0x00, the following bytes for x/y coordiantes are omitted.
There **must** be at least one normal chirpy for sunglasses chirpy to exist.
