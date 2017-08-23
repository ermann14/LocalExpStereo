# Continuous 3D Label Stereo Matching using Local Expansion Moves

This is an implementatioin of a stereo matching method described in

```
@article{Taniai16,
  author    = {Tatsunori Taniai and
               Yasuyuki Matsushita and
               Yoichi Sato and
               Takeshi Naemura},
  title     = {{Continuous 3D Label Stereo Matching using Local Expansion Moves}},
  journal   = {CoRR (arXiv)},
  volume    = {abs/1603.08328},
  year      = {2016},
  url       = {http://arxiv.org/abs/1603.08328},
}
```

If you use our code, please cite the above paper and cite the following conference paper.

```
@inproceedings{Taniai14,
  author    = {Tatsunori Taniai and
               Yasuyuki Matsushita and
               Takeshi Naemura},
  title     = {{Continuous Stereo Matching using Locally Shared Labels}},
  booktitle = {{IEEE Conference on Computer Vision and Pattern Recognition (CVPR)}},
  year      = {2014},
  pages     = {1613--1620},
}
```

## Running environment
- Visual Studio 2017 Community
- OpenCV 3.02 (will be automatically installed via NuGet)
- Maxflow code v3.01 by Boykov and Kolmogorov (http://vision.csd.uwo.ca/code/)

## How to Run?
1. Download and extract maxflow source code to "maxflow" directory. 
2. Download and extract an example dataset (see Adirondack below) in "data/MiddV3/Adirondack".
3. Build the solution with release mode.
4. Run demo.bat file. Results will be saved in "results/cones", "results/teddy", and "results/Adirondack".

## Options
- -doDual <0,1>: Estimate left and right image disparities and do post-processing using consistency check.
- -iterations <int>: Number of main iterations.
- -pmIterations <int>: Number of initial iterations performed without smoothness terms (this accelerates inference).
- -smooth_weight <float>: Smoothness weight (lambda in the paper).
- -filterRedious <int>: The redius of matching windows (filterRedious/2 is used as the kernel radius of guided image filter).

## Pre-computed MC-CNN matching costs
We use matching cost volumes computed by MC-CNN-acrt (https://github.com/jzbontar/mc-cnn).
We provide pre-computed matching cost data for 30 test and training image pairs of Middlebury benchmark V3.
For demonstration, please use Adirondack below that contains image pairs, calibration data, and ground truth.
- trainingH: http://www.hci.iis.u-tokyo.ac.jp/datasets/data/LocalExpStereo/trainingH.rar 
- testH: http://www.hci.iis.u-tokyo.ac.jp/datasets/data/LocalExpStereo/testH.rar
- Adirondack: http://www.hci.iis.u-tokyo.ac.jp/datasets/data/LocalExpStereo/Adirondack.zip
