WINDBG>!js fnid.js
===========================
win32kfull!mpFnidPfn = 0x9f6a0248  
when uMsg >= 0x400 or win32kfull!NtUserfnDWORD == gapfnMessageCall[MessageTable[uMsg]]

|fnid|name|fnIndex|mpFnidPfn
|----|----|----|----
|0x29A|FNID_FIRST|0x00|win32kfull!xxxWrapSBWndProc
|0x29A|FNID_SCROLLBAR|0x00|win32kfull!xxxWrapSBWndProc
|0x29B|FNID_ICONTITLE|0x01|win32kfull!xxxWrapRealDefWindowProc
|0x29C|FNID_MENU|0x02|win32kfull!xxxWrapMenuWindowProc
|0x29D|FNID_DESKTOP|0x03|win32kfull!xxxWrapDesktopWndProc
|0x29E|FNID_DEFWINDOWPROC|0x04|win32kfull!xxxWrapRealDefWindowProc
|0x29F|FNID_MESSAGEWND|0x05|win32kfull!xxxWrapRealDefWindowProc
|0x2A0|FNID_SWITCH|0x06|win32kfull!xxxWrapSwitchWndProc
|0x2A1|FNID_BUTTON|0x07|win32kfull!xxxUnusedFunctionId
|0x2A2|FNID_COMBOBOX|0x08|win32kfull!xxxUnusedFunctionId
|0x2A3|FNID_COMBOLBOX|0x09|win32kfull!xxxUnusedFunctionId
|0x2A4|FNID_DIALOG|0x0A|win32kfull!xxxUnusedFunctionId
|0x2A5|FNID_EDIT|0x0B|win32kfull!xxxUnusedFunctionId
|0x2A6|FNID_LISTBOX|0x0C|win32kfull!xxxUnusedFunctionId
|0x2A7|FNID_MDICLIENT|0x0D|win32kfull!xxxUnusedFunctionId
|0x2A8|FNID_STATIC|0x0E|win32kfull!xxxUnusedFunctionId
|0x2A9|FNID_IME|0x0F|win32kfull!xxxUnusedFunctionId
|0x2AA|FNID_GHOST|0x10|win32kfull!xxxUnusedFunctionId
|0x2AB|FNID_CALLWNDPROC|0x11|win32kfull!fnHkINLPCWPEXSTRUCT
|0x2AC|FNID_CALLWNDPROCRET|0x12|win32kfull!fnHkINLPCWPRETEXSTRUCT
|0x2AD|FNID_HKINLPCWPEXSTRUCT|0x13|win32kfull!xxxUnusedFunctionId
|0x2AE|FNID_HKINLPCWPRETEXSTRUCT|0x14|win32kfull!xxxUnusedFunctionId
|0x2AF|FNID_MB_DLGPROC|0x15|win32kfull!xxxUnusedFunctionId
|0x2B0|FNID_MDIACTIVATEDLGPROC|0x16|win32kfull!xxxUnusedFunctionId
|0x2B1|FNID_SENDMESSAGE|0x17|win32kfull!xxxWrapSendMessage
|0x2B2|FNID_SENDMESSAGEFF|0x18|win32kfull!xxxSendMessageFF
|0x2B3|FNID_SENDMESSAGEWTOOPTION|0x19|win32kfull!xxxSendMessageEx
|0x2B4|FNID_SENDMESSAGECALLPROC|0x1A|win32kfull!xxxWrapCallWindowProc
|0x2B5|FNID_BROADCASTSYSTEMMESSAGE|0x1B|win32kfull!xxxWrapSendMessageBSM
|0x2B6|FNID_TOOLTIPS|0x1C|win32kfull!xxxUnusedFunctionId
|0x2B7|FNID_SENDNOTIFYMESSAGE|0x1D|win32kfull!xxxWrapSendNotifyMessage
|0x2B8|FNID_SENDMESSAGECALLBACK|0x1E|win32kfull!xxxWrapSendMessageCallback
|0x2B9|FNID_LAST|0x1F|win32kfull!xxxUnusedFunctionId
|0x2000|FNID_DDEML|0x06|win32kfull!xxxWrapSwitchWndProc
|0x4000|FNID_DESTROY|0x06|win32kfull!xxxWrapSwitchWndProc
|0x8000|FNID_FREED|0x06|win32kfull!xxxWrapSwitchWndProc