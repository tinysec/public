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
const printf = require('cprintf').printf;
const sprintf = require('cprintf').sprintf;

const ref = require('ref');
const ffi = require('ffi');
const ref_array = require('ref-array');
const ref_struct = require('ref-struct');
const ref_union = require('ref-union');
const ref_wchar = require('ref-wchar');

const HANDLE = ref.types.void;

var kernel32 = ffi.Library( 'kernel32.dll' ,
{
    // ULONG __stdcall GetLogicalDrives();
    'GetLogicalDrives' : [ 'ulong' , [] , {abi : ffi.FFI_STDCALL } , null ],

    // BOOL __stdcall CloseHandle(HANDLE hHandle);
    "CloseHandle" : [ 'int' , [ HANDLE ], { abi : ffi.FFI_STDCALL } , null ] ,
}
);

// Get Logical Drive Mask
var nDriveMask = kernel32.GetLogicalDrives();

```


