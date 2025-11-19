## Dataset structure
The dataset on which I started the training has the following structure
```
2025_ipAdap_image
|
|__person
|____person1.jpg
|____person2.jpg
|____ ....
|____personN.jpg
|__next_person
|____next_person1.jpg
|____next_person2.jpg
|____ ....
|____next_personM.jpg
|__ ....
```
## Launching models
Because the code uses the [Accelerate](https://huggingface.co/docs/accelerate/index) library, do not forget to configure the configuration of your environment.
```bash
accelerate config
```

### IP-Adapter. Baseline
The following code will allow you to start image generation using a standard IP Adapter. The launch is performed by the command
```bash
bash script.sh
```
or
```bash
python script.py --data_dir "/data/kazachkovda/2025_ipAdap_image/" --output_dir "../../figures" --json "../../data_preprocess/metadata.jsonl" --num_images 4
```
Before doing so, you need to install all project dependencies and configure paths to the data folder. A description of the dataset structure can be found in this file above.

### IP-Adapter with Self-Attention
The following code will start generating images using a modified IP-Adapter. The change is that, along with a photo of a person, many photos of them from different angles are submitted. These angles are processed using self-attention. You can read more details in the [paper](https://github.com/wolkendolf/2025-project-DiffModels/blob/main/docs/2025genavatars_main.pdf) itself.

The `images_number` flag indicates the number of camera angles. You can set it as the minimum number of camera angles among the available photos of people.
```bash
bash train_script.sh
```
