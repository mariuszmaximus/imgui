cmake_minimum_required(VERSION 3.0.0)
project(imgui VERSION 0.1.0)

include_directories(${CMAKE_SOURCE_DIR}/.. )
include_directories(${CMAKE_SOURCE_DIR}/../backends)
aux_source_directory(../ SRC_FILES)

#######################################
add_executable(example_allegro5 ${SRC_FILES}
    example_allegro5/main.cpp
    ../backends/imgui_impl_allegro5.cpp
)
target_link_libraries(example_allegro5
    allegro
    liballegro_primitives.dll.a
)

#######################################
add_executable(example_glfw_opengl2 ${SRC_FILES}
    example_glfw_opengl2/main.cpp
    ../backends/imgui_impl_glfw.cpp
    ../backends/imgui_impl_opengl2.cpp
)
target_link_libraries(example_glfw_opengl2
    opengl32.lib
    glfw3.lib
)

#######################################
add_executable(example_glfw_opengl3 ${SRC_FILES}
    example_glfw_opengl3/main.cpp
    ../backends/imgui_impl_glfw.cpp
    ../backends/imgui_impl_opengl3.cpp
)
target_link_libraries(example_glfw_opengl3
    opengl32.lib
    glfw3.lib
)

#######################################
add_executable(example_glfw_vulkan ${SRC_FILES}
    example_glfw_vulkan/main.cpp
    ../backends/imgui_impl_glfw.cpp
    ../backends/imgui_impl_vulkan.cpp
)
find_package(Vulkan REQUIRED)
target_link_libraries(example_glfw_vulkan
    opengl32.lib
    glfw3.lib
    Vulkan::Vulkan
)

#######################################
add_executable(example_glut_opengl2 ${SRC_FILES}
    example_glut_opengl2/main.cpp
    ../backends/imgui_impl_glut.cpp
    ../backends/imgui_impl_opengl2.cpp
    ../backends/imgui_impl_glfw.cpp
)
target_link_libraries(example_glut_opengl2
    opengl32.lib
    freeglut.lib
    glfw3.lib
)

#######################################
add_executable(example_null ${SRC_FILES}
    example_null/main.cpp
)

#######################################
add_executable(example_sdl2_directx11 ${SRC_FILES}
    example_sdl2_directx11/main.cpp
    ../backends/imgui_impl_sdl2.cpp
    ../backends/imgui_impl_dx11.cpp
)
target_link_libraries(example_sdl2_directx11
    SDL2
    SDL2main
    d3d11
    d3dcompiler
)

#######################################
add_executable(example_sdl2_vulkan ${SRC_FILES}
    example_sdl2_vulkan/main.cpp
    ../backends/imgui_impl_sdl2.cpp
    ../backends/imgui_impl_vulkan.cpp
)
target_link_libraries(example_sdl2_vulkan
    SDL2
    SDL2main
    Vulkan::Vulkan
)

#######################################
add_executable(example_win32_directx9 ${SRC_FILES}
    example_win32_directx9/main.cpp
    ../backends/imgui_impl_dx9.cpp
    ../backends/imgui_impl_win32.cpp
)
target_link_libraries(example_win32_directx9 d3d9 Dwmapi)

#######################################
add_executable(example_win32_directx10 ${SRC_FILES}
    example_win32_directx10/main.cpp
    ../backends/imgui_impl_dx10.cpp
    ../backends/imgui_impl_win32.cpp
)
target_link_libraries(example_win32_directx10 d3d10 d3dcompiler Dwmapi)

#######################################
add_executable(example_win32_directx11 ${SRC_FILES}
    example_win32_directx11/main.cpp
    ../backends/imgui_impl_dx11.cpp
    ../backends/imgui_impl_win32.cpp
)
target_link_libraries(example_win32_directx11 d3d11 d3dcompiler Dwmapi)

#######################################
add_executable(example_win32_directx12 ${SRC_FILES}
    example_win32_directx12/main.cpp
    ../backends/imgui_impl_dx12.cpp
    ../backends/imgui_impl_win32.cpp
)
target_link_libraries(example_win32_directx12 d3d12 d3dcompiler Dwmapi DXGI)

