// enable Nested Virtualization  
Set-VMProcessor -VMName "win10_x86" -ExposeVirtualizationExtensions $true

// disable Nested Virtualization  
Set-VMProcessor -VMName "win10_x86" -ExposeVirtualizationExtensions $false



New-NetNat -Name NAT -InternalIPInterfaceAddressPrefix 192.168.30.0/24