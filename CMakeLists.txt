project(om-user-manager)
SET(PROJECT_VERSION "0.0.1")

cmake_minimum_required(VERSION 2.8.12 FATAL_ERROR)
set(QT_MIN_VERSION "5.11.0")
find_package(ECM 5.18.0 REQUIRED NO_MODULE)
set(CMAKE_MODULE_PATH ${ECM_MODULE_PATH} ${ECM_KDE_MODULE_DIR} ${PROJECT_SOURCE_DIR})

include(ECMInstallIcons)
include(FeatureSummary)
include(KDEInstallDirs)
include(KDECMakeSettings)
include(KDECompilerSettings)

find_package(Qt5 ${QT_MIN_VERSION} CONFIG REQUIRED COMPONENTS Core Gui Widgets DBus Quick)
find_package(KF5 REQUIRED COMPONENTS
    CoreAddons
    Auth
    ConfigWidgets
    ItemModels
    Notifications
    KCMUtils
    IconThemes)

add_subdirectory(src)

feature_summary(WHAT ALL FATAL_ON_MISSING_REQUIRED_PACKAGES)
