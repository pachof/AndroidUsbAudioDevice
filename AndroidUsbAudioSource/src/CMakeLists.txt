find_package(fmt CONFIG REQUIRED)
 find_package(libusb-1.0 CONFIG REQUIRED)
 set(CMAKE_PREFIX_PATH ${CMAKE_PREFIX_PATH} "/usr/lib/lib/cmake/portaudio/")
 find_package(PortAudio CONFIG REQUIRED)

add_executable(AndroidUsbAudioSource
	"android_usb_audio_source.cpp"
        "adk.hpp"
        "adk.cpp"
)

target_include_directories(AndroidUsbAudioSource PRIVATE ${LIBUSB_INCLUDE_DIRS})
target_link_libraries(AndroidUsbAudioSource PRIVATE fmt::fmt portaudio ${LIBUSB_LIBRARIES})
