# Introduction #

Tools and libraries you need:
  * a compiler (for now, MS Visual Studio 2008/2010 will do)
  * [Subversion](http://subversion.tigris.org/getting.html#windows), TortoiseSVN or any other Subversion client
    * [AnkhSVN](http://ankhsvn.net/downloads/2.1/) Visual Studio Subversion integration _(optional)_
  * [Boost](http://www.boost.org/users/download/)
  * [Debugging Tools for Windows](http://www.microsoft.com/whdc/DevTools/Debugging/default.mspx)
  * [WDK](http://www.microsoft.com/whdc/DevTools/WDK/WDKpkg.mspx)
GUI (wxWidgets):
  * [wxWidgets](http://www.wxwidgets.org/downloads/)
GUI (Qt):
  * [Qt](http://qt.nokia.com/products/)

# Details #

The following environment variables should be defined:
|**Variable**|**Example**|
|:-----------|:----------|
|BOOST\_ROOT |C:\Program Files\boost\boost\_1\_49\_0|
|DbgToolsSDK |C:\Program Files\Debugging Tools for Windows (x86)\sdk|
|WINDDK      |C:\WinDDK\7600.16385.0|
|WXWIN       |C:\wxWidgets-2.8.12|
|QTDIR       |C:\Qt\2009.03\Qt|
|PATH        |%PATH%;C:\Qt\2009.03\Qt|

Additional path for Visual Studio should be added. Open Tools->Options->Projects and Solutions\VC++ Directories, choose Platform:Win32, Show directories for:Include files, then add the following line:

$(WXWIN)\include\msvc

Then select Show directories for:Library files and add the following line:

$(BOOST\_ROOT)\stage\lib


Then open Visual Studio Command Prompt and do the following
```
$ svn checkout https://opendbg.googlecode.com/svn/branches/minidbg opendbg
$ devenv /Build Release opendbg\prj\vs100\opendbg.sln
```
If everything is ok, you are ready to go.