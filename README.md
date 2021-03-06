# Json2PascalVoc

Json2PascalVoc is a Python library for converting some special Json strings to PascalVOC format XML files.

## Installation

Use the package manager [pip](https://pip.pypa.io/en/stable/) to install Json2PascalVoc.



```bash
pip install Json2PascalVoc
```

Or download package from [GitHub](https://github.com/canerkaraguler/JsonToPascalVOC)

## Usage

```python
from Json2PascalVoc.Converter import Converter

myConverter = Converter()
# returns a Converter Object
myConverter.convertJsonToPascal("data.json")
# Converts Json to PascalVOC XML and saves the XML file to the related file path

```
An example data.json file is :
```json
{
   "data":[
      {
         "annotation":{
            "folder":"class1",
            "filename":"_ADC0362.jpg",
            "path":"~/Desktop/Dev/data/foo/train/class1/_ADC0362.jpg",
            "source":{
               "database":"Unknown"
            },
            "size":{
               "width":1500,
               "height":1500,
               "depth":3
            },
            "segmented":0,
            "object":[
               {
                  "name":"class1",
                  "pose":"Unspecified",
                  "truncated":0,
                  "difficult":0,
                  "bndbox":{
                     "xmin":579,
                     "ymin":584,
                     "xmax":924,
                     "ymax":1120
                  }
               },
               {
                  "name":"class1",
                  "pose":"Unspecified",
                  "truncated":0,
                  "difficult":0,
                  "bndbox":{
                     "xmin":120,
                     "ymin":400,
                     "xmax":1150,
                     "ymax":800
                  }
               }

            ]
         }
      },
      {
         "annotation":{
            "folder":"class1",
            "filename":"_ADC0373.jpg",
            "path":"~/Desktop/Dev/data/foo/train/class1/_ADC0373.jpg",
            "source":{
               "database":"Unknown"
            },
            "size":{
               "width":1500,
               "height":1500,
               "depth":3
            },
            "segmented":0,
            "object":[
               {
                  "name":"class1",
                  "pose":"Unspecified",
                  "truncated":0,
                  "difficult":0,
                  "bndbox":{
                     "xmin":487,
                     "ymin":558,
                     "xmax":798,
                     "ymax":942
                  }
               }
            ]
         }
      }
   ]
}
```
Notes:

1- "data" array of Json can contain multiple "annotation" objects for different images. 

2- "annotation" objects can contain multiple "object" attributes for multi object detecting in a single image.

3- PascalVOC formatted XML files are saved to the path that is given in "annotation.path" for each image/"annotation"

The output XML for an image is like :
```xml
<?xml version="1.0" encoding="UTF-8"?>
<annotation>
   <folder name="folder">class1</folder>
   <filename name="filename">_ADC0362.jpg</filename>
   <path name="path">~/Desktop/Dev/data/foo/train/class1/_ADC0362.jpg</path>
   <source>
      <database name="database">Unknown</database>
   </source>
   <size>
      <width name="width">1500</width>
      <height name="height">1500</height>
      <depth name="depth">3</depth>
   </size>
   <segmented name="segmented">0</segmented>
   <object>
      <name name="name">class1</name>
      <pose name="pose">Unspecified</pose>
      <truncated name="truncated">0</truncated>
      <difficult name="difficult">0</difficult>
      <bndbox>
         <xmin name="xmin">579</xmin>
         <ymin name="ymin">584</ymin>
         <xmax name="xmax">924</xmax>
         <ymax name="ymax">1120</ymax>
      </bndbox>
   </object>
   <object>
      <name name="name">class1</name>
      <pose name="pose">Unspecified</pose>
      <truncated name="truncated">0</truncated>
      <difficult name="difficult">0</difficult>
      <bndbox>
         <xmin name="xmin">120</xmin>
         <ymin name="ymin">400</ymin>
         <xmax name="xmax">1150</xmax>
         <ymax name="ymax">800</ymax>
      </bndbox>
   </object>
</annotation>
```





## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.


## License
[MIT](https://choosealicense.com/licenses/mit/)