set(MY_PROJ_NAME "pegasus_server")

# Source files under CURRENT project directory will be automatically included.
# You can manually set MY_PROJ_SRC to include source files under other directories.
set(MY_PROJ_SRC "")

# Search mode for source files under CURRENT project directory?
# "GLOB_RECURSE" for recursive search
# "GLOB" for non-recursive search
set(MY_SRC_SEARCH_MODE "GLOB")

set(MY_PROJ_LIBS
    dsn_replica_server
    dsn_meta_server
    dsn_replication_common
    dsn_client
    dsn.block_service.local
    dsn.block_service.fds
    dsn.block_service
    dsn.failure_detector
    dsn.replication.zookeeper_provider
    dsn_utils
    RocksDB::rocksdb
    pegasus_reporter
    pegasus_base
    pegasus_client_static
    zookeeper_mt
    event
    galaxy-fds-sdk-cpp
    PocoNet
    PocoFoundation
    PocoNetSSL
    PocoJSON
    )

set(MY_BOOST_LIBS Boost::system Boost::filesystem Boost::regex)

set(MY_BINPLACES "${CMAKE_CURRENT_SOURCE_DIR}/config.ini")

add_definitions(-Wno-attributes)

SET(CMAKE_INSTALL_RPATH ".")
SET(CMAKE_BUILD_WITH_INSTALL_RPATH TRUE)

dsn_add_executable()
dsn_install_executable()
