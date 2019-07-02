---
layout: default
---
This page is the demo of 
1. "Quasi-Periodic WaveNet vocoder: a pitch dependent dilated convolution model for parametric speech generation" [paper](https://arxiv.org/abs/1907.00797) [code]  
2. "Statistical voice conversion with Quasi-Periodic WaveNet vocoder" [paper]  

## **Abstract**
We propose a quasi-periodic neural network (QPNet) vocoder with a novel network architecture named pitch-dependent dilated convolution (PDCNN) to improve the pitch controllability of WaveNet (WN) vocoder. The effectiveness of the WN vocoder to generate high-fidelity speech samples from given acoustic features has been proved recently. However, because of the fixed dilated convolution and generic network architecture, the WN vocoder hardly generates speech with given F0 values which are outside the range observed in training data. Consequently, the WN vocoder lacks the pitch controllability which is one of the essential capabilities of conventional vocoders. To address this limitation, we propose the PDCNN component which has the time-variant adaptive dilation size related to the given F0 values and a cascade network structure of the QPNet vocoder to generate quasi-periodic signals such as speech. BThe experimental results demonstrate the better pitch controllability of the QPNet vocoder compared to the same and double sized WN vocoders while keeping comparable speech qualities.  
## **Architecture of QPNet vocoder**  
<center><img src="res/figure/QPNet_vocoder.jpg" ></center>  
  
## **Pitch-dependent dilated convolution**  
<center><img src="res/figure/PDCNN.jpg" ></center>  
  
---
## **Pitch transformation**
- Conditioning on **unchanged** *F*<sub>0</sub>

| Vocoder           | Female (SF3)                                                           | Male (SM3)                                                             |
|:------------------|:----------------------------------------------------------------------:|:----------------------------------------------------------------------:|
| **Natural**       | <audio src="res/audio/SF3/1_0_F0/Natural/30009.wav" controls preload></audio> | <audio src="res/audio/SM3/1_0_F0/Natural/30002.wav" controls preload></audio> |
| WORLD             | <audio src="res/audio/SF3/1_0_F0/WORLD/30009.wav" controls preload></audio>   | <audio src="res/audio/SM3/1_0_F0/WORLD/30002.wav" controls preload></audio>   |
| WNf<sup> *1</sup> | <audio src="res/audio/SF3/1_0_F0/WNf/30009.wav" controls preload></audio>     | <audio src="res/audio/SM3/1_0_F0/WNf/30002.wav" controls preload></audio>     |
| WNc<sup> *2</sup> | <audio src="res/audio/SF3/1_0_F0/WNc/30009.wav" controls preload></audio>     | <audio src="res/audio/SM3/1_0_F0/WNc/30002.wav" controls preload></audio>     |
| QPNet             | <audio src="res/audio/SF3/1_0_F0/QPNet/30009.wav" controls preload></audio>   | <audio src="res/audio/SM3/1_0_F0/QPNet/30002.wav" controls preload></audio>   |

<sup>*1. `WNf: WaveNet vocoder with full size (30 layers).` </sup>   
<sup>*2. `WNc: WaveNet vocoder with compact size (16 layers).` </sup>
- Conditioning on **1/2** *F*<sub>0</sub>

| Vocoder           | Female (SF3)                                                                   | Male (SM3)                                                                     |
|:------------------|:------------------------------------------------------------------------------:|:------------------------------------------------------------------------------:|
| WORLD             | <audio src="res/audio/SF3/0_5_F0/WORLD/30009.wav" controls preload></audio>   | <audio src="res/audio/SM3/0_5_F0/WORLD/30002.wav" controls preload></audio>   |
| WNf               | <audio src="res/audio/SF3/0_5_F0/WNf/30009.wav" controls preload></audio>     | <audio src="res/audio/SM3/0_5_F0/WNf/30002.wav" controls preload></audio>     |
| WNc               | <audio src="res/audio/SF3/0_5_F0/WNc/30009.wav" controls preload></audio>     | <audio src="res/audio/SM3/0_5_F0/WNc/30002.wav" controls preload></audio>     |
| QPNet             | <audio src="res/audio/SF3/0_5_F0/QPNet/30009.wav" controls preload></audio>   | <audio src="res/audio/SM3/0_5_F0/QPNet/30002.wav" controls preload></audio>   |
  
<br />  
- Conditioning on **3/2** *F*<sub>0</sub>

| Vocoder           | Female (SF3)                                                                   | Male (SM3)                                                                     |
|:------------------|:------------------------------------------------------------------------------:|:------------------------------------------------------------------------------:|
| WORLD             | <audio src="res/audio/SF3/1_5_F0/WORLD/30009.wav" controls preload></audio>   | <audio src="res/audio/SM3/1_5_F0/WORLD/30002.wav" controls preload></audio>   |
| WNf               | <audio src="res/audio/SF3/1_5_F0/WNf/30009.wav" controls preload></audio>     | <audio src="res/audio/SM3/1_5_F0/WNf/30002.wav" controls preload></audio>     |
| WNc               | <audio src="res/audio/SF3/1_5_F0/WNc/30009.wav" controls preload></audio>     | <audio src="res/audio/SM3/1_5_F0/WNc/30002.wav" controls preload></audio>     |
| QPNet             | <audio src="res/audio/SF3/1_5_F0/QPNet/30009.wav" controls preload></audio>   | <audio src="res/audio/SM3/1_5_F0/QPNet/30002.wav" controls preload></audio>   |
  
--- 
## **Speaker voice conversion**
*coming soon*
<br />  
<br />  