# Script generated with Bloom
pkgdesc="ROS - turtlesim is a tool made for teaching ROS and ROS packages."
url='http://www.ros.org/wiki/turtlesim'

pkgname='ros-melodic-turtlesim'
pkgver='0.9.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('qt5-base'
'ros-melodic-catkin'
'ros-melodic-geometry-msgs'
'ros-melodic-message-generation'
'ros-melodic-rosconsole'
'ros-melodic-roscpp'
'ros-melodic-roscpp-serialization'
'ros-melodic-roslib'
'ros-melodic-rostime'
'ros-melodic-std-msgs'
'ros-melodic-std-srvs'
)

depends=('qt5-base'
'ros-melodic-geometry-msgs'
'ros-melodic-message-runtime'
'ros-melodic-rosconsole'
'ros-melodic-roscpp'
'ros-melodic-roscpp-serialization'
'ros-melodic-roslib'
'ros-melodic-rostime'
'ros-melodic-std-msgs'
'ros-melodic-std-srvs'
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
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
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

