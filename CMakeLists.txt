cmake_minimum_required(VERSION 3.29)
project(Coleccion_de_Ejercicios_para_Nociones_Clave)

set(CMAKE_CXX_STANDARD 20)

include_directories(.)

add_executable(Problemas1y2
        "Problemas_1_2/main.cpp"
        "Problemas_1_2/Persona.h"
        "Problemas_1_2/Persona.cpp"
        "Problemas_1_2/Estudiante.h"
        "Problemas_1_2/Estudiante.cpp"
)

add_executable(Problemas3_4_5_6_7
        "Problemas_3_4_5_6_7/nuevo.cpp"
        "Problemas_3_4_5_6_7/funciones.cpp"
        "Problemas_3_4_5_6_7/funciones.h"
        "Problemas_3_4_5_6_7/Matematicas.h"
        "Problemas_3_4_5_6_7/Matematicas.cpp"
)

include(FetchContent)
FetchContent_Declare(
        fmt
        GIT_REPOSITORY https://github.com/fmtlib/fmt.git
        GIT TAG        7.1.3

)
FetchContent_MakeAvailable(fmt)

target_link_libraries(Problemas3_4_5_6_7 PRIVATE fmt::fmt)

add_library(Matematicas STATIC "Problemas_3_4_5_6_7/funciones.cpp")
target_link_libraries(Problemas3_4_5_6_7 PRIVATE Matematicas)