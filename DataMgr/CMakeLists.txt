find_package(CUDA)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-unused-result")

set(datamgr_source_files
    DataMgr.cpp
    Encoder.cpp
    StringNoneEncoder.cpp
    FileMgr/GlobalFileMgr.cpp
    FileMgr/FileMgr.cpp
    FileMgr/FileBuffer.cpp
    FileMgr/FileInfo.cpp
    FileMgr/File.cpp
    BufferMgr/GpuCudaBufferMgr/GpuCudaBufferMgr.cpp
    BufferMgr/GpuCudaBufferMgr/GpuCudaBuffer.cpp
    BufferMgr/CpuBufferMgr/CpuBufferMgr.cpp
    BufferMgr/CpuBufferMgr/CpuBuffer.cpp
    BufferMgr/BufferMgr.cpp
    BufferMgr/Buffer.cpp
)

add_library(DataMgr ${datamgr_source_files})

target_link_libraries(DataMgr CudaMgr ${Boost_THREAD_LIBRARY} ${Glog_LIBRARIES})
