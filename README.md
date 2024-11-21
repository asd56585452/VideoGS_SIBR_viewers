# Streaming Volumetric Video Viewer for V3: Viewing Volumetric Videos on Mobiles via Streamable 2D Dynamic Gaussians

Official implementation of the streaming volumetric video viewer for _V^3: Viewing Volumetric Videos on Mobiles via Streamable 2D Dynamic Gaussians_.

Please note that the SIBR viewer is only tested on Ubuntu, maybe not work for other platforms due to the video codec. 

## Installation

```
# Dependencies
sudo apt install -y libglew-dev libassimp-dev libboost-all-dev libgtk-3-dev libopencv-dev libglfw3-dev libavdevice-dev libavcodec-dev libeigen3-dev libxxf86vm-dev libembree-dev libcurl4-openssl-dev ffmpeg ninja-build
# Project setup
cd VideoGS_SIBR_viewers
cmake -Bbuild . -DCMAKE_BUILD_TYPE=Release # add -G Ninja to build faster
cmake --build build -j24 --target install
```

## Usage

Please setup a nginx server in the internal network to serve as a streaming server. 

Then modify the network address in `src/projects/gaussianviewer/renderer/GaussianView.hpp`, rebuild it and run it. 

## Acknowledgement

This viewer is based on the original [gaussian-splatting viewer](https://github.com/graphdeco-inria/gaussian-splatting). 

If you found our work useful, please kindly cite our paper:

```
@misc{wang2024v3viewingvolumetricvideos,
      title={V^3: Viewing Volumetric Videos on Mobiles via Streamable 2D Dynamic Gaussians}, 
      author={Penghao Wang and Zhirui Zhang and Liao Wang and Kaixin Yao and Siyuan Xie and Jingyi Yu and Minye Wu and Lan Xu},
      year={2024},
      eprint={2409.13648},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2409.13648}, 
}
```