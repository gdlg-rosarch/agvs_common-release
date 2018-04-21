# Script generated with Bloom
pkgdesc="ROS - The agvs_pad package.Component to control the robot by using a ps3 pad."
url='http://wiki.ros.org/agvs_pad'

pkgname='ros-kinetic-agvs-pad'
pkgver='0.1.3_2'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-ackermann-msgs'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-geometry-msgs'
'ros-kinetic-robotnik-msgs'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
)

depends=('ros-kinetic-ackermann-msgs'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-geometry-msgs'
'ros-kinetic-robotnik-msgs'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-std-srvs'
)

conflicts=()
replaces=()

_dir=agvs_pad
source=()
md5sums=()

prepare() {
    cp -R $startdir/agvs_pad $srcdir/agvs_pad
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

