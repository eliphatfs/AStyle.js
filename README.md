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
