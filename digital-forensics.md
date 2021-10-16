# Digital Forensics

## Top tools for DF
1. FTK Imager
2. Volatility


## Volatility
1. Volatility is a free memory forensics tool for linux
2. FTK Imager can be used to obtaining a memory capture from machines
3. .raw format is one of the most common memory file type, VMware - .vmem, Hyper-V - .bin, Parallels - .mem, VirtualBox - .sav
4. hiberfil.sys, better known as the Windows hibernation file contains a compressed memory image from the previous boot.
- Get profiles we can use `volatility -f MEMORY_FILE.raw imageinfo`
- List process `volatility -f MEMORY_FILE.raw --profile=WinXPSP2x86 pslist`
- 

Practice at 
- Cyberdefenders DumpMe [https://cyberdefenders.org/labs/65](https://cyberdefenders.org/labs/65)
- Tryhackme [https://tryhackme.com/room/bpvolatility](https://tryhackme.com/room/bpvolatility)
