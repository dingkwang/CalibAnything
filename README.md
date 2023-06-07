## Introduction

This is a project for LiDAR to camera calibration.

## Environment
```shell
docker pull xiaokyan/opencalib:v1
```


## Compile
```shell
# mkdir build
mkdir -p build && cd build
# build
cmake .. && make
```
## Usage
```
./run_lidar2camera <data_folder>
```
The data folder should contain:
- img_file
- `masks`: masks generated by Segment Anything
- lidar_file
- initial extrinsic

## Test Example
We provide examples of two dataset:
```
./run_lidar2camera ./data/st/1
./run_lidar2camera ./data/kitti/1
```
We have given a reference value of the extrinsic. You can set an initial error to the reference extrinsic in file `data/initial_error.txt` and test the accuracy of the algorithm. The format is "roll pitch yaw(degree) x y z(m)"

## result
- initial projection: `init_proj.png`, `init_proj_seg.png`
- refined projection: `refined_proj.png`, `refined_proj_seg.png`
- refined extrinsic: `extrinsic.txt`
