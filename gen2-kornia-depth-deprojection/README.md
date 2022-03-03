## On Device Depth deprojection Demo
This example shows how to perform depth reprojection on device.

[![Point Cloud Generation on OAK-D using Kornia](https://user-images.githubusercontent.com/32992551/156474386-6026e364-8a64-462c-99b3-b3dfb9283a28.png)](https://www.youtube.com/watch?v=xnrsqMJM3Pk "Point Cloud Generation on OAK-D using Kornia")

Note that the included model will only work for a 640x480 camera (and also used my camera' intrinsics),
so you should probably update this file. I want to find a way to get this info to the network via some kind of host-device interaction.

Your camera will throw a warning saying the image size doesnt match the neural network, but you can ignore it as it is 
just going based off of the ImgFrame metadata (which I should update at some point using a script node).

### Install Dependencies:
`python3 install_requirements.py`

Note: `python3 install_requirements.py` also tries to install kornia, pytorch, onnx, etc... which are needed if you want to 
compile your own model.

### Running Example As-Is:
`python3 main.py` - Runs depth image pointcloud visualization

### TODO:
- [ ] Fix ImgFrame shape so NN node doesn't spam warnings
- [ ] Get rectified right intrinsics to the NN node somehow
- [ ] Profile the pointclouds / second coming off of the device vs on cpu 
