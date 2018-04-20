# Script generated with Bloom
pkgdesc="ROS - The tuw_ellipses package contains a computer vision library which is able to detect ellipses within images. The package is able to estimate the pose of the circle related to the ellipse the circle diameter as well as the camera parameter are known. A dynamic reconfigure interface allows the user to tune the parameter of the system to ones needs. But be aware that the pose of a projected circle within a image (ellipse) has two solutions and only one is published as TF."


pkgname='ros-kinetic-tuw-ellipses'
pkgver='0.0.7_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('eigen3'
'ros-kinetic-catkin'
'ros-kinetic-cmake-modules'
'ros-kinetic-cv-bridge'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-marker-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-tf'
)

depends=('ros-kinetic-cv-bridge'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-marker-msgs'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-rospy'
'ros-kinetic-tf'
)

conflicts=()
replaces=()

_dir=tuw_ellipses
source=()
md5sums=()

prepare() {
    cp -R $startdir/tuw_ellipses $srcdir/tuw_ellipses
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

