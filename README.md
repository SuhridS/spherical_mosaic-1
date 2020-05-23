# Spherical Mosaic - Computational Photography Final Project
---
Libraries we used in this project:
- **OpenCV** (3.4.2) for feature detection/matching
- **Eigen3** for ceres compatibility
- **Ceres** for large-scale non-linear optimization
- **Boost** for file management system, sorting and random algorithms


## OPENCV VERSION 3.4.2 (w. SIFT/SURF Support)
---
Download the opencv git repo and switch to the version 3.4.2 (for SIFT/SURF feature detection support)

```bash
git clone https://github.com/opencv/opencv.git
cd opencv
git checkout tags/3.4.2 -b opencv3.4.2
```

Download the opencv_contrib git repo and switch to the version 3.4.2
```bash
git clone https://github.com/opencv/opencv_contrib.git
cd opencv_contrib
git checkout tags/3.4.2 -b opencv_contrib3.4.2
```

Cmake build and install opencv 3.4.2 project and ensure that EXTRA MODULE and ENABLE NONFREE is set

```bash
cd opencv
mkdir build
cd build

cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr/local -DOPENCV_EXTRA_MODULES_PATH=<path_to_directory>/opencv_contrib/modules -DOPENCV_ENABLE_NONFREE=True -DBUILD_opencv_rgbd=OFF ..

sudo make install -j8
```

To test the version of your OPENCV, you want to find the OpenCVConfig.cmake. To find out this, use:
```bash
sudo updatedb
locate OpenCVConfig.cmake
```
The command will give you the path for OpenCVConfig.cmake (normally under the folder /usr/local/share/OpenCV/), open the file and find the line "SET(OpenCV_VERSION *.*.*)". Make sure the number match with 3.4.2.