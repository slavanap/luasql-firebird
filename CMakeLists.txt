# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( luasql C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

include_directories ( src )

find_package ( Firebird REQUIRED )
include_directories ( SYSTEM ${FIREBIRD_INCLUDE_DIR} )
install_lua_module ( luasql.firebird src/ls_firebird.c src/luasql.c LINK ${FIREBIRD_LIBRARIES} )

find_package ( PostgreSQL REQUIRED )
include_directories ( SYSTEM ${PostgreSQL_INCLUDE_DIRS} )
install_lua_module ( luasql.postgres src/ls_postgres.c src/luasql.c LINK ${PostgreSQL_LIBRARIES} )