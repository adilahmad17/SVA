set( LLVM_LINK_COMPONENTS
  support
  )

set( LLVM_USED_LIBS
  clangBasic
  clangLex
  clangSema
  )

add_clang_executable(diagtool
  diagtool_main.cpp
  DiagTool.cpp
  ListWarnings.cpp
)

if(UNIX)
  set(CLANGXX_LINK_OR_COPY create_symlink)
else()
  set(CLANGXX_LINK_OR_COPY copy)
endif()

install(TARGETS diagtool 
  RUNTIME DESTINATION bin)
