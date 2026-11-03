# H2 — Scene

## a) Podcast: SANS Internet Stormcenter Stormcast

**Episode:** October 15, 2026, hosted by Johannes Ullrich  
**Source:** https://isc.sans.edu/podcastdetail/10138

### Summary

- **AutoCAD:** DWG files can contain VBA macros, just like Microsoft Office documents. Didier Stevens found that some VBA projects remained inside DWG files even after their references had been removed. They were no longer active, but their code could still be extracted.
- **Ledger:** Some hardware cryptocurrency wallets reportedly contained malicious LTE modules and SIM cards designed to steal recovery seed phrases.
- **Docker Hub:** A bug in converting personal accounts into organizations could transfer access tokens in an unsafe way, allowing an attacker to impersonate another user. Docker fixed the issue.
- **curl:** An update fixed an HTTP/2 file-upload vulnerability that could allow a malicious server to execute code on the client.

### My thoughts

I was particularly interested in the AutoCAD story. At my previous job, I worked quite a lot with AutoCAD drawings, although I am not a designer and do not know all the details of the software. I did not realize that DWG files could contain potentially malicious VBA scripts, just like Excel files. It was also interesting that removing a reference to a script does not necessarily remove the script itself from the file.

## b) Blog: Cyberattack on Connected Fridges in France

**Author:** Bruce Schneier  
**Published:** October 14, 2026  
**Source:** https://www.schneier.com/blog/archives/2026/10/cyberattack-on-connected-fridges-in-france.html

### Summary

- Attackers gained control of refrigeration systems in supermarkets and changed their temperature settings. Some units reportedly heated up, putting refrigerated food at risk.
- Some affected controllers were older models that could no longer receive security updates.
- The discussion raised questions about exposing management interfaces to the Internet and about network security around IoT devices. The exact method used in this attack was not confirmed in the post.
- This is an example of a cyberattack causing physical consequences and economic damage, not just a data breach.

### My thoughts

- An attack does not always need to bring the attacker direct financial profit. Sometimes it is vandalism or an attempt to cause economic damage. We should be prepared for these risks even when a device seems unimportant.
- Even an ordinary connected refrigerator needs basic network protection: no openly exposed management interface, restricted access, a firewall, VPN or network segmentation where appropriate, and firmware updates when available. The same principles should apply to all network-connected equipment.

## c) Science That: From PBXs to IoT Security

The refrigerator story reminded me of how telephone systems moved from dedicated lines to IP networks. Traditional corporate PBXs, such as Avaya DEFINITY, Panasonic KX-TDA and Samsung OfficeServ, often used E1 lines with ISDN PRI signaling. Later, voice and signaling increasingly moved to IP networks, using technologies such as H.323 and SIP. This was much easier and often cheaper to connect than arranging dedicated telephone circuits.

But IP connectivity also brought new security problems. Some PBX systems gained IP capabilities without security being a priority, and administrators sometimes connected them to the Internet without enough protection. SIP can be protected with TLS, but unencrypted signaling is still used in some installations. Exposing such systems without proper access controls creates opportunities for abuse, including SIP toll fraud: attackers use compromised telephone systems to make expensive calls at someone else's expense.

This connects to the H1 scientific review, *Telecom spam and scams in the 5G and artificial intelligence era* (Pietri et al., 2025), which discusses security weaknesses and fraud in modern telecommunications. The same general problem appears in the refrigerator attack: equipment built for a specific physical task becomes connected to IP networks, but security does not always keep up. In my opinion, we need to protect not only servers and computers but also PBXs, cameras, refrigerators, smart kettles and any other network-connected devices.

**H1 article:** https://doi.org/10.1007/s10207-025-01062-8


## d) Download Debian

Downloaded Debian 13.7 (Trixie) Live Xfce amd64 from the official Debian website.

## e) Bonus: Install Debian on a Virtual Machine

Installed Debian 13.7 with Xfce in Oracle VirtualBox on Windows 10.

VM configuration:
- RAM: 3072 MB
- CPUs: 2
- Virtual disk: 30 GB
- Network: NAT

I also installed VirtualBox Guest Additions to enable shared clipboard support.

### Verification

```console
$ cat /etc/os-release
PRETTY_NAME="Debian GNU/Linux 13 (trixie)"
VERSION_ID="13"
DEBIAN_VERSION_FULL=13.7

$ uname -a
Linux anna-virtualbox 6.12.115+deb13.1-amd64 #1 SMP PREEMPT_DYNAMIC Debian 6.12.115-2 (2026-11-01) x86_64 GNU/Linux

$ systemd-detect-virt
oracle

$ lsblk -o NAME,SIZE,TYPE,MOUNTPOINTS
NAME    SIZE TYPE MOUNTPOINTS
sda      30G disk
├─sda1  300M part /boot/efi
├─sda2 23,3G part /
└─sda3  6,4G part [SWAP]
sr0    50,7M rom
```

