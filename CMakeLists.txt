cmake_minimum_required(VERSION 2.8.12)

project( kplasmafoxhelper )

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

find_package(ECM 1.0.0 REQUIRED NO_MODULE)

set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR})

include(KDEInstallDirs)
include(KDECMakeSettings)
include(KDECompilerSettings)
include(FeatureSummary)

find_package(KF5 REQUIRED COMPONENTS Notifications KIO WindowSystem I18n)

add_executable(kplasmafoxhelper main.cpp)

target_link_libraries(kplasmafoxhelper KF5::I18n KF5::KIOWidgets KF5::Notifications KF5::WindowSystem)

install(TARGETS kplasmafoxhelper DESTINATION ${CMAKE_INSTALL_PREFIX}/lib/mozilla/)
install(FILES kplasmafoxhelper.notifyrc DESTINATION ${KNOTIFYRC_INSTALL_DIR})
