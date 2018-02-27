# DL ISO-8583 Library

- v0.0.4 - 16th July 2008
- v0.0.3 - 14th October 2007
- v0.0.2 - 3rd September 2007
- v0.0.1 - 28th August 2007

## CONTENTS

This package contains the following source code files:

  - demo.c

      Demo application source, with message packing/unpacking example

  - benchmark.c
  
      Benchmark source, to benchmark pack/unpack operations

  - dl_c_iso8583

      DL ISO-8583 library source files

  - dl_c_common

      DL Common source files (used by DL ISO-8583)

  - benchmark / demo
  
      Sample MSVC 6.0 project files

## COMPILATION

Simply compile all the provided source code to run the demo application, from
there you can easily integrate the DL ISO-8583 library into other projects.

If using MSVC 6.0 then simply open the applicable DSW file.

## CHANGE HISTORY

This version includes the following changes:

  [Bug-fix] Fixed issue in 'VarLen_Get' (dl_iso8583_fields.c) which resulted in
            the length being incorrectly determined (during unpack) for any
            variable length field with a length equal to or exeeding 100

## BUGS / SUGGESTIONS

Please email any bugs or suggestions to 'o.sanderson@gmail.com'.

## [Introduction Blog post](http://www.oscarsanderson.com/iso-8583/)

### Background

ISO 8583 is a messaging standard used for payment card originated financial transactions. At present there are three different versions of the standard, as follows:

1987 (used by Visa / MasterCard)
1993 (used by Amex)
2003
Each version is named based on the year that it was published.

Whilst ISO 8583 is an official standard, it is important to note that most implementations are derivatives and do not fully comply with the published standard, however the variations are typically minor and it is generally quite a trivial task to modify an existing ISO 8583 version handler to accommodate such variations.

### Overview

The DL ISO8583 library is available free of charge and with a very liberal (zlib style) license. The library is written in C and is designed to be suitable for use on a variety of systems (including embedded devices). It can be used in environments both with and without dynamic memory allocation.

The library supports multiple ISO 8583 message handlers, each of which can be specified at run-time by the client application. Existing ISO 8583 message handlers can be easily modified to support derivative implementations, as required.


## Notes by [Yazdan](https://github.com/yazdan)

I've add cmake build file. to use it just type:

        $ mkdir build
        $ cd build
        $ cmake ..
        $ make
