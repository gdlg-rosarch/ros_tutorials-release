# Script generated with Bloom
pkgdesc="ROS - turtlesim is a tool made for teaching ROS and ROS packages."
url='http://www.ros.org/wiki/turtlesim'

pkgname='ros-lunar-turtlesim'
pkgver='0.8.1_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('qt5-base'
'ros-lunar-catkin'
'ros-lunar-geometry-msgs'
'ros-lunar-message-generation'
'ros-lunar-rosconsole'
'ros-lunar-roscpp'
'ros-lunar-roscpp-serialization'
'ros-lunar-roslib'
'ros-lunar-rostime'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
)

depends=('qt5-base'
'ros-lunar-geometry-msgs'
'ros-lunar-message-runtime'
'ros-lunar-rosconsole'
'ros-lunar-roscpp'
'ros-lunar-roscpp-serialization'
'ros-lunar-roslib'
'ros-lunar-rostime'
'ros-lunar-std-msgs'
'ros-lunar-std-srvs'
)

conflicts=()
replaces=()

_dir=turtlesim
source=()
md5sums=()

prepare() {
    cp -R $startdir/turtlesim $srcdir/turtlesim
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
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

