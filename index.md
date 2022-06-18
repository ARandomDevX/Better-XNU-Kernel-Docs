## Better XNU Docs
Better XNU kernel docs (Don't use, them yet).

We aim to make understanding the XNU kernel, or generally kernels, easier, by simplifying documentation.

### 1. Introduction
#### Who should read this guide?
This guide is intended for:
 * Device driver developers
 * Network extension developers
 * People coming from different kernel backgrounds

We assume you know key programming concepts and have at least a basic knowledge of C++ since OSX uses a restricted form of it.

#### Avoid unnecessary interactions with the Kernelspace
The kernel is the "heart" of an operating system. Avoid writing unnecessary device drivers to prevent crashes. If the kernel crashes, the system crashes. However, if an application crashes in the userspace, the error can be mitigated quickly. Even most device drivers (ex. USB) can be written in the Userspace itself.

Next off, An Architectural overview of the Kernel
