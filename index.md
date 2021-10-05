## Abstract

Previously proposed FullSubNet has achieved outstanding performance in Deep Noise Suppression (DNS) Challenge and thus received great interests. Unfortunately, it still has shortcomings such as input-output mismatch and coarse processing for frequency band.
In this paper, we propose an extended real-time single-channel speech enhancement framework called FullSubNet+ with following significant improvements. First, to make full use of the phase information in noisy speech, our model takes all the magnitude, real and imaginary spectrograms as inputs. Then, we design a multi-scale time sensitive channel attention (MulCA) module which adopts multi-scale convolution kernel and channel attention mechanism to have different emphases on different frequency bands. Moreover, by replacing the long short-time momery (LSTM) layers in original full-band model with stacked temporal convolutional network (TCN) blocks, we design a more efficient full-band module called full-band extractor. 
The experimental results in DNS Challenge dataset show the superior performance of our FullSubNet, which reach the state-of-the-art performance and outperform other existing speech enhancement approaches.





## Without Reverberation



## With Reverberation

|                          **case 1**                          |
| :----------------------------------------------------------: |
|                          **Noisy**                           |
| **<img src="./data/with_reverb/example1/noisy.png" alt="flowtron_0.0" style="zoom: 100%;" />** |
| <audio controls><source src="./data/with_reverb/example1/noisy.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
|                        **FullSubNet**                        |
| **<img src="./data/with_reverb/example1/fullsubnet.png" alt="flowtron_0.0" style="zoom: 100%;" />** |
| <audio controls><source src="./data/with_reverb/example1/fullsubnet.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
|                       **FullSubNet+**                        |
| **<img src="./data/with_reverb/example1/fullsubnet+.png" alt="flowtron_0.0" style="zoom: 100%;" />** |
| <audio controls><source src="./data/with_reverb/example1/fullsubnet+.wav" type="audio/wav">Your browser does not support the audio element.</audio> |
|                          **Clean**                           |
| **<img src="./data/with_reverb/example1/clean.png" alt="flowtron_0.0" style="zoom: 100%;" />** |
| <audio controls><source src="./data/with_reverb/example1/clean.wav" type="audio/wav">Your browser does not support the audio element.</audio> |









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

