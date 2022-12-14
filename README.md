<div align="center">

# Multimodal Semantic Mismatch Detection in Social Media Posts

<h4>
  <a href='https://jason-khan.github.io/' target='_blank'>Kehan Wang</a>
  ·
  <a href='https://sethzhao506.github.io/' target='_blank'>Seth Z. Zhao</a>
  ·
  <a href='https://dchan.cc/' target='_blank'>David Chan</a>
  ·
  <a href='https://www2.eecs.berkeley.edu/Faculty/Homepages/zakhor.html' target='_blank'>Avideh Zakhor</a>
  ·
  <a href='https://www2.eecs.berkeley.edu/Faculty/Homepages/canny.html' target='_blank'>John Canny</a>
</h4>

<h4>
IEEE 24th International Workshop on Multimedia Signal Processing (MMSP) 2022
</h4>

<!-- [![arXiv](http://img.shields.io/badge/arXiv-2203.04229-B31B1B.svg)](https://arxiv.org/abs/2203.04229) -->
<!-- [![Conference](https://img.shields.io/badge/CVPR-2022-4b44ce.svg)](https://openaccess.thecvf.com/content/CVPR2022/html/Wang_Neural_Face_Identification_in_a_2D_Wireframe_Projection_of_a_CVPR_2022_paper.html) -->

<img src="assets/teaser.png"  width="500">

</div>

## Download Dataset

We release two dataset, Twitter-1M and Twitter-60k-with-audio, with precomputed features from [S3D](https://github.com/antoine77340/S3D_HowTo100M) on video and [DeBERTa-v3](https://huggingface.co/microsoft/deberta-v3-large) on text. Twitter-60k-with-audio also contains [DeBERTa-v3](https://huggingface.co/microsoft/deberta-v3-large) features on the transcript of tweet audios, transcribed using [Wav2vec 2.0](https://huggingface.co/facebook/wav2vec2-base-960h). 
- [Twitter-1M](https://drive.google.com/drive/folders/1PSxoMhdJCtW9T0vDxLCeVYMv_mL5cFT-?usp=sharing) contains all features in a zip, and their corresponding tweet-ids. Tweet ids and features are in the same order. Features can be loaded through `np.load`.
- [Twitter-60k-with-audio](https://drive.google.com/drive/folders/1XeFCB-nvHOrnfscY1PouzFr6DjKOLhoB?usp=sharing) contains all features and ids in a `dict` saved in `.npy` files. To load the dict, use
```python
import numpy as np
dictionary = np.load(f'60k_{mode}_features.npy', allow_pickle=True).flatten()[0]
dictionary.keys() # dict_keys(['text_feats', 'caption_feats', 'video_feats', 'ids'])
```
## Acknowledgement

We would like to graciously acknowledge Google for partially providing cloud computing resouces for this project, and Twitter for Academic Research API.

## Citation

Please cite `Semantic Mismatch Detector` in your publications if it helps your research:

```bibtex
@inproceedings{SMD,
  title     = {Multimodal Semantic Mismatch Detection in Social Media Posts},
  author    = {Kehan Wang and Seth Z. Zhao and David Chan and Avideh Zakhor and John Canny},
  booktitle = {Proceedings of IEEE 24th International Workshop on Multimedia Signal Processing (MMSP)},
  year      = {2022}
}
```

## License

[MIT license](LICENSE)