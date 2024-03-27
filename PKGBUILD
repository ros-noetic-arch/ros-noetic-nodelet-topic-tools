# Script generated with import_catkin_packages.py.
# For more information: https://github.com/bchretien/arch-ros-stacks.
pkgdesc="ROS - This package contains common nodelet tools such as a mux, demux and throttle."
url='https://wiki.ros.org/nodelet_topic_tools'

pkgname='ros-noetic-nodelet-topic-tools'
pkgver='1.11.0'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=1
license=('BSD')

ros_makedepends=(
	ros-noetic-dynamic-reconfigure
	ros-noetic-catkin
)

makedepends=(
	'cmake'
	'ros-build-tools'
	${ros_makedepends[@]}
	boost
)

ros_depends=(
	ros-noetic-nodelet
	ros-noetic-dynamic-reconfigure
	ros-noetic-roscpp
	ros-noetic-message-filters
	ros-noetic-pluginlib
)

depends=(
	${ros_depends[@]}
	boost
)

_dir="nodelet_core-${pkgver}/nodelet_topic_tools"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros/nodelet_core/archive/${pkgver}.tar.gz")
sha256sums=('c5f4f17a2165f7201964c985019d41e7c4664307f6bc6ec70a48c97d4a6166f9')

build() {
	# Use ROS environment variables.
	source /usr/share/ros-build-tools/clear-ros-env.sh
	[ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

	# Create the build directory.
	[ -d ${srcdir}/build ] || mkdir ${srcdir}/build
	cd ${srcdir}/build

	# Build the project.
	cmake ${srcdir}/${_dir} \
		-DCATKIN_BUILD_BINARY_PACKAGE=ON \
		-DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
		-DPYTHON_EXECUTABLE=/usr/bin/python \
		-DSETUPTOOLS_DEB_LAYOUT=OFF
	make
}

package() {
	cd "${srcdir}/build"
	make DESTDIR="${pkgdir}/" install
}
