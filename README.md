# Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data

Sound Data should be located in
```
  Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/Diffwave/dataset/[train or test]/
```

Run trainnig
```
  cd Diffwave
  sh ./scripts/icbhi_diffwave_conditional_bs16_sr16k_4s_cls_all_2gpu.sh
```

Inference
```
  python inference.py --spectrograms_path [YOUR_AUDIO_SPECTROGRAMS_DIR] --model_dir [YOUR_MODEL] --save_path [PATH_TO_SAVE_GENERATED wav FILE] --fast --mode condition
```
