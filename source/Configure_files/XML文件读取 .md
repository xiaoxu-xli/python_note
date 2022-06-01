# XML文件读取 

20220601  
https://mlhive.com/2022/02/read-and-write-pascal-voc-xml-annotations-in-python  

```
def get_bounding_box(xml_path):
    """
    this function used for get the bounding box position of the annotation
    :param xml_path: xml file path
    :return: left bounding box, right bounding box
    """
    dom = ET.parse(xml_path)
    annotation = dom.getroot()

    height = int(annotation.find("size")[0].text)
    width = int(annotation.find("size")[1].text)
    channels = int(annotation.find("size")[2].text)

    bbox_coordinates = []
    left_bounding_box = {}
    right_bounding_box = {}
    for member in annotation.findall('object'):
        class_name = member[0].text  # class name
        print(class_name)
        if class_name.find('1') >= 0:
            left_bounding_box['x_min'] = int(member[4][1].text)
            left_bounding_box['x_max'] = int(member[4][3].text)
            left_bounding_box['y_min'] = int(member[4][0].text)
            left_bounding_box['y_max'] = int(member[4][2].text)
        elif class_name.find('2') >= 0:
            right_bounding_box['x_min'] = int(member[4][1].text)
            right_bounding_box['x_max'] = int(member[4][3].text)
            right_bounding_box['y_min'] = int(member[4][0].text)
            right_bounding_box['y_max'] = int(member[4][2].text)

    print('left', left_bounding_box)
    print('right', right_bounding_box)
    return left_bounding_box, right_bounding_box
```
