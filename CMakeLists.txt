cmake_minimum_required(VERSION 3.25.0)
project(ImGuizmo)

file(GLOB SOURCE_FILES_EXE 
	 ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp
)

# Add header files
file(GLOB HEADER_FILES_EXE 
	 ${CMAKE_CURRENT_SOURCE_DIR}/*.h
)

add_library (ImGuizmo ${HEADER_FILES_EXE} ${SOURCE_FILES_EXE})

target_include_directories(ImGuizmo PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
	PUBLIC ${CMAKE_SOURCE_DIR}/thirdParty/imgui/backends
	PUBLIC ${CMAKE_SOURCE_DIR}/thirdParty/imgui/
)

target_link_libraries(ImGuizmo PRIVATE imgui)
