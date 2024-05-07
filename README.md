## Laboratory work III

Данная лабораторная работа посвещена изучению систем автоматизации сборки проекта на примере **CMake**

```sh
$ open https://cmake.org/
```

## Tasks

- [ ] 1. Создать публичный репозиторий с названием **lab03** на сервисе **GitHub**
- [ ] 2. Ознакомиться со ссылками учебного материала
- [ ] 3. Выполнить инструкцию учебного материала
- [ ] 4. Составить отчет и отправить ссылку личным сообщением в **Slack**

## Tutorial

```sh
andrew@Ubuntu24Laby:~$ cd AndrewB203
andrew@Ubuntu24Laby:~/AndrewB203$ mkdir workspacenew
andrew@Ubuntu24Laby:~/AndrewB203$ cd workspacenew
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew$ pushd .
~/AndrewB203/workspacenew ~/AndrewB203/workspacenew
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew$ source scripts/activate
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew$ git clone https://github.coandrew@Ubuntu24Laby:~/AndrewB203/workspacenew$ git clone https://github.com/AndrewB203/lab02.git lab03
Cloning into 'lab03'...
remote: Enumerating objects: 2993, done.
remote: Counting objects: 100% (2993/2993), done.
remote: Compressing objects: 100% (2301/2301), done.
remote: Total 2993 (delta 516), reused 2990 (delta 515), pack-reused 0
Receiving objects: 100% (2993/2993), 13.50 MiB | 1.07 MiB/s, done.
Resolving deltas: 100% (516/516), done.
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew$ git remote remove origin
fatal: not a git repository (or any of the parent directories): .git
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew$ cd lab03
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ git remote remove origin
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ git remote add originhttps://github.com/AndrewB203/lab03n.git
usage: git remote add [<options>] <name> <url>

    -f, --fetch           fetch the remote branches
    --tags                import all tags and associated objects when fetching
                          or do not fetch any tag at all (--no-tags)
    -t, --track <branch>  branch(es) to track
    -m, --master <branch>
                          master branch
    --mirror[=(push|fetch)]
                          set up remote as a mirror to push to or fetch from
```

```sh
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ g++ -std=c++11 -I./include -c sources/print.cpp
cc1plus: fatal error: sources/print.cpp: No such file or directory
compilation terminated.
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ g++ -std=c++11 -I./include -c sources/print.cpp
cc1plus: fatal error: sources/print.cpp: No such file or directory
compilation terminated.
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ g++ -std=c++11 -I./include -c sources/print.cpp
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ ls print.o
print.o
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ nm print.o | grep print
00000000000000aa t _GLOBAL__sub_I__Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSo
0000000000000000 T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSo
000000000000002a T _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ ar rvs print.a print.o
ar: creating print.a
a - print.o
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ file print.a
print.a: current ar archive
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ g++ -std=c++11 -I./include -c examples/example1.cpp
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ ls example1.o
example1.o
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ g++ example1.o print.a -o example1
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ ./example1 && echo
hello
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ g++ -std=c++11 -I./include -c examples/example2.cpp
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ nm example2.o
                 U __cxa_atexit
                 U __dso_handle
0000000000000000 V DW.ref.__gxx_personality_v0
                 U _GLOBAL_OFFSET_TABLE_
000000000000017e t _GLOBAL__sub_I_main
                 U __gxx_personality_v0
0000000000000000 T main
                 U __stack_chk_fail
                 U _Unwind_Resume
0000000000000128 t _Z41__static_initialization_and_destruction_0ii
                 U _Z5printRKNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEERSt14basic_ofstreamIcS2_E
                 U _ZNSaIcEC1Ev
                 U _ZNSaIcED1Ev
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEEC1EPKcSt13_Ios_Openmode
                 U _ZNSt14basic_ofstreamIcSt11char_traitsIcEED1Ev
                 U _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEEC1EPKcRKS3_
                 U _ZNSt7__cxx1112basic_stringIcSt11char_traitsIcESaIcEED1Ev
                 U _ZNSt8ios_base4InitC1Ev
                 U _ZNSt8ios_base4InitD1Ev
0000000000000000 r _ZStL19piecewise_construct
0000000000000000 b _ZStL8__ioinit
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ g++ example2.o print.a -o example2
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ ./example2
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cat log.txt && echo
hello
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ rm -rf example1.o example2.o print.o
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ rm -rf print.a
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ rm -rf example1 example2
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ rm -rf log.txt
```

```sh
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$  cat > CMakeLists.txt <<EOF
cmake_minimum_required(VERSION 3.4)
project(print)
EOF
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$  cat >> CMakeLists.txt <<EOF
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
EOF
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cat >> CMakeLists.txt <<EOF
add_library(print STATIC \${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)
EOF
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$  cat >> CMakeLists.txt <<EOF
include_directories(\${CMAKE_CURRENT_SOURCE_DIR}/include)
EOF
```

```sh
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake -H. -B_build
-- The C compiler identification is GNU 11.4.0
-- The CXX compiler identification is GNU 11.4.0
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Configuring done
-- Generating done
-- Build files have been written to: /home/andrew/AndrewB203/workspacenew/lab03/_build
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake --build _build
[ 50%] Building CXX object CMakeFiles/print.dir/sources/print.cpp.o
[100%] Linking CXX static library libprint.a
[100%] Built target print
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cat >> CMakeLists.txt <<EOF

add_executable(example1 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example1.cpp)
add_executable(example2 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example2.cpp)
EOF
```

```sh
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cat >> CMakeLists.txt <<EOF

target_link_libraries(example1 print)
target_link_libraries(example2 print)
EOF
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake --build _build
-- Configuring done
-- Generating done
-- Build files have been written to: /home/andrew/AndrewB203/workspacenew/lab03/_build
Consolidate compiler generated dependencies of target print
[ 33%] Built target print
[ 50%] Building CXX object CMakeFiles/example1.dir/examples/example1.cpp.o
[ 66%] Linking CXX executable example1
[ 66%] Built target example1
[ 83%] Building CXX object CMakeFiles/example2.dir/examples/example2.cpp.o
[100%] Linking CXX executable example2
[100%] Built target example2
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake --build _build --target print
[100%] Built target print
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake --build _build --target example1
[ 50%] Built target print
Consolidate compiler generated dependencies of target example1
[100%] Built target example1
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake --build _build --target example2
[ 50%] Built target print
Consolidate compiler generated dependencies of target example2
[100%] Built target example2
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ ls -la _build/libprint.a
-rw-rw-r-- 1 andrew andrew 3126 мая  7 16:57 _build/libprint.a

```

```sh
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ _build/example1 && echo
hello
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$  _build/example2
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cat log.txt && echo
hello
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ rm -rf log.txt
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ git clone https://github.com/tp-
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ git clone https://github.com/tp-labs/lab03 tmp
Cloning into 'tmp'...
remote: Enumerating objects: 91, done.
remote: Counting objects: 100% (30/30), done.
remote: Compressing objects: 100% (9/9), done.
remote: Total 91 (delta 23), reused 21 (delta 21), pack-reused 61
Receiving objects: 100% (91/91), 1.02 MiB | 3.27 MiB/s, done.
Resolving deltas: 100% (41/41), done.
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ mv -f tmp/CMakeLists.txt .
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ rm -rf tmp
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cat CMakeLists.txt
cmake_minimum_required(VERSION 3.4)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

option(BUILD_EXAMPLES "Build examples" OFF)

project(print)

add_library(print STATIC ${CMAKE_CURRENT_SOURCE_DIR}/sources/print.cpp)

target_include_directories(print PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>
)

if(BUILD_EXAMPLES)
  file(GLOB EXAMPLE_SOURCES "${CMAKE_CURRENT_SOURCE_DIR}/examples/*.cpp")
  foreach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
    get_filename_component(EXAMPLE_NAME ${EXAMPLE_SOURCE} NAME_WE)
    add_executable(${EXAMPLE_NAME} ${EXAMPLE_SOURCE})
    target_link_libraries(${EXAMPLE_NAME} print)
    install(TARGETS ${EXAMPLE_NAME}
      RUNTIME DESTINATION bin
    )
  endforeach(EXAMPLE_SOURCE ${EXAMPLE_SOURCES})
endif()

install(TARGETS print
    EXPORT print-config
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/ DESTINATION include)
install(EXPORT print-config DESTINATION cmake)
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake -H. -B_build -DCMAKE_INSTALL_PREFIX=_install
-- Configuring done
-- Generating done
-- Build files have been written to: /home/andrew/AndrewB203/workspacenew/lab03/_build
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ cmake --build _build --target install
Consolidate compiler generated dependencies of target print
[100%] Built target print
Install the project...
-- Install configuration: ""
-- Installing: /home/andrew/AndrewB203/workspacenew/lab03/_install/lib/libprint.a
-- Installing: /home/andrew/AndrewB203/workspacenew/lab03/_install/include
-- Installing: /home/andrew/AndrewB203/workspacenew/lab03/_install/include/print.hpp
-- Installing: /home/andrew/AndrewB203/workspacenew/lab03/_install/cmake/print-config.cmake
-- Installing: /home/andrew/AndrewB203/workspacenew/lab03/_install/cmake/print-config-noconfig.cmake
```

```sh
$ cat >> CMakeLists.txt <<EOF
include_directories(\${CMAKE_CURRENT_SOURCE_DIR}/include)
EOF
```

```sh
$ cmake -H. -B_build
$ cmake --build _build
```

```sh
$ cat >> CMakeLists.txt <<EOF

add_executable(example1 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example1.cpp)
add_executable(example2 \${CMAKE_CURRENT_SOURCE_DIR}/examples/example2.cpp)
EOF
```

```sh
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ tree _install
_install
├── cmake
│   ├── print-config.cmake
│   └── print-config-noconfig.cmake
├── include
│   └── print.hpp
└── lib
    └── libprint.a

3 directories, 4 files
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ git add CMakeLists.txt
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03$ git commit -m"added CMakeLists.txt"
[main eea6f32] added CMakeLists.txt
 1 file changed, 36 insertions(+)
 create mode 100644 CMakeLists.txt
```

```sh
andrew@Ubuntu24Laby:~/AndrewB203/workspacenew/lab03n$ git push origin main
Username for 'https://github.com': AndrewB203
Password for 'https://AndrewB203@github.com': 
Enumerating objects: 87, done.
Counting objects: 100% (87/87), done.
Delta compression using up to 12 threads
Compressing objects: 100% (78/78), done.
Writing objects: 100% (86/86), 50.47 KiB | 6.31 MiB/s, done.
Total 86 (delta 20), reused 7 (delta 0), pack-reused 0
remote: Resolving deltas: 100% (20/20), done.
To https://github.com/AndrewB203/lab03n.git
   ea283f2..7d20a84  main -> main
```

