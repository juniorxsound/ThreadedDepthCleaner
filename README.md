# Threaded Depth Cleaner

Threaded depth-map cleaning and inpainting using OpenCV. 
1. [Quickstart](#quickstart)
1. [Depth Cleaning](#depth-cleaning)
1. [Video](https://vimeo.com/276897884)
1. [Dependencies](#dependencies)
1. [License](#license)

![Depth-map image](https://github.com/juniorxsound/ThreadedDepthCleaner/blob/master/docs/depth_cleaning_top_bottom.jpg)
*Left-to-right: Original depth-map visualized using a color-map, filtered depth-map visualized using a color-map*  
### Quickstart
The tool is setup to use the Intel's [librealsense](https://github.com/IntelRealSense/librealsense) SDK and a RealSense depth sensor (415/435). 
1. Clone the repository with it's submodules:
```
git clone https://github.com/juniorxsound/ThreadedDepthCleaner --recursive
```
2. Install OpenCV ([Windows](https://docs.opencv.org/3.4/d3/d52/tutorial_windows_install.html#tutorial_windows_install_prebuilt), [macOS](https://www.pyimagesearch.com/2016/12/19/install-opencv-3-on-macos-with-homebrew-the-easy-way/), [Linux](https://www.learnopencv.com/install-opencv3-on-ubuntu/))
3. Install CMake ([Instructions](https://cmake.org/download/))
4. ```cd``` into the repository folder and run:
```
mkdir build && cd build && cmake ../ && make -j4
```
5. Run it by running ```./DepthCleaner```

> Tested on macOS (10.13.2) using CMake (3.10.0)

### Depth Cleaning
1. Use the ```SCALE_FACTOR``` macro to determine how much to scale the depth-map for the inpainting (1 means no scaling and less performent, 0.2 means 1/5 of the original depth-map is used for inpainting and more performent).

### Dependencies
1. [librealsense](https://github.com/IntelRealSense/librealsense)
1. [OpenCV](https://opencv.org)

> Depth coloring and cv::Mat queuing functionality was implemented thanks to [@PKLab](http://pklab.net/index.php?id=394&lang=EN) and [@Catree](https://stackoverflow.com/questions/42356562/realsense-opencv-depth-image-too-dark) 🙌🏻

> Thanks to [@Dodiku](https://github.com/dodiku) for help with the cover image 💪🏻

### License
All code in this repository is released under the MIT license [found here](https://github.com/juniorxsound/ThreadedDepthCleaner/blob/master/LICENSE)
