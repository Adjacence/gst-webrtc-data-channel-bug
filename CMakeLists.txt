cmake_minimum_required(VERSION 3.0)

find_package(PkgConfig REQUIRED)

pkg_check_modules(GST REQUIRED gstreamer-1.0 gstreamer-sdp-1.0 gstreamer-webrtc-1.0)

add_executable(gst-webrtc-data-channel-bug main.c)
target_compile_options(gst-webrtc-data-channel-bug PUBLIC ${GST_CFLAGS} -DGST_USE_UNSTABLE_API)
target_include_directories(gst-webrtc-data-channel-bug PUBLIC ${GST_INCLUDE_DIRS})
target_link_libraries(gst-webrtc-data-channel-bug ${GST_LIBRARIES})
