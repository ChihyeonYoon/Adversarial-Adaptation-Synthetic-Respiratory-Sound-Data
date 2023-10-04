# Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data

## Generate Sound Data


### ICBHI lung Sound Data Download
We offer the ICBHI lung sound data we used in this project.

https://drive.google.com/file/d/1hycczKL1k_nCps0ARUFhqxYSqDE30ocm/view?usp=sharing

unzip the file and put it in the directory.  
Sound Data should be located in
```
Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/Diffwave/dataset/
```
it might be like this.
```
Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/Diffwave/dataset/wav_4secs_16000/...
```

### Preprocess
process sound data to mel-spectrogram.  
(not necessary. the spectrogram files already exists in the dataset we provide.)
```
python preprocess.py dir [YOUR_SOUND_DATA_DIR] 
```

### Run Diffwave trainning
```
cd Diffwave
sh ./scripts/icbhi_diffwave_conditional_bs16_sr16k_4s_cls_all_2gpu.sh
```

### Model
We offer 1M step model we made  

https://drive.google.com/file/d/1LU3pKDHc85bSkQ_BZH5ZTxsCGsOHyXnS/view?usp=sharing  

Model should be located in
```
Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/Diffwave/save/[CHECKPOINT]/
```
for inference
### Inference
```
python inference.py [YOUR_MODEL_PATH] --spectrogram_path [Spectrograms_PATH]
# [YOUR_MODEL_PATH] directory should contain train_args.json
# [Spectrograms_PATH] directory should contain the preprocessed spectorgrams you want to synthesize 

여기에 선배 쓰시는 inference.py 사용할 수 있는 명령어 적어주세요
(지금 있는 inference.py는 folder by folder 생성하는 것임.)
dataset mixing 도 추가하시면 될거 같습니다.
```

### Generated Samples
/sample 이하에 있는 파일들로 들을 수 있게 구성하시면됩니다.

### References
- [DiffWave: A Versatile Diffusion Model for Audio Synthesis](https://arxiv.org/pdf/2009.09761.pdf)
