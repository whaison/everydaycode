cmake_minimum_required(VERSION 2.8)

PROJECT(wakeonlan)

IF(WIN32)
	SET(myinc $ENV{DEV_HOME}/poco/include)
ELSE(WIN32)
	SET(myinc /usr/local/include)
ENDIF(WIN32)

INCLUDE_DIRECTORIES(
	${myinc}
)

IF(WIN32)
	LINK_DIRECTORIES(
		$ENV{DEV_HOME}/poco/lib
	)
	ADD_DEFINITIONS(-DPOCO_STATIC)
ENDIF(WIN32)

SET(sources
	wakeonlan.cpp
)

ADD_EXECUTABLE(wakeonlan ${sources})