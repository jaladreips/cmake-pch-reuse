# cmake-pch-reuse
An actual working example of creating a dedicated CMake library that precompiles headers

This thread was a great help: https://gitlab.kitware.com/cmake/cmake/-/issues/20288

This small repo shows a case of 2 projects that reuse precompiled headers from the same library.
The PCH library was created as STATIC, because INTERFACE does not run the compiler, which is necessary to actually create the cmake_pch.cxx file.
STATIC library requires a source file to compile, hence the dummy PCH file generation.

I hope this helps at least one person like me who struggled to get this right with no examples anywhere on the web.
