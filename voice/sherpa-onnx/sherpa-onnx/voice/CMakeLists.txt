include_directories(${PROJECT_SOURCE_DIR} 
/home/luckfox/work/AI面试助手/zmq-comm-kit/include
)


 add_executable(sherpa-onnx-microphone-test1
    sherpa-onnx-microphone.cc
    microphone.cc
  )


target_link_libraries(sherpa-onnx-microphone-test1 portaudio_static sherpa-onnx-core /home/luckfox/work/AI面试助手/zmq-comm-kit/build/libzmq_component.a zmq)


target_link_libraries(sherpa-onnx-microphone-test1 "-Wl,-rpath,${SHERPA_ONNX_RPATH_ORIGIN}/../lib")
target_link_libraries(sherpa-onnx-microphone-test1 "-Wl,-rpath,${SHERPA_ONNX_RPATH_ORIGIN}/../../../sherpa_onnx/lib")
  
install(
    TARGETS sherpa-onnx-microphone-test1 
    DESTINATION
      bin

  )
