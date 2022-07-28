******
tinyxml2					(tag: 8.0.0)
eigen3-3.3.7 
bullet3					(tag: 3.24)
foonathan_memory_vendor			(tag: v.1.2.0)

	cmake ..
	make -j8 && sudo make install
	
******
help2man-1.48.1
texinfo-6.5

	./configure
	make -j8 && sudo make install

******
asio-1.12.2

	./configure --without-boost
	make -j8 && sudo make install
	
******
automake-1.16.5
﻿
	./bootstrap
	./configure
	make -j8 && sudo make install

﻿
******
libtool					(v2.4.7)

	./bootstrap
		bootstrap: running: git clone --shallow-since=2019-02-19 'git://git.savannah.gnu.org/gnulib.git' 'gnulib'
		Cloning into 'gnulib'...
	./configure
	make -j8 && sudo make install

******
libexpat
apr-1.7.0

	./buildconf
	./configure
	make -j8 && sudo make install

******
apr-util-1.6.1
﻿
	./configure --with-apr=/usr/local/apr
	make -j8 && sudo make install

******
logging-log4cxx				(tag: v0.11.0)
﻿
﻿	./autogen.sh
	./configure --with-apr=/usr/local/apr --with-apr-util=/usr/local/apr
	make -j8 && sudo make install
	
		export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/usr/local/apr/lib/

******
Fast-CDR					(v1.0.13)
opencv

	cmake ..
	make -j8 && sudo make install

******
Fast-RTPS					(2.7.x)
﻿
	cmake -DTHIRDPARTY=ON ..
	make -j8 && sudo make install
	
******
src/ros2/rosidl/rosidl_generator_c		(python module)
﻿
	sudo apt install ros-foxy-rosidl-generator-c

******
src/ros2/rcutils				(python module)
		--- stderr: rcutils
		CMake Error at /usr/local/share/cmake-3.18/Modules/FindPackageHandleStandardArgs.cmake:165 (message):
		Could NOT find PythonLibs (missing: PYTHON_LIBRARIES PYTHON_INCLUDE_DIRS)
		(Required is at least version "3.5")
﻿
	sudo apt install python-dev python3-dev
	
******
packages compress:

		src/ros-visualization
		src/ros2/rivz
		src/ros/ros_tutorials/turtlesim
