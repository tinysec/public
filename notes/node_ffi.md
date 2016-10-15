# ffi fast reference

```javascript
ffi.Library(libraryFile, { functionSymbol: [ returnType, [ arg1Type, arg2Type, ... ], [option] ] , [lib] } );
```
option list
 * abi  
     * ffi.FFI_DEFAULT_ABI	means __cdcel
     * ffi.FFI_STDCALL means __stdcall
     * ffi.FFI_THISCALL means __thiscall
     * ffi.FFI_FASTCALL means __fastcall
     * 
 * async 
 * varargs 

returnType
* int8 uint8 byte char uchar
* int16 uint16 short ushort

usage
```javascript
var ref = require('ref');
var ffi = require('ffi');
var ref_array = require('ref-array');
var ref_struct = require('ref-struct');
var ref_union = require('ref-union');
var ref_wchar = require('ref-wchar');


var HANDLE = ref.types.void;

ffi.Library(

// ULONG __stdcall GetLogicalDrives();
'GetLogicalDrives' : [ 'ulong' , [] , {abi : ffi.FFI_STDCALL } ],

// BOOL __stdcall CloseHandle(HANDLE hHandle);
'kernel32.dll', { "CloseHandle" : [ 'int' , [HANDLE], { abi : ffi.FFI_STDCALL } ] }
);
```


