# Avalanche Studios Programming Test

## Assignment

The provided application shows a bunch of small geometric shapes that bounce around and
 also gravitate towards each other. The supplied default implementation works fine for small
 numbers of shapes, but as soon as the numbers increase the application gets bogged down
 by poor performance.

Your job is to **modify the default implementation so that it performs significantly better
 in terms of speed and the number of shape objects it can handle.** The functionality has
 to remain the same.

Since hardware performance varies we have provided an optimised reference
 implementation you can measure your own implementation against. This implementation
 does not use multithreading, SIMD instructions or assembly level optimisations.

**At 30000 objects, solutions more than 10 times slower than the reference
 implementation will not be considered.**

The framework supports multiple implementations simultaneously though a factory function,
so that you conveniently can compare different approaches. Look in Framework.h for some
other prerequisites to take advantage of.

## Memory

Keep your eyes on the memory used. Try to stay within a similar memory footprint as the
 reference implementation. We have overloaded the new operators to track and display
 memory usage through those. Avoid allocating static memory as that won’t show. You are
 free to use as much stack allocated memory as you wish as long as you keep within the
 compiler’s default settings.

## Result and judgement criteria

The reference implementation is single threaded C/C++ and doesn’t use asm, simd intrisics,
 GPGPU, or anything like that. You are however free to do so if you wish. You are not
 required to meet or exceed the performance of the reference implementation. The reasoning
 behind the attempts made is equally important as the actual numbers reached. If you wish,
 you can provide multiple implementations that have different characteristics and strengths.
 Some things we will look for in a solution is performance, memory use, correctness, and
 stability over time.

## Installation

There are 3 supported platforms: Linux (Ubuntu 10.4), Mac OS X (10.6) and Windows There
 are scripts included for compiling the application for either platform and solution/project files
 for windows.

### Linux
The compile script (compile_linux.sh) uses g++ and links towards OpenGL and Glut
 (freeglut) and the included “libframework.so”. Was tested on Ubuntu 10.4 on a 64-bit machine.

### Max OSX

The compile script (compile_osx.sh) uses g++ and links towards OpenGL and Glut and the
 included “libframework_osx.a”. OpenGL and GLUT was installed using MacPorts. Was
 tested on OSX10.6 on a 64-bit machine.

### Windows

The windows version is tested with Windows 7 and Windows 10. The solution/project files
 were created using Visual C++ 2015. You can download Visual Studio Community free of
 charge from: https://www.visualstudio.com/downloads/

## Compilers and Libraries

The application uses OpenGL and GLUT and links with opengl32.lib and glut32.lib so you
 need to have that installed. (glut library files are included in this package)

### Other compilers

You are free to use any compiler you wish, but the reference implementation was compiled
 with Visual C++ 2015 using default settings for Release builds. This will probably give you
 the best implementation comparison as other compilers will optimize differently. If you use
 other compilers, don’t forget to add opengl32.lib and glut32.lib to your linking step. The
 framework also requires the character set not to be set to Unicode, which some compilers
 have as default.
