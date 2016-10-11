// enable Nested Virtualization  
Set-VMProcessor -VMName "win10_x86" -ExposeVirtualizationExtensions $true

// disable Nested Virtualization  
Set-VMProcessor -VMName "win10_x86" -ExposeVirtualizationExtensions $false



netsh int ip set global taskoffload=disabled
netsh int tcp set global RSS=disabled
netsh interface tcp set global autotuninglevel=disabled
netsh int tcp set global chimney=disabled