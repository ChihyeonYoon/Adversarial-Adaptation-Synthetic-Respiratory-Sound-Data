# Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data

## Generate Sound Data


### Sound Data Download
Add here

### Sound Data should be located in
```
Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/Diffwave/dataset/[train or test]/
```
### Preprocess
```
python preprocess.py dir [YOUR_SOUND_DATA_DIR] 
```

### Run Diffwave trainning
- edit --datadirs argument in  
  scripts/icbhi_diffwave_conditional_bs16_sr16k_4s_cls_all_2gpu.sh  
  to your sound data dir

```
cd Diffwave
sh ./scripts/icbhi_diffwave_conditional_bs16_sr16k_4s_cls_all_2gpu.sh
```

### Inference
```
python inference.py --spectrograms_path [YOUR_AUDIO_SPECTROGRAMS_DIR] --model_dir [YOUR_MODEL] --save_path [PATH_TO_SAVE_GENERATED_WAV_FILES] --fast --mode condition
```

### Model
https://drive.google.com/file/d/1LU3pKDHc85bSkQ_BZH5ZTxsCGsOHyXnS/view?usp=sharing

## Classification
Add here


### References
- [DiffWave: A Versatile Diffusion Model for Audio Synthesis](https://arxiv.org/pdf/2009.09761.pdf)