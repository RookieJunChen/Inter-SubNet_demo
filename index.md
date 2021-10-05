## Abstract

Previously proposed FullSubNet has achieved outstanding performance in Deep Noise Suppression (DNS) Challenge and thus received great interests. Unfortunately, it still has shortcomings such as input-output mismatch and coarse processing for frequency band.
In this paper, we propose an extended real-time single-channel speech enhancement framework called FullSubNet+ with following significant improvements. First, to make full use of the phase information in noisy speech, our model takes all the magnitude, real and imaginary spectrograms as inputs. Then, we design a multi-scale time sensitive channel attention (MulCA) module which adopts multi-scale convolution kernel and channel attention mechanism to have different emphases on different frequency bands. Moreover, by replacing the long short-time momery (LSTM) layers in original full-band model with stacked temporal convolutional network (TCN) blocks, we design a more efficient full-band module called full-band extractor. 
The experimental results in DNS Challenge dataset show the superior performance of our FullSubNet, which reach the state-of-the-art performance and outperform other existing speech enhancement approaches.



## Without Reverberation

| **Model** | **Condition**           |                          **Audio**                           |                     **Mel-spectrogram**                      |
| :-------: | ----------------------- | :----------------------------------------------------------: | :----------------------------------------------------------: |
| Flowtron  | *sigma = 0.0*           | <audio controls><source src="./data/experiment1/Audio/flowtron_0.0.wav" type="audio/wav">Your browser does not support the audio element.</audio> | <img src="./data/experiment1/Mel-spectrogram/Flowtron_0.0.png" alt="flowtron_0.0" style="zoom: 40%;" /> |
| Flowtron  | *sigma = 0.5*           | <audio controls><source src="./data/experiment1/Audio/flowtron_0.5.wav" type="audio/wav">Your browser does not support the audio element.</audio> | <img src="./data/experiment1/Mel-spectrogram/Flowtron_0.5.png" alt="flowtron_0.5" style="zoom: 40%;" /> |
| Flowtron  | *sigma = 1.0*           | <audio controls><source src="./data/experiment1/Audio/flowtron.wav" type="audio/wav">Your browser does not support the audio element.</audio> | <img src="./data/experiment1/Mel-spectrogram/flowtron.png" alt="flowtron_1.0" style="zoom: 52%;" /> |
| Tacotron2 | *p in {0.45,0.5,0.55 }* | <audio controls><source src="./data/experiment1/Audio/tacotron2.wav" type="audio/wav">Your browser does not support the audio element.</audio> | <img src="./data/experiment1/Mel-spectrogram/Tacotron2.png" alt="flowtron_0.5" style="zoom: 40%;" /> |



### **F0 Contours对比图**

|                       **F0 Contours**                        |
| :----------------------------------------------------------: |
| **<img src="./data/experiment1/F0-Contours/Flowtron_0.0.png" alt="flowtron_0.0" style="zoom: 120%;" />** |
|                   *Flowtron   sigma = 0.0*                   |
| **<img src="./data/experiment1/F0-Contours/Flowtron_0.5.png" alt="flowtron_0.0" style="zoom: 120%;" />** |
|                   *Flowtron   sigma = 0.5*                   |
| **<img src="./data/experiment1/F0-Contours/Flowtron_1.0.png" alt="flowtron_0.0" style="zoom: 120%;" />** |
|                   *Flowtron  sigma = 1.0*                    |
| **<img src="./data/experiment1/F0-Contours/Tacotron2.png" alt="flowtron_0.0" style="zoom: 120%;" />** |
|              *Tacotron2  p in {0.45,0.5,0.55 }*              |









## **样本间插值实验**

| **Case**  |                         **Gaussian**                         |                     **Mel-spectrogram**                      |                          **Audio**                           |
| :-------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
| sample 1  | **<img src="./data/experiment2/Gaussian/0.png" alt="flowtron_0.0" style="zoom: 40%;" />** | **<img src="./data/experiment2/Mel-spectrogram/0.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <audio controls><source src="./data/experiment2/Audio/0.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| step = 25 | **<img src="./data/experiment2/Gaussian/25.png" alt="flowtron_0.0" style="zoom: 40%;" />** | **<img src="./data/experiment2/Mel-spectrogram/25.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <audio controls><source src="./data/experiment2/Audio/25.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| step = 75 | **<img src="./data/experiment2/Gaussian/75.png" alt="flowtron_0.0" style="zoom: 40%;" />** | **<img src="./data/experiment2/Mel-spectrogram/75.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <audio controls><source src="./data/experiment2/Audio/75.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| sample 2  | **<img src="./data/experiment2/Gaussian/100.png" alt="flowtron_0.0" style="zoom: 40%;" />** | **<img src="./data/experiment2/Mel-spectrogram/100.png" alt="flowtron_0.0" style="zoom: 40%;" />** | <audio controls><source src="./data/experiment2/Audio/100.wav" type="audio/wav">Your browser does not support the audio element.</audio> |







## **说话人之间风格转换实验**

|        **Case**        |                          **Image**                           |                          **Audio**                           |
| :--------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: |
|        参考音频        | **<img src="./data/experiment3/Image/0.png" alt="flowtron_0.0" style="zoom: 50%;" />** | <audio controls><source src="./data/experiment3/Audio/reference.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| Flowtron随机采样的语音 | **<img src="./data/experiment3/Image/1.png" alt="flowtron_0.0" style="zoom: 50%;" />** | <audio controls><source src="./data/experiment3/Audio/normal.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
| Flowtron风格转换的语音 | **<img src="./data/experiment3/Image/2.png" alt="flowtron_0.0" style="zoom: 50%;" />** | <audio controls><source src="./data/experiment3/Audio/GST_Tacotron.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
|   GSTs风格转换的语音   | **<img src="./data/experiment3/Image/4.png" alt="flowtron_0.0" style="zoom: 25%;" />** | <audio controls><source src="./data/experiment3/Audio/transfer.wav" type="audio/wav">Your browser does not support the audio element.</audio> |

