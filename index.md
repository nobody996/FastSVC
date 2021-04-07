# <center> FastSVC: Fast Cross-Domain Singing Voice Conversion with Feature-wise Linear Modulation</center>

<center> Songxiang Liu *, Yuewen Cao *, Na Hu, Dan Su, Helen Meng </center>  

<center> Human-Computer Communications Laboratory, The Chinese University of Hong Kong </center>

<center> Tencent AI Lab </center>

*Work done during internship at Tencent AI Lab.

## Abstract
This paper presents FastSVC, a light-weight cross-domain sing voice conversion (SVC) system, which is able to achieve high conversion performance, with inference speed 4x faster than real time on CPUs. FastSVC uses Conformer based phoneme recognizer to extract singer-agnostic linguistic features from singing signals. A feature-wise linear modulation based generator is used to synthesize waveform directly from linguistic features, leveraging information from sine-excitation signals and loudness features. The waveform generator can be trained conveniently using a multi-resolution spectral loss and an adversarial loss. Experimental results show that the proposed FastSVC system, compared with a computationally heavy baseline system, can achieve comparable conversion performance in some scenarios and significantly better conversion performance in other scenarios. Moreover, the proposed FastSVC system achieves desirable cross-lingual singing conversion performance. Inference speed of the FastSVC system is 3x and 70x faster than the baseline system on GPUs and CPUs, respectively.

## Brief introduction
- Singing voice conversion (SVC): convert the voice of one singer to that of other singers without changing the underlying content and melody.
- Cross-domain training: models are trained with speech dataset while conversion is conducted in the singing domain.
- Faster than real time: able to conduct inference with a real-time factor (RTF) < 1.0 on modern CPUs.
- Any-to-many conversion: convert an arbitrary voice into a target singer’s voice within the finite singer set during training process.
- Cross-lingual conversion: convert singing voice in a language which is unseen during the training process.

## Compared systems
- UCD-SVC: unsupervised cross-domain singing voice conversion system, Adam Polyak et al.
- FastSVC (Ours)

## Any-to-One Cross-domain (A2O-CD) singing voice conversion
### Target speech reference samples from LJ-Speech.

| LJ002-0271 | LJ010-0295 | LJ028-0335 | LJ031-0224 | 
| :--- | :--- | :--- | :--- |
| <audio src="wavs/A2O-CD/LJ-refs/LJ002-0271.wav" controls preload></audio> | <audio src="wavs/A2O-CD/LJ-refs/LJ010-0295.wav" controls preload></audio> | <audio src="wavs/A2O-CD/LJ-refs/LJ028-0335.wav" controls preload></audio> | <audio src="wavs/A2O-CD/LJ-refs/LJ031-0224.wav" controls preload></audio> |
| --- | --- | --- | --- |

| Source | UCD-SVC | FastSVC (Ours) |
| :--- | :--- | :--- |
| <audio src="wavs/NUS-refs/ADIZ_18.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/ADIZ.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/ADIZ.wav" controls preload></audio> | 
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JLEE_11.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/JLEE.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/JLEE.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JTAN_07.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/JTAN.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/JTAN.wav" controls preload></audio> | 
| --- | --- | --- |
| <audio src="wavs/NUS-refs/KENN_10.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/KENN.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/KENN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MCUR_17.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/MCUR.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/MCUR.wav" controls preload></audio> | 
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPOL_20.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/MPOL.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/MPOL.wav" controls preload></audio> | 
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPUR_02.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/MPUR.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/MPUR.wav" controls preload></audio> | 
| --- | --- | --- |
| <audio src="wavs/NUS-refs/NJAT_16.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/NJAT.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/NJAT.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/PAMR_15.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/PAMR.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/PMAR.wav" controls preload></audio> | 
| --- | --- | --- |
| <audio src="wavs/NUS-refs/SAMF_13.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/SAMF.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/SAMF.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/VKOW_11.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/VKOW.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/VKOW.wav" controls preload></audio> | 
| --- | --- | --- |
| <audio src="wavs/NUS-refs/ZHIY_03.wav" controls preload></audio> | <audio src="wavs/A2O-CD/UCD-SVC/ZHIY.wav" controls preload></audio> | <audio src="wavs/A2O-CD/FastSVC/ZHIY.wav" controls preload></audio> | 
| --- | --- | --- |

## Any-to-Many Cross-domain (A2M-CD) singing voice conversion

| Source | References (VCTK) | UCD-SVC | FastSVC (Ours) |     
| :--- | :--- | :--- | :--- |      
| <audio src="wavs/A2M-CD/source/ADIZ_18_to_p258.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p258_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/ADIZ_to_p258_18.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/ADIZ_18_to_p258.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/JLEE_15_to_p304.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p304_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/JLEE_to_p304_15.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/JLEE_15_to_p304.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/JTAN_16_to_p282.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p282_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/JTAN_to_p282_16.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/JTAN_16_to_p282.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/KENN_04_to_p248.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p248_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/KENN_to_p248_04.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/KENN_04_to_p248.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/MCUR_17_to_p233.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p233_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/MCUR_to_p233_17.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/MCUR_17_to_p233.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/MPOL_11_to_p256.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p256_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/MPOL_to_p256_11.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/MPOL_11_to_p256.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/MPUR_03_to_p248.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p248_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/MPUR_to_p248_03.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/MPUR_03_to_p248.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/NJAT_07_to_p243.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p243_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/NJAT_to_p243_07.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/NJAT_07_to_p243.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/PMAR_11_to_p311.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p311_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/PMAR_to_p311_11.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/PMAR_11_to_p311.wav" controls preload></audio> |
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/SAMF_18_to_p335.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p335_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/SAMF_to_p335_18.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/SAMF_18_to_p335.wav" controls preload></audio> | 
| --- | --- | --- | --- |  
| <audio src="wavs/A2M-CD/source/VKOW_19_to_p259.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p259_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/VKOW_to_p259_19.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/VKOW_19_to_p259.wav" controls preload></audio> | 
| --- | --- | --- | --- | 
| <audio src="wavs/A2M-CD/source/ZHIY_06_to_p307.wav" controls preload></audio> | <audio src="wavs/A2M-CD/vctk_refs/p307_ref.wav" controls preload></audio> | <audio src="wavs/A2M-CD/UCD-SVC/ZHIY_to_p307_06.wav" controls preload></audio> | <audio src="wavs/A2M-CD/FastSVC/ZHIY_06_to_p307.wav" controls preload></audio> | 
| --- | --- | --- | --- | 


## Any-to-Many In-domain (A2M-ID) singing voice conversion
### Female source singer 

| Source sample from ADIZ (NUS-48E) | <audio src="wavs/A2M-ID/ADIZ_18.wav" controls preload></audio> |

| Referneces (NUS-48E) | UCD-SVC | FastSVC (Ours) |
| :--- | :--- | :--- |
| <audio src="wavs/NUS-refs/ADIZ_18.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/ADIZ.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/ADIZ.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JLEE_11.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/JLEE.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/JLEE.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JTAN_07.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/JTAN.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/JTAN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/KENN_10.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/KENN.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/KENN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MCUR_17.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/MCUR.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/MCUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPOL_20.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/MPOL.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/MPOL.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPUR_02.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/MPUR.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/MPUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/NJAT_16.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/NJAT.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/NJAT.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/PAMR_15.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/PMAR.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/PMAR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/SAMF_13.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/SAMF.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/SAMF.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/VKOW_11.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/VKOW.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/VKOW.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/ZHIY_03.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/ADIZ-18/ZHIY.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/ADIZ-18/ZHIY.wav" controls preload></audio> |
| --- | --- | --- |

### Male source singer 

| Source sample from VKOW (NUS-48E) | <audio src="wavs/A2M-ID/VKOW_20.wav" controls preload></audio> |

| Referneces (NUS-48E) | UCD-SVC | FastSVC (Ours) |
| :--- | :--- | :--- |
| <audio src="wavs/NUS-refs/ADIZ_18.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/ADIZ.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/ADIZ.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JLEE_11.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/JLEE.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/JLEE.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JTAN_07.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/JTAN.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/JTAN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/KENN_10.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/KENN.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/KENN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MCUR_17.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/MCUR.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/MCUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPOL_20.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/MPOL.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/MPOL.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPUR_02.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/MPUR.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/MPUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/NJAT_16.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/NJAT.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/NJAT.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/PAMR_15.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/PMAR.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/PMAR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/SAMF_13.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/SAMF.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/SAMF.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/VKOW_11.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/VKOW.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/VKOW.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/ZHIY_03.wav" controls preload></audio> | <audio src="wavs/A2M-ID/UCD-SVC/VKOW-20/ZHIY.wav" controls preload></audio> | <audio src="wavs/A2M-ID/FastSVC/VKOW-20/ZHIY.wav" controls preload></audio> |
| --- | --- | --- |

## Cross-lingual (CL) singing voice conversion
### Female source singer 

| Chinese Source sample | <audio src="wavs/cross-lingual/JL95.wav" controls preload></audio> |

| Referneces (NUS-48E) | UCD-SVC | FastSVC (Ours) |
| :--- | :--- | :--- |
| <audio src="wavs/NUS-refs/ADIZ_18.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/ADIZ.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/ADIZ.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JLEE_11.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/JLEE.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/JLEE.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JTAN_07.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/JTAN.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/JTAN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/KENN_10.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/KENN.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/KENN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MCUR_17.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/MCUR.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/MCUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPOL_20.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/MPOL.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/MPOL.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPUR_02.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/MPUR.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/MPUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/NJAT_16.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/NJAT.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/NJAT.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/PAMR_15.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/PMAR.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/PMAR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/SAMF_13.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/SAMF.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/SAMF.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/VKOW_11.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/VKOW.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/VKOW.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/ZHIY_03.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/95/ZHIY.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/95/ZHIY.wav" controls preload></audio> |
| --- | --- | --- |

### Male source singer 

| Chinese Source sample | <audio src="wavs/cross-lingual/JL94.wav" controls preload></audio> |

| Referneces (NUS-48E) | UCD-SVC | FastSVC (Ours) |
| :--- | :--- | :--- |
| <audio src="wavs/NUS-refs/ADIZ_18.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/ADIZ.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/ADIZ.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JLEE_11.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/JLEE.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/JLEE.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/JTAN_07.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/JTAN.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/JTAN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/KENN_10.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/KENN.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/KENN.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MCUR_17.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/MCUR.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/MCUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPOL_20.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/MPOL.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/MPOL.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/MPUR_02.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/MPUR.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/MPUR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/NJAT_16.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/NJAT.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/NJAT.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/PAMR_15.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/PMAR.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/PMAR.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/SAMF_13.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/SAMF.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/SAMF.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/VKOW_11.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/VKOW.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/VKOW.wav" controls preload></audio> |
| --- | --- | --- |
| <audio src="wavs/NUS-refs/ZHIY_03.wav" controls preload></audio> | <audio src="wavs/cross-lingual/UCD-SVC/94/ZHIY.wav" controls preload></audio> | <audio src="wavs/cross-lingual/FastSVC/94/ZHIY.wav" controls preload></audio> |
| --- | --- | --- |


