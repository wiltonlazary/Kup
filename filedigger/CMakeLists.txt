include_directories("../daemon")
include_directories("../kioslave")

set(filedigger_SRCS
filedigger.cpp
main.cpp
mergedvfs.cpp
mergedvfsmodel.cpp
restoredialog.cpp
restorejob.cpp
versionlistdelegate.cpp
versionlistmodel.cpp
../kioslave/vfshelpers.cpp
../kcm/dirselector.cpp
)

add_definitions(-fexceptions)

ki18n_wrap_ui(filedigger_SRCS restoredialog.ui)
add_executable(kup-filedigger ${filedigger_SRCS})
target_link_libraries(kup-filedigger
Qt5::Core
Qt5::Gui
KF5::KIOCore
KF5::KIOFileWidgets
KF5::I18n
KF5::IconThemes
git24kup
)

########### install files ###############
install(TARGETS kup-filedigger ${INSTALL_TARGETS_DEFAULT_ARGS})
