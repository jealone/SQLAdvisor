cmake_minimum_required (VERSION 2.6)
project(sqladvisor)

# /usr/local/sqlparser为sqlparser库安装目录，必要时进行修改
include_directories("/usr/local/dependency/sqlparser/include")
include_directories("/usr/local/dependency/sqlparser/include/regex")
include_directories("/usr/lib64/glib-2.0/include")
include_directories("/usr/include/glib-2.0")
link_directories("/usr/local/dependency/sqlparser/lib")
link_directories("/usr/lib64")

set(TEST_SRC main.cc)
add_executable(sqladvisor ${TEST_SRC})

#如果是sqlparser debug库，则应连接的库为sqlparser-debug
target_link_libraries(sqladvisor sqlparser-debug)
target_link_libraries(sqladvisor perconaserverclient)
target_link_libraries(sqladvisor glib-2.0)
