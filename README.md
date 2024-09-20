# SLET

SLET is an edge-based method for 6DOF pose tracking of rigid objects using a monocular RGB camera. The edge confidence is integrated into the edge-based energy function to reduce the influence of false contour points caused by cluttered backgrounds and partial occlusions. We also extend our method to multi-object tracking which can handle mutual occlusions. 

## Copyright disclaimer
This repository is a migration of the original copy of SLET implementation hosted on [Gitee](https://gitee.com/huanghone/SLET). The ownership fully belongs to the original creator, Dr. Hong Huang. This repository was only created to share the work with a broader community.

### Preview Video

[![PG'20 supplementary video.](https://img.youtube.com/vi/-LoPCaPWs70/0.jpg)](https://www.youtube.com/watch?v=-LoPCaPWs70)


### Related Papers

If you use SLET in your research work, please cite:

	@article{Huang2020,
		AUTHOR  = {Hong Huang and Fan Zhong and Yuqing Sun and Xueying Qin},
		TITLE   = {An occlusion‐aware edge‐based method for monocular 3D object tracking using edge confidence},
		JOURNAL = "Computer Graphics Forum",
		VOLUME  = {39}, 
		NUMBER  = {7},
		YEAR    = {2020},	
		PAGES   = {399-409},
	}

# Dependencies

SLET depends on (recent versions of) the following software libraries:

* Assimp
* OpenCV
* OpenGL
* Qt

**It must be run from the root directory (that contains the *src* folder) otherwise the relative paths to the model and the shaders will be wrong.**

The code was developed and tested under Windows 10. It should, however, also run on IOS and Linux systems with (probably) a few minor changes required. Nothing is plattform specific by design.


# How To Use

The general usage of the algorithm is demonstrated in a small example command line application provided in `run_on_video.cc`. Here the pose of a single 3D model is refined with respect to a given example image. The extension to actual pose tracking and using multiple objects should be straight foward based on this example. Simply replace the example image with the live feed from a camera or a video and add your own 3D models instead.

For the best performance when using your own 3D models, please **ensure that each 3D model consists of a maximum of around 4000 - 7000 vertices and is equally sampled across the visible surface**. This can be enforced by using a 3D mesh manipulation software such as MeshLab (http://www.meshlab.net/) or OpenFlipper (https://www.openflipper.org/).


# Dataset

To test the algorithm you can for example use the corresponding dataset available for download at: https://github.com/huanghone/RBOTE


# License

SLET is licensed under the GNU General Public License Version 3 (GPLv3), see http://www.gnu.org/licenses/gpl.html.
