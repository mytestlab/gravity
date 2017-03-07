cmake_minimum_required(VERSION 3.6)
project(gravity)

set(CMAKE_C_STANDARD 99)

LINK_DIRECTORIES("c:\\Program Files (x86)\\Windows Kits\\10\\Lib\\10.0.10586.0\\um\\x86\\")

INCLUDE_DIRECTORIES(
        src/shared
        src/compiler
        src/utils
        src/runtime
)

set(SOURCE_FILES
        src/shared/gravity_memory.h
        src/shared/gravity_memory.c
        src/utils/gravity_utils.h
        src/utils/gravity_utils.c
        src/utils/gravity_json.h
        src/utils/gravity_json.c
        src/utils/gravity_debug.h
        src/utils/gravity_debug.c
        src/compiler/gravity_token.h
        src/compiler/gravity_token.c
        src/compiler/gravity_ast.h
        src/compiler/gravity_ast.c
        src/compiler/gravity_lexer.h
        src/compiler/gravity_lexer.c
        src/compiler/gravity_visitor.h
        src/compiler/gravity_visitor.c
        src/compiler/gravity_parser.h
        src/compiler/gravity_parser.c
        src/compiler/gravity_codegen.h
        src/compiler/gravity_codegen.c
        src/compiler/gravity_ircode.h
        src/compiler/gravity_ircode.c
        src/compiler/gravity_optimizer.h
        src/compiler/gravity_optimizer.c
        src/compiler/gravity_semacheck1.h
        src/compiler/gravity_semacheck1.c
        src/compiler/gravity_semacheck2.h
        src/compiler/gravity_semacheck2.c
        src/compiler/gravity_symboltable.h
        src/compiler/gravity_symboltable.c
        src/compiler/gravity_compiler.h
        src/compiler/gravity_compiler.c
        src/runtime/gravity_vm.h
        src/runtime/gravity_vm.c
        src/compiler/debug_macros.h
        src/cli/unittest.c
        src/cli/gravity.c
        )

add_executable(gravity ${SOURCE_FILES})

TARGET_LINK_LIBRARIES(gravity ShLwApi user32)