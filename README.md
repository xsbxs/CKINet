# Adaptive Consistency Learning for Fine-Grained Multimodal Panoptic Perception of Remote Sensing Images

This is the code and results repository of “Adaptive Consistency Learning for Fine-Grained Multimodal Panoptic Perception of Remote Sensing Images”. [\[paper\]](https://www.sciencedirect.com/science/article/pii/S0924271626005162)

## Datasets

### FineGrip

The FineGrip dataset is available from the [official dataset page](https://ybio.github.io/FineGrip/).

### DLRSD-UCM

We construct a paired multimodal remote sensing dataset from the public [DLRSD](https://sites.google.com/view/zhouwx/dataset) (Shao et al., 2018) and [UCM-Captions](https://github.com/201528014227051/RSICD_optimal#other-remote-sensing-image-captioning-dataset) (Qu et al., 2016) datasets. DLRSD provides pixel-level semantic segmentation annotations for 17 classes, while UCM-Captions provides five textual descriptions per image. We match and correct the corresponding data, and screen out problematic or unsuitable samples, yielding **1,785 image-mask-caption triplets**.

Please contact us if you need access to this paired dataset.

## Results

### FineGrip

Results on the original FineGrip benchmark. Random image flipping is used as the default geometric data augmentation.

<table class="comparison-table original-table" align="center">
<thead>
<tr><th rowspan="3" width="12%" align="center">Method</th><th rowspan="3" width="18%" align="center">Backbone</th><th colspan="6" align="center">Panoptic segmentation</th><th colspan="6" align="center">Language generation</th></tr>
<tr><th colspan="3" align="center">All</th><th colspan="3" align="center">Things</th><th colspan="3" align="center">Beam size = 3</th><th colspan="3" align="center">Beam size = 5</th></tr>
<tr><th align="center">PQ</th><th align="center">SQ</th><th align="center">RQ</th><th align="center">PQ<sup>Th</sup></th><th align="center">SQ<sup>Th</sup></th><th align="center">RQ<sup>Th</sup></th><th align="center" title="BLEU-4">BU</th><th align="center" title="METEOR">MR</th><th align="center" title="ROUGE-L">RE</th><th align="center" title="BLEU-4">BU</th><th align="center" title="METEOR">MR</th><th align="center" title="ROUGE-L">RE</th></tr>
</thead>
<tbody>
<tr><td align="center">MaskFormer</td><td align="center">R-50</td><td align="center">50.52</td><td align="center">76.96</td><td align="center">65.30</td><td align="center">49.22</td><td align="center">75.89</td><td align="center">64.75</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">Mask2Former</td><td align="center">R-50</td><td align="center">55.11</td><td align="center">80.80</td><td align="center">67.90</td><td align="center">54.68</td><td align="center">80.36</td><td align="center">67.89</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">LDA-AQU</td><td align="center">R-50</td><td align="center">47.21</td><td align="center">78.88</td><td align="center">59.46</td><td align="center">47.93</td><td align="center">79.28</td><td align="center">60.54</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">YOSO</td><td align="center">R-50</td><td align="center">53.13</td><td align="center">79.65</td><td align="center">66.41</td><td align="center">52.80</td><td align="center">79.18</td><td align="center">66.57</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">MaskDINO</td><td align="center">R-50</td><td align="center">54.11</td><td align="center">81.72</td><td align="center">66.11</td><td align="center">54.04</td><td align="center">81.18</td><td align="center">66.47</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">OneFormer</td><td align="center">R-50</td><td align="center">54.63</td><td align="center">80.89</td><td align="center">67.18</td><td align="center">54.13</td><td align="center">80.75</td><td align="center">66.86</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">UISE</td><td align="center">R-50</td><td align="center">54.10</td><td align="center">80.42</td><td align="center">67.05</td><td align="center">53.16</td><td align="center">79.83</td><td align="center">66.50</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">SAT</td><td align="center">R-50</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">38.30</td><td align="center">27.45</td><td align="center">54.59</td><td align="center">37.41</td><td align="center">26.99</td><td align="center">53.30</td></tr>
<tr><td align="center">MLAT</td><td align="center">R-50</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">41.40</td><td align="center">27.05</td><td align="center">56.04</td><td align="center">40.69</td><td align="center">26.49</td><td align="center">55.46</td></tr>
<tr><td align="center">SCAMET</td><td align="center">EfficientNetB3</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">38.44</td><td align="center">26.52</td><td align="center">53.70</td><td align="center">38.31</td><td align="center">26.15</td><td align="center">53.50</td></tr>
<tr><td align="center">PP</td><td align="center">R-50</td><td align="center">55.09</td><td align="center">81.12</td><td align="center">67.74</td><td align="center">54.67</td><td align="center">80.64</td><td align="center">67.76</td><td align="center">41.60</td><td align="center">29.21</td><td align="center">56.03</td><td align="center">40.70</td><td align="center">28.68</td><td align="center">54.59</td></tr>
<tr><td align="center"><strong>CKINet (ours)</strong></td><td align="center">R-50</td><td align="center">56.11</td><td align="center">80.92</td><td align="center">69.15</td><td align="center">56.26</td><td align="center">80.48</td><td align="center">69.83</td><td align="center">43.93</td><td align="center">29.62</td><td align="center">57.01</td><td align="center">43.99</td><td align="center">29.30</td><td align="center">56.38</td></tr>
<tr class="backbone-break"><td align="center">MaskFormer</td><td align="center">Swin-L</td><td align="center">60.03</td><td align="center">79.62</td><td align="center">75.24</td><td align="center">59.96</td><td align="center">78.76</td><td align="center">76.06</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">Mask2Former</td><td align="center">Swin-L</td><td align="center">63.12</td><td align="center">82.47</td><td align="center">76.38</td><td align="center">62.93</td><td align="center">81.68</td><td align="center">76.88</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">MaskDINO</td><td align="center">Swin-L</td><td align="center">61.79</td><td align="center">82.99</td><td align="center">74.32</td><td align="center">62.32</td><td align="center">82.43</td><td align="center">75.47</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">OneFormer</td><td align="center">Swin-L</td><td align="center">62.31</td><td align="center">81.98</td><td align="center">75.79</td><td align="center">61.83</td><td align="center">81.33</td><td align="center">75.89</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">MGTransformer</td><td align="center">R-152&nbsp;+&nbsp;ViT-B/32</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">40.05</td><td align="center">26.98</td><td align="center">55.40</td><td align="center">40.31</td><td align="center">26.78</td><td align="center">55.45</td></tr>
<tr><td align="center">SFDR</td><td align="center">R-50&nbsp;+&nbsp;R-152&nbsp;+&nbsp;ViT-B/32</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">38.63</td><td align="center">27.71</td><td align="center">53.07</td><td align="center">38.67</td><td align="center">27.78</td><td align="center">52.95</td></tr>
<tr><td align="center">PP</td><td align="center">Swin-L</td><td align="center">62.67</td><td align="center">82.33</td><td align="center">75.90</td><td align="center">62.11</td><td align="center">81.55</td><td align="center">75.97</td><td align="center">42.47</td><td align="center">29.50</td><td align="center">55.85</td><td align="center">41.68</td><td align="center">28.93</td><td align="center">54.57</td></tr>
<tr><td align="center"><strong>CKINet (ours)</strong></td><td align="center">Swin-L</td><td align="center">63.54</td><td align="center">82.18</td><td align="center">77.15</td><td align="center">63.44</td><td align="center">81.38</td><td align="center">77.81</td><td align="center">42.87</td><td align="center">30.15</td><td align="center">56.14</td><td align="center">42.44</td><td align="center">29.66</td><td align="center">55.33</td></tr>
</tbody>
</table>

### FineGrip v1.1 upgrade

FineGrip v1.1 includes data refinements and corrections to the validation set for segmentation. The table below reports segmentation results on the latest version of the dataset. Random image flipping is used as the default geometric data augmentation.

<table class="comparison-table upgrade-table" align="center">
<thead>
<tr><th rowspan="3" width="12%" align="center">Method</th><th rowspan="3" width="18%" align="center">Backbone</th><th colspan="6" align="center">Panoptic segmentation</th><th colspan="6" align="center">Language generation</th></tr>
<tr><th colspan="3" align="center">All</th><th colspan="3" align="center">Things</th><th colspan="3" align="center">Beam size = 3</th><th colspan="3" align="center">Beam size = 5</th></tr>
<tr><th align="center">PQ</th><th align="center">SQ</th><th align="center">RQ</th><th align="center">PQ<sup>Th</sup></th><th align="center">SQ<sup>Th</sup></th><th align="center">RQ<sup>Th</sup></th><th align="center" title="BLEU-4">BU</th><th align="center" title="METEOR">MR</th><th align="center" title="ROUGE-L">RE</th><th align="center" title="BLEU-4">BU</th><th align="center" title="METEOR">MR</th><th align="center" title="ROUGE-L">RE</th></tr>
</thead>
<tbody>
<tr><td align="center">MaskFormer</td><td align="center">R-50</td><td align="center">55.26</td><td align="center">77.41</td><td align="center">71.27</td><td align="center">54.76</td><td align="center">76.08</td><td align="center">72.01</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">Mask2Former</td><td align="center">R-50</td><td align="center">61.00</td><td align="center">81.28</td><td align="center">74.98</td><td align="center">61.62</td><td align="center">80.55</td><td align="center">76.51</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">LDA-AQU</td><td align="center">R-50</td><td align="center">51.98</td><td align="center">79.12</td><td align="center">65.44</td><td align="center">53.48</td><td align="center">79.38</td><td align="center">67.59</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">YOSO</td><td align="center">R-50</td><td align="center">58.83</td><td align="center">80.13</td><td align="center">73.32</td><td align="center">59.56</td><td align="center">79.34</td><td align="center">75.07</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">MaskDINO</td><td align="center">R-50</td><td align="center">61.11</td><td align="center">81.88</td><td align="center">74.65</td><td align="center">62.24</td><td align="center">81.16</td><td align="center">76.71</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">OneFormer</td><td align="center">R-50</td><td align="center">60.38</td><td align="center">81.41</td><td align="center">74.05</td><td align="center">60.95</td><td align="center">80.95</td><td align="center">75.30</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">UISE</td><td align="center">R-50</td><td align="center">60.00</td><td align="center">80.87</td><td align="center">74.17</td><td align="center">60.14</td><td align="center">79.94</td><td align="center">75.25</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">SAT</td><td align="center">R-50</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">38.30</td><td align="center">27.45</td><td align="center">54.59</td><td align="center">37.41</td><td align="center">26.99</td><td align="center">53.30</td></tr>
<tr><td align="center">MLAT</td><td align="center">R-50</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">41.40</td><td align="center">27.05</td><td align="center">56.04</td><td align="center">40.69</td><td align="center">26.49</td><td align="center">55.46</td></tr>
<tr><td align="center">SCAMET</td><td align="center">EfficientNetB3</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">38.44</td><td align="center">26.52</td><td align="center">53.70</td><td align="center">38.31</td><td align="center">26.15</td><td align="center">53.50</td></tr>
<tr><td align="center">PP</td><td align="center">R-50</td><td align="center">61.03</td><td align="center">81.56</td><td align="center">74.84</td><td align="center">61.70</td><td align="center">80.77</td><td align="center">76.47</td><td align="center">41.60</td><td align="center">29.21</td><td align="center">56.03</td><td align="center">40.70</td><td align="center">28.68</td><td align="center">54.59</td></tr>
<tr><td align="center"><strong>CKINet (ours)</strong></td><td align="center">R-50</td><td align="center">62.24</td><td align="center">81.31</td><td align="center">76.54</td><td align="center">63.50</td><td align="center">80.59</td><td align="center">78.81</td><td align="center">43.93</td><td align="center">29.62</td><td align="center">57.01</td><td align="center">43.99</td><td align="center">29.30</td><td align="center">56.38</td></tr>
<tr class="backbone-break"><td align="center">MaskFormer</td><td align="center">Swin-L</td><td align="center">66.57</td><td align="center">80.10</td><td align="center">83.20</td><td align="center">67.70</td><td align="center">78.95</td><td align="center">85.80</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">Mask2Former</td><td align="center">Swin-L</td><td align="center">70.37</td><td align="center">82.95</td><td align="center">84.91</td><td align="center">71.55</td><td align="center">81.83</td><td align="center">87.39</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">MaskDINO</td><td align="center">Swin-L</td><td align="center">68.68</td><td align="center">83.45</td><td align="center">82.40</td><td align="center">70.51</td><td align="center">82.54</td><td align="center">85.41</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">OneFormer</td><td align="center">Swin-L</td><td align="center">69.08</td><td align="center">82.43</td><td align="center">83.81</td><td align="center">69.86</td><td align="center">81.45</td><td align="center">85.76</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">MGTransformer</td><td align="center">R-152&nbsp;+&nbsp;ViT-B/32</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">40.05</td><td align="center">26.98</td><td align="center">55.40</td><td align="center">40.31</td><td align="center">26.78</td><td align="center">55.45</td></tr>
<tr><td align="center">SFDR</td><td align="center">R-50&nbsp;+&nbsp;R-152&nbsp;+&nbsp;ViT-B/32</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">-</td><td align="center">38.63</td><td align="center">27.71</td><td align="center">53.07</td><td align="center">38.67</td><td align="center">27.78</td><td align="center">52.95</td></tr>
<tr><td align="center">PP</td><td align="center">Swin-L</td><td align="center">69.64</td><td align="center">82.78</td><td align="center">84.16</td><td align="center">70.37</td><td align="center">81.65</td><td align="center">86.13</td><td align="center">42.47</td><td align="center">29.50</td><td align="center">55.85</td><td align="center">41.68</td><td align="center">28.93</td><td align="center">54.57</td></tr>
<tr><td align="center"><strong>CKINet (ours)</strong></td><td align="center">Swin-L</td><td align="center">70.71</td><td align="center">82.63</td><td align="center">85.64</td><td align="center">71.97</td><td align="center">81.49</td><td align="center">88.29</td><td align="center">42.87</td><td align="center">30.15</td><td align="center">56.14</td><td align="center">42.44</td><td align="center">29.66</td><td align="center">55.33</td></tr>
</tbody>
</table>

### DLRSD-UCM

Results under the ResNet-50 setting. The structured task is **semantic segmentation**, evaluated by mean intersection over union (mIoU) and overall pixel accuracy (aAcc).

<table class="dlrsd-table" align="center">
<thead>
<tr><th rowspan="2" width="25%" align="center">Method</th><th colspan="2" align="center">Structure</th><th colspan="3" align="center">Language</th></tr>
<tr><th align="center">mIoU</th><th align="center">aAcc</th><th align="center" title="BLEU-4">BU</th><th align="center" title="METEOR">MR</th><th align="center" title="ROUGE-L">RE</th></tr>
</thead>
<tbody>
<tr><td align="center">MaskFormer</td><td align="center">74.57</td><td align="center">84.44</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">Mask2Former</td><td align="center">76.54</td><td align="center">84.93</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">OneFormer</td><td align="center">76.50</td><td align="center">85.34</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">UISE</td><td align="center">74.08</td><td align="center">84.69</td><td align="center">-</td><td align="center">-</td><td align="center">-</td></tr>
<tr><td align="center">SAT</td><td align="center">-</td><td align="center">-</td><td align="center">73.15</td><td align="center">50.88</td><td align="center">83.78</td></tr>
<tr><td align="center">MLAT</td><td align="center">-</td><td align="center">-</td><td align="center">76.98</td><td align="center">50.90</td><td align="center">84.72</td></tr>
<tr><td align="center">PP</td><td align="center">77.24</td><td align="center">85.21</td><td align="center">75.83</td><td align="center">51.22</td><td align="center">85.62</td></tr>
<tr><td align="center"><strong>CKINet (ours)</strong></td><td align="center">77.00</td><td align="center">86.12</td><td align="center">76.69</td><td align="center">52.13</td><td align="center">86.52</td></tr>
</tbody>
</table>

## Citations

Please cite our paper in your publications if you find this repository useful.

```bibtex
@article{xu2027adaptive,
  title   = {Adaptive consistency learning for fine-grained multimodal panoptic perception of remote sensing images},
  author  = {Xu, Shuobo and Zhao, Danpei and Yuan, Bo and Liu, Hangjian
             and Li, Wentao and Li, Tian and Shi, Zhenwei},
  journal = {ISPRS Journal of Photogrammetry and Remote Sensing},
  volume  = {243},
  pages   = {749--763},
  year    = {2027},
  doi     = {10.1016/j.isprsjprs.2026.10.018},
  url     = {https://doi.org/10.1016/j.isprsjprs.2026.10.018}
}
```
