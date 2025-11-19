# Data processing

Launch order:
1. check_watermarks.py (additionally, we will delete the verified files)
2. check_number_faces.py
3. (optional) check_count_imgs.py (You can set a minimum number of images in a folder. All folders below this threshold will be deleted.)
4. generate_metadata_gpuVersion.py

## Check watermarks

### Desription
The solution is based on the [watermark-detection](https://github.com/boomb0om/watermark-detection) project, from which dependencies must be installed.

The code is capable of processing broken images.

### Run
After cloning the repository [watermark-detection](https://github.com/boomb0om/watermark-detection), it is necessary to register in `data/check_watermarks.py ` the path to the model:

```python
sys.path.append(
    "/home/jovyan/nkiselev/kazachkovda/2025-project-DiffModels/watermark-detection"
)
```

Also, do not forget to specify the path to the dataset and the device.
```python
BASE_DATASET_PATH = (
    "/path/to/dataset"
)
device = 'cuda:0'
```

Launching the handler
```bash
cd data
python check_watermarks.py
```


## Face validation

### Description
Checking photos for only one face in the image. It is based on the `YOLOv11n-face-detection` model.

### Run
Don't forget to specify the path to the dataset:
```python
BASE_DATASET_PATH = "/path/to/dataset"
```

After installing the necessary dependencies:
```bash
cd data 
python check_number_faces.py
```


## Desriptive generation

### Description
It is based on the `Qwen2.5-VL-7B-Instruct` model.

### Run
After installing the necessary dependencies:

```bash
cd data 
python generate_metadata_gpuVersion
```

