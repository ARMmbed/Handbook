<h2 id="contributing-storage">Storage</h2>

Storage support is split between filesystems and their underlying block device support. The <a href="/docs/v5.6/reference/storage-overview.html" target="_blank">storage API page</a> has more information on existing APIs in Mbed OS for both interfaces.

#### Block Device

Adding a block device implementation is required for backing filesystems on new hardware. You can extend the <a href="https://os.mbed.com/docs/v5.6/mbed-os-api-doxy/class_heap_block_device.html" target="_blank">BlockDevice</a> class to provide support for unsupported storage. 

If you want to port a new filesystem to Mbed OS on existing storage options you can skip to the following section.

#### Filesystems

To implement a new file system in Mbed OS, an implementor needs to provide the abstract functions in the file system interface. The <a href="https://os.mbed.com/docs/v5.6/mbed-os-api-doxy/class_f_a_t_file_system.html" target="_blank">FAT file system</a> provides an excellent example.

A minimal file system needs to provide the following functions:

- `file_open`.
- `file_close`.
- `file_read`.
- `file_write`.
- `file_seek`.

Here is the full API that a filesystem may implement:

[![View code](https://www.mbed.com/embed/?type=library)](https://github.com/ARMmbed/mbed-os/blob/master/features/filesystem/FileSystem.h#L205)

Filesystems must be backed by a block device in Mbed OS. If you are using supported hardware then you can use the Mbed OS block device classes, otherwise view the block device porting section earlier in this guide.

#### Related content

- <a href="https://os.mbed.com/docs/v5.6/mbed-os-api-doxy/class_heap_block_device.html" target="_blank">BlockDevice</a>.
- <a href="https://os.mbed.com/docs/v5.6/mbed-os-api-doxy/class_f_a_t_file_system.html" target="_blank">FAT file system</a>.
