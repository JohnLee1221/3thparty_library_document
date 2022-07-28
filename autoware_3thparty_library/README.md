******
boost_1_69_0        (don't change the version)
﻿
	./bootstrap.sh
	sudo ./b2 install

autoware.auto need libboost_python3 library

	./bootstrap.sh --with-python=/usr/bin/python3 --with-python-root=/usr
	sudo ./b2 --with-python install
	sudo ln -s libboost_python38.a libboost_python3.8.10.a
	sudo ln -s libboost_python38.so libboost_python3.8.10.so
	sudo ln -s libboost_numpy38.a libboost_numpy3.8.10.a
	sudo ln -s libboost_numpy38.so libboost_numpy3.8.10.so

******
googletest					(1.12.0)
octomap						(tag:v1.9.3/ros2)
geographiclib-1.50.1
libzmq						(tag: v4.3.4)
cppzmq						(tag: v4.3.0)
cgal
apex_test_tools/apex_test_tools
gflags
glog
memory
pugixml						(tag: v1.12)
SPIRV-Headers
SPIRV-Tools
orocos_kinematics_dynamics/orocos_kdl		(foxy)
tf2_sensor_msgs
oneTBB						(tag: v2021.3.0)
flann						(tag: 1.9.1)
lapack						(tag: v3.10.0)
﻿
	cmake ..
	make -j8 && sudo make install

******
gmp-6.2.0+dfsg
mpfr4-4.0.2

	./configure
	make -j8 && sudo make install

******
graphicsmagick-1.4+really1.3.35
﻿
	./configure --without-prel --enable-shared --disable-openmp
	make -j8 && sudo make install
	
******
ceres-solver 					(tag: 1.14.0)
﻿
	cmake ..
	make -j8 && sudo make install

		colcon build --packages-select smac_planner
		CMakeLists.txt - line 22
		#find_package(Ceres REQUIRED COMPONENTS SuiteSparse)
		find_package(Ceres REQUIRED)

******	
ompl
	cmake ..
	make -j8 && sudo make install

******
waylan-1.18.91
libxext-1.3.4
libxrender-0.9.10
libxrandr-1.5.2
﻿
	./configure
	make -j8 && sudo make install

******
Vulkan-Headers					(tag: v1.3.204)
Vulkan-Loader					(tag: v1.3.204)
OpenBLAS					(tag: v0.3.20)
﻿
	cmake ..
	make -j8 && sudo make install

******
﻿﻿VTK
pcl						(tag: v1.10.0)
﻿
	cmake ..
	make -j8 && sudo make install

		CMake Error at /usr/local/share/pcl-1.10/PCLConfig.cmake:56 (message):
		PCL can not be found on this machine
		Call Stack (most recent call first):
		/usr/local/share/pcl-1.10/PCLConfig.cmake:452 (pcl_report_not_found)
		CMakeLists.txt:23 (find_package)
﻿

		sudo vim /usr/local/share/pcl-1.10/PCLConfig.cmake
		更改line 423 
		if(EXISTS "/usr/local/include/pcl-1.10/pcl/pcl_config.h")

******
packages compress:

		nav2_system_tests
		nav2_rviz_plugins
		autoware_rviz_plugins
		grid_map_rviz_plugin

******
packages building error
		--- stderr: nav2_bt_navigator                             
		/usr/bin/ld: /home/linearx/linearx/AutowareAuto/install/nav2_behavior_tree/lib/libnav2_behavior_tree.so: undefined reference to `BT::PublisherZMQ::PublisherZMQ(BT::Tree const&, unsigned int, unsigned int, unsigned int)'
		解决方案是:
		/src/external/behaviortree_cpp_v3-release/CMakeLists.txt
		lines 173 添加 : src/loggers/bt_zmq_publisher.cpp
