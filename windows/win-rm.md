---
description: 'Common port: 5985, 5986'
---

# 💾 Win RM

Windows Remote Management (WinRM) is the Microsoft implementation of [WS-Management Protocol](https://learn.microsoft.com/en-us/windows/win32/winrm/ws-management-protocol), a standard Simple Object Access Protocol (SOAP)-based, firewall-friendly protocol that allows hardware and operating systems, from different vendors, to interoperate.

The WS-Management protocol specification provides a common way for systems to access and exchange management information across an IT infrastructure. WinRM and [_Intelligent Platform Management Interface (IPMI)_](https://learn.microsoft.com/en-us/windows/win32/winrm/windows-remote-management-glossary#i), along with the [Event Collector](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc785056\(v=ws.10\)#event-collector) are components of the [Windows Hardware Management](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2003/cc785056\(v=ws.10\)) features.

## Exploiting

If you have identified winrm and have the credentials necessary then use evil winrm to get a shell. Use the docker version as the openssl on ubuntu 22 and macos no longer supports the encryption method that it uses.&#x20;

{% embed url="https://github.com/Hackplayers/evil-winrm" %}

For a better guide see:

{% embed url="https://book.hacktricks.xyz/network-services-pentesting/5985-5986-pentesting-winrm#winrm" %}

### Common command for HTB.

{% code overflow="wrap" %}
```bash
docker run --rm -ti --name evil-winrm -v /home/lyr4/windows/ps1_scripts:/ps1_scripts -v /home/lyr4/windows/exe_files:/exe_files -v /home/foo/data:/data oscarakaelvis/evil-winrm -i '<ip>' -u support -p '<password>' -s '/ps1_scripts/' -e '/exe_files/'
```
{% endcode %}

