## 2. An Architectural Overview of the Kernel
#### Darwin

The XNU Kernel is an open-source project. It and other core parts of it are collectively referred to as Darwin, such as QuickTime and the Classic, Carbon, and Cocoa JDK application envirnoments. 
Darwin is based on BSD. Because it is open-source, developers can actually be a part of Darwin or use it in their own projects.

#### Architecture

The foundation layer of the XNU kernel is based on many singular architectural components:

![osxarchitecture](https://user-images.githubusercontent.com/67783955/174450164-1b4faf34-3d71-402f-a85a-0bffa8fd8cf3.gif)


#### Mach
Mach manages processor resources such as CPU usage and memory, handles scheduling, provides memory protection, and provides a messaging-centered infrastructure to the rest of the operating-system layers. The Mach component provides
untyped interprocess communication (IPC)
remote procedure calls (RPC)
scheduler support for symmetric multiprocessing (SMP)
support for real-time services
virtual memory support
support for pagers
modular architecture

#### BSD
Above the Mach layer, the BSD layer provides “OS personality” APIs and services. The BSD layer is based on the BSD kernel, primarily FreeBSD. The BSD component provides
file systems
networking (except for the hardware device level)
UNIX security model
syscall support
the BSD process model, including process IDs and signals
FreeBSD kernel APIs
many of the POSIX APIs
kernel support for threads (POSIX threads)

#### Networking
OS X networking takes advantage of BSD’s advanced networking capabilities to provide support for modern features, such as Network Address Translation (NAT) and firewalls. The networking component provides
4.4BSD TCP/IP stack and socket APIs
support for both IP and DDP (AppleTalk transport)
multihoming
routing
multicast support
server tuning
packet filtering
Mac OS Classic support (through filters)

#### Filesystems
OS X provides support for numerous types of file systems, including HFS, HFS+, UFS, NFS, ISO 9660, and others. The default file-system type is HFS+; OS X boots (and “roots”) from HFS+, UFS, ISO, NFS, and UDF. Advanced features of OS X file systems include an enhanced Virtual File System (VFS) design. VFS provides for a layered architecture (file systems are stackable). The file system component provides
UTF-8 (Unicode) support
increased performance over previous versions of Mac OS.

#### I/O Kit
The I/O Kit provides a framework for simplified driver development, supporting many categories of devices. The I/O Kit features an object-oriented I/O architecture implemented in a restricted subset of C++. The I/O Kit framework is both modular and extensible. The I/O Kit component provides
true plug and play
dynamic device management
dynamic (“on-demand”) loading of drivers
power management for desktop systems as well as portables
multiprocessor capabilities
