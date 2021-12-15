# TRACER: Extreme Attention Guided Salient Object Tracing Network implementation in PyTorch

This paper was accepted at AAAI 2022 SA poster session.  

## Datasets
All datasets are available in public.
* Download the DUTS-TR and DUTS-TE from [Here](http://saliencydetection.net/duts/#org3aad434)
* Download the DUT-OMRON from [Here](http://saliencydetection.net/dut-omron/#org96c3bab)
* Download the HKU-IS from [Here](https://sites.google.com/site/ligb86/hkuis)
* Download the ECSSD from [Here](https://www.cse.cuhk.edu.hk/leojia/projects/hsaliency/dataset.html)
* Download the PASCAL-S from [Here](http://cbs.ic.gatech.edu/salobj/)
* Download the edge GT from [Here]().

## Data structure
<pre><code>
TRACER
├── data
│   ├── DUTS
│   │   ├── Train
│   │   │   ├── images
│   │   │   ├── masks
│   │   │   ├── edges
│   │   ├── Test
│   │   │   ├── images
│   │   │   ├── masks
│   ├── DUT-O
│   │   ├── Test
│   │   │   ├── images
│   │   │   ├── masks
│   ├── HKU-IS
│   │   ├── Test
│   │   │   ├── images
│   │   │   ├── masks
      .
      .
      .
</code></pre>

## Requirements
* Python 3.7.x
* Pytorch >= 1.8.0
* albumentations >= 0.5.1
* matplotlib >= 3.3.3
* tqdm >=4.54.0
* scikit-learn > 0.23.2

## Run
* Run **main.py** scripts.
<pre><code>
# For training TRACER-TE0 (e.g.)
python main.py train --arch b0 --img_size 320

# For testing TRACER with pre-trained model (e.g.)  
python main.py test --exp_num 0 --arch b0 --img_size 320
</code></pre>

## Configurations
--img_size: Input image resolution.  
--arch: EfficientNet backbone scale: TE0 to TE7.  
--frequency_radius: High-pass filter radius in the MEAM.  
--gamma: channel confidence ratio \gamma in the UAM.   
--denoise: Denoising ratio d in the OAM.  
--RFB_aggregated_channel: # of channels in receptive field blocks.  
--multi_gpu: Multi-GPU learning options.  





