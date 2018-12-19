# AStyle.js
### Astyle Code Formatter & Beautifier for C++ within just one js.
-----

## Installation
1. Download the javascript file from the [release page](https://github.com/strongrex2001/AStyle.js/releases).  
2. Include the file in the web page where you want to use AStyle to format codes. For Example:  
```html
<script language="javascript" src="AStyle_v0.3.js"></script>
```  
3. Call the formatter somewhere else in your js code.  

## Usage
High Level API:  
```javascript
/**
 * @param code - Source code, string
 * @param style - allman / bsd / break / java / attach / kr
 *                / stroustrup / whitesmith / vtk / ratliff / gnu / linux
 *                / horstmann / 1tbs / google / mozilla / pico / lisp
 *                @see http://astyle.sourceforge.net/astyle.html#_Basic_Brace_Styles
 * @param indent - count of a layer of indent, between 2 and 20.
 * @param lang - 0 for C/CPP/Objective-C, 1 for C#, 2 for Java
 * @returns Formatted Code.
 *
 * Supports: C, C++, Java, C#, Objective-C
 */
function beautify(code, style, indent, lang);
```  
Low Level API:  
```javascript
astyle_instance.ccall("process", "string", ["string", "string", "string", "string"], [param1, param2, param3, param4])
```  
Where param1..4 are command-line parameters. Accepts the same as those in AStyle itself.  

## Working with Source
*Work on the AStyle Core is not discussed here.*  
The modified part and also the export logic is at the very bottom of `astyle_main.cpp`, where you can preprocess the parameters you want to pass from javascript code according to Emscripten and AStyle specifications.  
Building the code is quite easy. Just get Emscripten ready and run this command:  
```bash
<path to python2.exe> <path to emcc.py> --emscripten-cxx ASFormatter.cpp ASLocalizer.cpp ASResource.cpp astyle_main.cpp ASBeautifier.cpp ASEnhancer.cpp -std=c++11 -O3 -s INLINING_LIMIT=1 --memory-init-file 0 -s MODULARIZE=1 -s EXPORT_NAME='AStyle'
```  
The release is built under windows with clang as the frontend.  
