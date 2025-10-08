# WAD

## Header

**A WAD file always starts with a 12-byte header. It contains three values:**

|Position|Length|Name|Description|
|---|---|---|---|
|0x00|4|identification|The ASCII characters "IWAD" or "PWAD".|
|0x04|4|numlumps|An integer specifying the number of lumps in the WAD.|
|0x08|4|infotableofs|An integer holding a pointer to the location of the directory.|

## Directory

**The directory associates names of lumps with the data that belong to them. It consists of a number of entries, each with a length of 16 bytes. The length of the directory is determined by the number given in the WAD header. The structure of each entry is as follows:**

|Offset|Length|Name|Content|
|---|---|---|---|
|0x00|4|filepos|An integer holding a pointer to the start of the lump's data in the file.|
|0x04|4|size|An integer representing the size of the lump in bytes.|
|0x08|8|name|An ASCII string defining the lump's name. The name has a limit of 8 characters, the same as the main portion of an MS-DOS filename. The name must be nul-terminated if less than 8 characters; for maximum tool compatibility, it is best to pad any remainder with nul characters as well.|

## Vertex Structure

|Offset|Size (bytes)|C99 type|Description|
|---|---|---|---|
|0|2|int16_t|x|position|
|2|2|int16_t|y|position|