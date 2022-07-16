# openssl-3.0.5-win64-VS2019
Compiled binaries of OpenSSL 3.0.5 for Windows x64 with Visual Studio 2019

These binaries were compiled with:
  - NASM version 2.15.05 compiled on Aug 28 2020
  - Strawberry Perl 5.32.1.1-64bit
  - Microsoft Visual Studio Professional 2019 Version 16.11.3


The following step by step was used to compile the binaries:

Native builds using Visual C++
==============================

The native builds using Visual C++ have a `VC-*` prefix.

Requirement details
-------------------

In addition to the requirements and instructions listed in `INSTALL.md`,
these are required as well:

### Perl

We recommend Strawberry Perl, available from <http://strawberryperl.com/>
Please read NOTES.PERL for more information, including the use of CPAN.
An alternative is ActiveState Perl, <https://www.activestate.com/ActivePerl>
for which you may need to explicitly build the Perl module Win32/Console.pm
via <https://platform.activestate.com/ActiveState> and then download it.

### Microsoft Visual C compiler.

Since these are proprietary and ever-changing we cannot test them all.
Older versions may not work. Use a recent version wherever possible.

### Netwide Assembler (NASM)

NASM is the only supported assembler. It is available from <https://www.nasm.us>.

Quick start
-----------

 1. Install Perl

 2. Install NASM

 3. Make sure both Perl and NASM are on your %PATH%

 4. Use Visual Studio Developer Command Prompt with administrative privileges,
    choosing one of its variants depending on the intended architecture.
    Or run `cmd` and execute `vcvarsall.bat` with one of the options `x86`,
    `x86_amd64`, `x86_arm`, `x86_arm64`, `amd64`, `amd64_x86`, `amd64_arm`,
    or `amd64_arm64`.
    This sets up the environment variables needed for `nmake.exe`, `cl.exe`,
    etc.
    See also
    <https://docs.microsoft.com/cpp/build/building-on-the-command-line>

 5. From the root of the OpenSSL source directory enter
    - `perl Configure VC-WIN32`     if you want 32-bit OpenSSL or
    - `perl Configure VC-WIN64A`    if you want 64-bit OpenSSL or
    - `perl Configure VC-WIN64-ARM` if you want Windows on Arm (win-arm64)
       OpenSSL or
    - `perl Configure`              to let Configure figure out the platform

 6. `nmake`

 7. `nmake test`

 8. `nmake install`
