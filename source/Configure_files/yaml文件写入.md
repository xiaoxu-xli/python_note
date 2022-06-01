# yaml文件写入
Yaml文件写入  
http://www.pythonck.com/archives/docs/1-2/15-2/15011-2  

```
yaml_data = yaml_example_data
left_bounding_box, right_bounding_box = get_bounding_box(annotation_xml_path)
yaml_data['scan_info']['right_bounding_box'] = right_bounding_box
yaml_data['scan_info']['left_bounding_box'] = left_bounding_box
yaml_data['scan_info']['dicom_to_tif'] = False
yaml_data['scan_info']['adding_background'] = False
yaml_data['scan_info']['scan_root'] = scan_path
# 转换成yml字符串并写入文件
with open(yaml_write_path, "w") as yaml_file:
    yaml.dump(yaml_data, yaml_file)
```