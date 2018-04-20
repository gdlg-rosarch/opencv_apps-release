# Script generated with Bloom
pkgdesc="ROS - <p>opencv_apps provides various nodes that run internally OpenCV's functionalities and publish the result as ROS topics. With opencv_apps, you can skip writing OpenCV application codes for a lot of its functionalities by simply running a launch file that corresponds to OpenCV's functionality you want.</p> <ul> <li>You can have a look at all launch files provided here (be sure to choose the correct branch. As of Sept. 2016 indigo branch is used for ROS Indigo, Jade, and Kinetic distros).</li> <li>Some of the features covered by opencv_apps are explained in <a href="http://wiki.ros.org/opencv_apps">the wiki</a>.</li> </ul> <p>The most of code is originally taken from https://github.com/Itseez/opencv/tree/master/samples/cpp</p>"


pkgname='ros-kinetic-opencv-apps'
pkgver='2.0.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-compressed-image-transport'
'ros-kinetic-cv-bridge'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-proc'
'ros-kinetic-image-transport'
'ros-kinetic-image-view'
'ros-kinetic-message-generation'
'ros-kinetic-nodelet'
'ros-kinetic-rosbag'
'ros-kinetic-roscpp'
'ros-kinetic-rosservice'
'ros-kinetic-rostest'
'ros-kinetic-rostopic'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
'ros-kinetic-topic-tools'
)

depends=('ros-kinetic-cv-bridge'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-transport'
'ros-kinetic-message-runtime'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
)

conflicts=()
replaces=()

_dir=opencv_apps
source=()
md5sums=()

prepare() {
    cp -R $startdir/opencv_apps $srcdir/opencv_apps
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

