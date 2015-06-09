## Qt 5.3.1 minimal library

- No ICU (reduce size by 27.5 MB)
- only release version (no debug)

---

To build:

1. Download **base** Qt module from [qtbase-opensource-src-5.3.1.7z](http://download.qt.io/official_releases/qt/5.3/5.3.1/submodules/qtbase-opensource-src-5.3.1.7z).
2. Unpack to a folder without spaces in the path.
3. Add these paths to the Path environment variable (if unpacked to 'QtBase' folder):

        QtBase;
        QtBase/qtbase/bin

4. Create another empty dir anywhere (path without spaces).
5. Enter it through command line.
6. Run the command:

        configure -release -opensource -confirm-license -platform win32-g++ -opengl desktop -no-accessibility -no-icu -no-iconv -no-angle -no-rtti -no-dbus -no-sse2 -no-sse3 -no-ssse3 -no-sse4.1 -no-sse4.2 -no-avx -no-avx2 -no-openssl -no-fontconfig -no-qml-debug -no-freetype -no-style-windowsvista -nomake libs -nomake tools -nomake examples -nomake tests

7. Build the library:

        mingw32-make
    
(I used `mingw32-make` from [Qt5.3.1 with MinGW installation](http://download.qt.io/official_releases/qt/5.3/5.3.1/qt-opensource-windows-x86-mingw482_opengl-5.3.1.exe), but it should work with [MinGW 4.8.2](https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/4.8.2/threads-posix/dwarf/) separate compiler, didn't check)

8. After a long time of build the `bin` and `plugins` folders will contain all necessary minimal DLLs.
