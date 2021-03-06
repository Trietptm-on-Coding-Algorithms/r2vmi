# r2vmi

[![Join the chat at https://gitter.im/r2vmi/Lobby](https://badges.gitter.im/r2vmi/Lobby.svg)](https://gitter.im/r2vmi/Lobby?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

Radare2 VMI IO and debugger plugins.

These plugins allow you to debug remote process running in a VM, from the hypervisor-level,
leveraging _Virtual Machine Introspection_.

Based on `Libvmi` to access the VM memory and listen on hardware events.

What works:
- Intercept a process by name/PID
- Read the registers
- Single-step the process execution
- Set breakpoints
- Load Rekall symbols

# Demo

![R2VMI_DEMO](https://github.com/Wenzel/wenzel.github.io/raw/master/public/images/r2vmi_demo.gif)

# Requirements

- `Xen 4.6`
- [`libvmi`](http://libvmi.com/)
- `radare2`
- `pkg-config`

# Setup

    $ make
    $ make install

Note: if `pkgconfig` fails, you need to:

    export PKG_CONFIG_PATH=/usr/lib/pkgconfig

# Usage

You need a virtual machine configured on top of `Xen`, and a process name/pid to intercept

    $ r2 vmi://<vm_name>:<name/pid>

Example:

    $ r2 vmi://win7:firefox

