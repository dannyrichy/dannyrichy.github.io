---
layout: default
title: Deep Learning for Music
category: "Prjkt"
---
## Music Infomatics

Date: 27/11/2024

Intention of this page is to summarize the project I carried out for the course [Music Informatics](https://www.kth.se/student/kurser/kurs/DT2470?l=en){:target="_blank"}. The detailed report can be found [here](https://github.com/Adhithyan8/musical-shrooms/blob/master/Group-13-project-report.pdf){:target="_blank"}.

#### Prelude

Using deep learning models to directly process a music track is challenging due to the large number of data points it contains. For instance, consider this [file](https://sound-effects.bbcrewind.co.uk/search?q=NHU05104233){:target="_blank"}. The file has a [sampling rate](https://manual.audacityteam.org/man/sample_rates.html){:target="_blank"}  of 44100 Hz, meaning there are 44,100 data points per second. With a total duration of 51 seconds, one channel contains 2,249,100 data points. (You can use this [python library](https://pypi.org/project/pydub/){:target="_blank"} to experiment with audio files.) By comparison, an image in the ImageNet dataset typically has dimensions of 224x224, amounting to 150,528 data points (considering 3 channels).

#### Spectrogram

Powering down your brain to the absolute minimum, if someone were asked what comes to mind when they hear time series data, I’m pretty sure they would say [Fourier transform](https://en.wikipedia.org/wiki/Fourier_analysis){:target="_blank"}. Performing a [Discrete Fourier Transform (DFT)](https://en.wikipedia.org/wiki/Discrete_Fourier_transform){:target="_blank"} outputs data in the Frequency-Magnitude domain (still 2D). Performing DFT on an entire file, however, would require significant computational power. Therefore, one typically uses the [Short-Time Fourier Transform (STFT)](https://en.wikipedia.org/wiki/Short-time_Fourier_transform){:target="_blank"}, which computes DFT for every pre-defined window size (usually after applying a window function, such as the Hann window). This results in 3D data, where, in addition to frequency and magnitude, there is also a time axis that indicates the start time of each window. The resulting data is called spectrogram and looks like this (taken from wikipedia)

![spectrogram](https://upload.wikimedia.org/wikipedia/commons/thumb/c/c5/Spectrogram-19thC.png/400px-Spectrogram-19thC.png)

The above can be viewed as an image, thus providing a means to loosely view an audio file as an image. Now we can bring out the big-gun *Deep Learning* models like Res-Net (?) or some CNN to perform whatever task we want.

#### Get to the point Danny

Out in the wild there are bunch of music taggers like  [Fully Convolutional Network](https://arxiv.org/abs/1606.00298){:target="_blank"}, [Musicnn](https://arxiv.org/abs/1711.02520){:target="_blank"}, [Convolutional Recurrent Neural Network](https://arxiv.org/abs/1609.04243){:target="_blank"}, [Self-attention based Network](https://arxiv.org/abs/1906.04972){:target="_blank"}, [Harmonic CNN](https://ieeexplore.ieee.org/document/9053669){:target="_blank"}, [Sample-level CNN](https://arxiv.org/abs/1703.01789){:target="_blank"} and [Sample-level CNN with Squeeze and Excitation layers](https://arxiv.org/abs/1710.10451){:target="_blank"}. But what's **tagging**, welp it can be anything from genre to mood. We consider the models trained on [MTG-Jamendo Dataset](https://mtg.github.io/mtg-jamendo-dataset/){:target="_blank"}, which has the following tagging class:

| Genre             | Instrument       | Mood/Theme   |
|-------------------|------------------|--------------|
| rock              | voice            | film         |
| pop               | synthesizer      | relaxing     |
| classical         | piano            | emotional    |
| popfolk           | guitar           | energetic    |
| funk              | strings          | happy        |
| ambient           | keyboard         |              |
| chillout          | violin           |              |
| downtempo         | bass             |              |
| easylistening     | computer         |              |
| electronic        | drummachine      |              |
| lounge            | drums            |              |
| triphop           | electricguitar   |              |
| techno            | acousticguitar   |              |
| newage            | electricpiano    |              |
| jazz              |                  |              |
| metal             |                  |              |
| alternative       |                  |              |
| experimental      |                  |              |
| soundtrack        |                  |              |
| world             |                  |              |
| trance            |                  |              |
| orchestral        |                  |              |
| hiphop            |                  |              |
| instrumentalpop   |                  |              |
| reggae            |                  |              |
| dance             |                  |              |
| folk              |                  |              |
| poprock           |                  |              |
| indie             |                  |              |
| house             |                  |              |
| atmospheric       |                  |              |

Our aim is to see how well these taggers generalize. We take the help of [GTZAN dataset](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification){:target="_blank"} and check if they form natural clusters  without the knowledge of the true clusters:***Blues, Classical, Country, Disco, Hiphop, Jazz, Metal, Pop, Reggae and Rock***. Our aim is to now learn **WHAT ON EARTH DO THEY LEARN?**. In Academic parlance, this layer gives the representation of the input. *Representation learning* as they call it, is the viewpoint that all the deep learning architecture learns is ways to project highly complex data into some $$ \mathbb{R}^d $$ space. 


#### Really really exciting part I

I will skip some essential yet perhaps boring details about data processing that you can find [here](https://github.com/Adhithyan8/musical-shrooms/blob/master/Group-13-project-report.pdf){:target="_blank"} in the methodology section. Lo and behold, the clusters formed quite nicely (Actually, maybe nicely) when projected using [tSNE](https://en.wikipedia.org/wiki/T-distributed_stochastic_neighbor_embedding){:target="_blank"}

![fig](/assets/music_thingy/tsne_attention.png) ![fig](/assets/music_thingy/tsne_crnn.png) ![fig](/assets/music_thingy/tsne_fcn.png) ![fig](/assets/music_thingy/tsne_hcnn.png) ![fig](/assets/music_thingy/tsne_musicnn.png) ![fig](/assets/music_thingy/tsne_sample.png) ![fig](/assets/music_thingy/tsne_se.png)

Is it just me, or do you also see a pigeon in the representation? Here's a picture of [pigeon](https://www.warrenphotographic.co.uk/photgraphy/bigs/06614-white-pigeon-in-flight.jpg){:target="_blank"} for comparison. Maybe deep learning models have revealed that all music is a path to peace... XD. Well, time to come back to reality: ***Ground Control to Major Tom...***

Interestingly, it roughly organizes these genres in a manner similar to this [map](https://musicmap.info/){:target="_blank"}. We used [Hungarian algorithm](https://en.wikipedia.org/wiki/Hungarian_algorithm){:target="_blank"} to compare our clusters with true cluster. Imo, it is too boring to discuss about them here, you can find it again in the [report](https://github.com/Adhithyan8/musical-shrooms/blob/master/Group-13-project-report.pdf){:target="_blank"}

#### Really really exciting part II

All that is fine, but what happens if we throw non-Western songs at it? Will it dodge them like Muhammad Ali?
![MuhammadAli](https://i.giphy.com/media/v1.Y2lkPTc5MGI3NjExa216YWRsb2NxcHlmNmJka3M3ejlzb2diaWx0OWRtajZwcGg2anhqayZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/N9oq9rijUWT3q/giphy.gif)

Turns out, it still organizes them into clusters. To test this, we used [Carnatic songs](https://en.wikipedia.org/wiki/Carnatic_music){:target="_blank"}, [Gaana songs](https://en.wikipedia.org/wiki/Gaana){:target="_blank"} and [Carnatic-Rock](https://youtu.be/oESni03J8h8){:target="_blank"}. We hoped that Gaana songs would be placed near rap and/or reggae, as we felt both genres share roots in being music of the masses. Similarly, we expected Carnatic music to be close to the classical genre due to its strong emphasis on structure. And, as the name suggests, we anticipated that Carnatic Rock would fall somewhere between classical and rock music. 

![fig](/assets/music_thingy/ood_attention.png) ![fig](/assets/music_thingy/ood_crnn.png) ![fig](/assets/music_thingy/ood_fcn.png) ![fig](/assets/music_thingy/ood_hcnn.png) ![fig](/assets/music_thingy/ood_musicnn.png) ![fig](/assets/music_thingy/ood_sample.png) ![fig](/assets/music_thingy/ood_se.png)

Carnatic formed its own cluster, separate from the pigeon, but as expected, Gaana was placed close to reggae and hip-hop. Likewise, Carnatic Rock was positioned in a space spanning both the Rock and Carnatic clusters.

#### Things we liked to explore

We wanted to explore how the one-and-only [Isaignani(Maestro) Illayaraja's](https://en.wikipedia.org/wiki/Ilaiyaraaja) songs end up in this space. But perhaps his work is best left unanalyzed—sometimes magic is better left untouched (_or we didn't have enough time_ 😜). Here's a [playlist](https://youtu.be/8Hjf-UyTSKg?list=RDQMuDs1OjuZmoM) to knock you off your feet.

#### PEACE OUT, CIAO, BYE

---
### References
- [Automatic tagging using deep convolutional neural networks](https://arxiv.org/abs/1606.00298){:target="_blank"}
- [End-to-end learning for music audio tagging at scale](https://arxiv.org/abs/1711.02520){:target="_blank"}
- [Convolutional Recurrent Neural Networks for Music Classification](https://arxiv.org/abs/1609.04243){:target="_blank"}
- [Toward Interpretable Music Tagging with Self-Attention](https://arxiv.org/abs/1906.04972){:target="_blank"}
- [Data-Driven Harmonic Filters for Audio Representation Learning](https://ieeexplore.ieee.org/document/9053669){:target="_blank"}
- [Sample-level Deep Convolutional Neural Networks for Music Auto-tagging Using Raw Waveforms](https://arxiv.org/abs/1703.01789){:target="_blank"}
- [Sample-level CNN Architectures for Music Auto-tagging Using Raw Waveforms](https://arxiv.org/abs/1710.10451){:target="_blank"}
