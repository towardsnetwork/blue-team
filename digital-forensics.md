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
- View hidden process(process has 'False' listed) `volatility -f MEMORY_FILE.raw --profile=WinXPSP2x86 psxview`
- Hidden process `ldrmodules` 3 columns middle, InLoad, InInit, InMem. If any of these are false, that module has likely been injected
- View unexpected patches in the standard system DLLs `apihooks` 
- View/Dump injected code `volatility -f cridex.vmem --profile=WinXPSP2x86 malfind -D /tmp` (-D is destination)
- List all of the DLLs in memory `dlllist`
- Dump DLLs in memory `--pid=PID dlldump -D <Destination Directory>`
- Upload files or Sha256 sum the DLLs and search the hashes in virustotal etc.
- 

Practice | Tutorials
- Cyberdefenders DumpMe [https://cyberdefenders.org/labs/65](https://cyberdefenders.org/labs/65)
- Tryhackme [https://tryhackme.com/room/bpvolatility](https://tryhackme.com/room/bpvolatility)
- [Memory Forensics with Vol(a|u)tility talk](https://www.youtube.com/watch?v=dB5852eAgpc)

## Windows forensics
- Check windows Task scheduler
- 
Tryhackme room [investigatingwindows](https://tryhackme.com/room/investigatingwindows), read this [https://markonsecurity.medium.com/investigating-windows-tryhackme-10e187badedb](https://markonsecurity.medium.com/investigating-windows-tryhackme-10e187badedb)
