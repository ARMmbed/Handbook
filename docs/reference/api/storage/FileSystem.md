## FileSystem

The file system API provides a common interface for implementing a file system on a [block-based storage device](/docs/development/reference/contributing-storage.html#block-devices). The file system API is a class-based interface, but implementing the file system API provides the standard POSIX file API familiar to C users.

The main purpose of a FileSystem is to be instantiated. The FileSystem's constructor can take in a BlockDevice and mount point specified as a string, as well as other implementation-specific configuration options. The mount point can then act as the first directory in any paths in Mbed OS when used with the POSIX API. This gives you access to files inside the file system. The mount point can be `NULL` if you only need to use the FileSystem as a C++ object.

The FileSystem's `file` and `dir` functions are protected because you should not use the FileSystem `file` and `dir` functions directly. They are only a convenience for implementors. Instead, the [File](file.html) and [Dir](dir.html) classes provide access to file and directory operations in a C++ class that respects [RAII](https://os-doc-builder.test.mbed.com/docs/development/introduction/glossary.html#r) and other C++ conventions.

### File system class reference

[![View code](https://www.mbed.com/embed/?type=library)](http://os-doc-builder.test.mbed.com/docs/development/mbed-os-api-doxy/classmbed_1_1_file_system.html)

### File system example

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-filesystem/)](http://os.mbed.com/teams/mbed-os-examples/code/mbed-os-example-filesystem/file/adaa6c01d727/main.cpp)

### Sector requirements

**LittleFS requirements:**

- 4 blocks root dir.
- 2 blocks per dir.
- 1 block per file.

**FATFS requirements:**

- Hard minimum: 256 blocks.
- 128 blocks for FAT table.
- 1 block per dir.
- 1 block per file.

### Related content

- [Storage configuration](configuration-storage.html).
- [File](file.html).
- [Dir](dir.html).
