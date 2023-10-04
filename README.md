# Adversarial Fine-tuning using Generated Respiratory Sound to Address Class Imbalance

## Generated Samples

### Label 'Normal'

#### (Test Real) 147_2b4_Pl_mc_AKGC417L_event_2_label_0.wav
<audio 
  controls
  source="Diffwave/samples/test_set_samples/147_2b4_Pl_mc_AKGC417L_event_2_label_0.wav"
  type="audio/wav"
  </audio>
  <img width="300" src="https://github.com/ChihyeonYoon/Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/assets/46586785/c211aadd-c381-49d5-a349-7bc8e28f274b">


#### (ICBHI Audio Diffusion) 147_2b4_Pl_mc_AKGC417L_event_2_label_0.wav
<audio controls="controls">  
  <source type="audio/wav" src="Diffwave/samples/generated_test_samples/147_2b4_Pl_mc_AKGC417L_event_2_label_0.wav"></source>
  <img width="300" src="https://github.com/ChihyeonYoon/Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/assets/46586785/dc303cba-13f2-459f-b5e0-0c2453bbf1c8">
</audio>

#### (LJSpeech Audio Diffusion) 147_2b4_Pl_mc_AKGC417L_event_2_label_0.wav
<audio controls="controls">  
  <source type="audio/wav" src="Diffwave/samples/generated_test_samples_from_speech_pretrained/147_2b4_Pl_mc_AKGC417L_event_2_label_0.wav"></source>
  <img width="300" src="https://github.com/ChihyeonYoon/Adversarial-Adaptation-Synthetic-Respiratory-Sound-Data/assets/46586785/747a5f96-943e-4995-bf57-706bd68e3831">
</audio>

### Label 'Crackle'

### Label 'Wheeze'

### Label 'Both'



## Notion
To train or evalutate the audio diffusion model, please see ```Diffwave/``` folder.

To train or evalutate the respiratory sound classification task, please see ```Classification/``` folder.

## Environmental set-up

### Environments
`Ubuntu xx.xx`  
`Python 3.8.xx`

# Install the proper version of PyTorch
```
pip3 install torch torchvision torchaudio
```
and
```
pip install -r requirements.txt
```

## Datasets

Download the ICBHI files and unzip it.
All details is described in the [paper w/ code](https://paperswithcode.com/dataset/icbhi-respiratory-sound-database)

```
wget https://bhichallenge.med.auth.gr/sites/default/files/ICBHI_final_database/ICBHI_final_database.zip
or 
wget --no-check-certificate  https://bhichallenge.med.auth.gr/sites/default/files/ICBHI_final_database/ICBHI_final_database.zip
```
To directly use our pre-processed ICBHI dataset for reproducibility, see in ```Diffwave/``` and ```Classification/``` folder

## ICBHI Data

The database consists of a total of 5.5 hours of recordings containing 6898 respiratory cycles, of which 1864 contain crackles, 886 contain wheezes, and 506 contain both crackles and wheezes, in 920 annotated audio samples from 126 subjects.

The downloaded data looks like [[kaggle](https://www.kaggle.com/datasets/vbookshelf/respiratory-sound-database), [paper w/ code](https://paperswithcode.com/dataset/icbhi-respiratory-sound-database)]:

<pre>
data/icbhi_dataset
├── metadata.txt
│    ├── Patient number
│    ├── Age
│    ├── Sex
│    ├── Adult BMI (kg/m2)
│    ├── Adult Weight (kg)
│    └── Child Height (cm)
│
├── official_split.txt
│    ├── Patient number_Recording index_Chest location_Acqiosotopm mode_Recording equipment
│    |    ├── Chest location
│    |    |    ├── Trachea (Tc),Anterior left (Al),Anterior right (Ar),Posterior left (Pl)
│    |    |    └── Posterior right (Pr),Lateral left (Ll),Lateral right (Lr)
│    |    |
│    |    ├── Acquisition mode
│    |    |    └── sequential/single channel (sc), simultaneous/multichannel (mc)
│    |    |
│    |    └── Recording equipment 
│    |         ├── AKG C417L Microphone (AKGC417L), 
│    |         ├── 3M Littmann Classic II SE Stethoscope (LittC2SE), 
│    |         ├── 3M Litmmann 3200 Electronic Stethoscope (Litt3200), 
│    |         └── WelchAllyn Meditron Master Elite Electronic Stethoscope (Meditron)
│    |    
│    └── Train/Test   
│
├── patient_diagnosis.txt
│    ├── Patient number
│    └── Diagnosis
│         ├── COPD: Chronic Obstructive Pulmonary Disease
│         ├── LRTI: Lower Respiratory Tract Infection
│         └── URTI: Upper Respiratory Tract Infection
│
└── patient_list_foldwise.txt
</pre>
