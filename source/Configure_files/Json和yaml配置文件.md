# Json和yaml配置文件

20220520

https://www.cnblogs.com/bigberg/p/6430095.html  

## json
```
import json
with open('config/smith_mdct.json', 'r') as json_file:
    load_dict = json.load(json_file)
```

Json file 示例
```
{
    "scan_info": {
        "spacing": [
            0.60,
            0.30,
            0.30
        ],
        "total_num_slices": 288,
        "dimension": {
            "x": 800,
            "y": 800
        },
        "generation_type": "bone"
    },
    "config_dict": {
        "process_start_index": 2
    },
    "scan_root": "/Users/strdrv/Work/Project/CBCTvsMCT/Data/CTVerificationDatabase/Alphen/CA_CBCT",
    "stl_folder": "stl_alphen_cbct"
}
```
```
scan_root = load_dict['scan_root']
stl_folder = os.path.join(scan_root, load_dict['stl_folder'])
```

## yaml文件

```
#data
data:
  test_path: './data/tran_val_test/test.txt'
  train_path: './data/tran_val_test/train.txt'
  val_path: './data/tran_val_test/val.txt'

# model parameters
model:
  loadpretrainmodel: False
  model_load_path: './checkpoints/Unet_480.pth'
  model_name: UNet0
  model_save_path: './checkpoints/01_5class_z_normalization_lr_3e-5_new_configure_style.pth'

# test parameters
test_param:
  test_batchsize: 1

# training parameters
train_param:
  batch_size: 12
  lr: 5e-05
  max_epoch: 100
  num_workers: 4
  print_freq: 10
  use_gpu: True
  device: 'cuda:0'
```

读取方法
```
import yaml
import numpy as np
f = open("config.yaml")
cfg = yaml.load(f)

#print(cfg['model']['model_name'])
#print(cfg['scan_info']['left_bounding_box'])

left_bounding_box = cfg['scan_info']['left_bounding_box']
with open('config420.yaml', 'r') as yaml_file:
    cfg = yaml.load(yaml_file)

left_bounding_box = cfg['scan_info']['left_bounding_box']
right_bounding_box = cfg['scan_info']['right_bounding_box']
```

## Yaml 搭配yacs实现动态配置文件
https://blog.csdn.net/happyday_d/article/details/103338888  
https://github.com/rbgirshick/yacs  
