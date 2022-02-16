<h1 align="center">WireGuard-Manager 👋</h1>
<p align="center">
	<a href="https://github.com/complexorganizations/wireguard-manager/releases">
		<img alt="Release" src="https://img.shields.io/github/v/release/complexorganizations/wireguard-manager" target="_blank" />
	</a>
	<a href="https://github.com/complexorganizations/wireguard-manager/actions">
		<img alt="ShellCheck" src="https://github.com/complexorganizations/wireguard-manager/workflows/ShellCheck/badge.svg" target="_blank" />
	</a>
	<a href="https://github.com/complexorganizations/wireguard-manager/issues">
		<img alt="Issues" src="https://img.shields.io/github/issues/complexorganizations/wireguard-manager" target="_blank" />
	</a>
	<a href="https://github.com/sponsors/Prajwal-Koirala">
		<img alt="Sponsors" src="https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub" target="_blank" />
	</a>
	<a href="https://github.com/complexorganizations/wireguard-manager/pulls">
		<img alt="PullRequest" src="https://img.shields.io/github/issues-pr/complexorganizations/wireguard-manager" target="_blank" />
	</a>
	<a href="https://raw.githubusercontent.com/complexorganizations/wireguard-manager/main/.github/LICENSE">
		<img alt="License" src="https://img.shields.io/github/license/complexorganizations/wireguard-manager" target="_blank" />
	</a>
</p>

---
### 🤷 What is VPN ?
A Virtual Private Network (VPN) allows users to send and receive data through shared or public networks as if their computing devices were directly connected to the private network. Thus, applications running on an end-system (PC, smartphone, etc.) over a VPN may benefit from individual network features, protection, and management. Encryption is a standard aspect of a VPN connection but not an intrinsic one.

### 📶 What is WireGuard❓
WireGuard is a straightforward yet fast and modern VPN that utilizes state-of-the-art cryptography. It aims to be faster, simpler, leaner, and more useful than IPsec while avoiding the massive headache. It intends to be considerably more performant than OpenVPN. WireGuard is designed as a general-purpose VPN for running on embedded interfaces and super computers alike, fit for many circumstances. Initially released for the Linux kernel, it is now cross-platform (Windows, macOS, BSD, iOS, Android) and widely deployable. It is currently under a massive development, but it already might be regarded as the most secure, most comfortable to use, and the simplest VPN solution in the industry.

### ⛳ Goals
 - robust and modern security by default
 - minimal config and critical management
 - fast, both low-latency and high-bandwidth
 - simple internals and small protocol surface area
 - simple CLI and seamless integration with system networking

---
### 🌲 Prerequisite
- CentOS, Debian, Ubuntu, Arch, Fedora, Redhat, Raspbian, PopOS, Manjaro, Kali, Alpine, Mint, FreeBSD, Neon, Alma, Rocky
- Linux `Kernel 3.1` or newer
- You will need superuser access or a user account with `sudo` privilege.

---
### 🐧 Installation
Lets first use `curl` and save the file in `/usr/local/bin/`
```
curl https://raw.githubusercontent.com/complexorganizations/wireguard-manager/main/wireguard-manager.sh --create-dirs -o /usr/local/bin/wireguard-manager.sh
```
Then let's make the script user executable
```
chmod +x /usr/local/bin/wireguard-manager.sh
```
It's finally time to execute the script
```
bash /usr/local/bin/wireguard-manager.sh
```

In your `/etc/wireguard/clients` directory, you will have `.conf` files. These are the peer configuration files. Download them from your WireGuard Interface and connect using your favorite WireGuard Peer.

---
### 💣 After Installation
- Show WireGuard Interface
- Start WireGuard Interface
- Stop WireGuard Interface
- Restart WireGuard Interface
- Add WireGuard Peer
- Remove WireGuard Peer
- Uninstall WireGuard Interface
- Update this script
- Encrypt & Backup Configs
- Restore WireGuard Configs

---
### 🔑 Usage
```
usage: ./wireguard-manager.sh <command>
  --install     Install WireGuard
  --start       Start WireGuard
  --stop        Stop WireGuard
  --restart     Restart WireGuard
  --list        Show WireGuard
  --add         Add WireGuard Peer
  --remove      Remove WireGuard Peer
  --reinstall   Reinstall WireGuard
  --uninstall   Uninstall WireGuard
  --update      Update WireGuard Manager
  --ddns        Update WireGuard IP Address
  --backup      Backup WireGuard
  --restore     Restore WireGuard
  --purge       Purge WireGuard Peer(s)
  --help        Show Usage Guide
```

---
### 🥰 Features
- Install & Configure WireGuard Interface
- Backup & Restore WireGuard
- Expiration of peer configurations on autopilot
- (IPv4|IPv6) Supported, Leak Protection
- Variety of Public DNS to be pushed to the peers
- Choice to use a self-hosted resolver with Unbound **Prevent DNS Leaks, DNSSEC Supported**
- Iptables rules and forwarding managed in a seamless way
- Remove & Uninstall WireGuard Interface
- Preshared-key for an extra layer of security. **Required**
- Many other little things!

---
### 💡 Options
* `PRIVATE_SUBNET_V4` - By default, the private IPv4 subnet configuration is `10.0.0.0/8`.
* `PRIVATE_SUBNET_V6` - `fd00:00:00::0/8` is the default private IPv6 subnet.
* `SERVER_HOST_V4` - Curl detects a public IPv4 address by default.
* `SERVER_HOST_V6` - Curl by default finds a public IPv6 address.
* `SERVER_PUB_NIC` - Using the ip command, to find the local public network interface.
* `SERVER_PORT` - `51820` is the default public port for the wireguard interface.
* `DISABLE_HOST` - Determine whether or not IPv4 or IPv6 should be disabled.
* `CLIENT_ALLOWED_IP` - Using an IP range, choose what should be sent to the VPN.
* `NAT_CHOICE` - Determine whether or not to use the vpn tunnel's keep alive feature.
* `INSTALL_UNBOUND` - Whether or not to install unbound is up to you.
* `UNINSTALL_UNBOUND` - If you need to remove Unbound for whatever reason, you can do so.
* `REMOVE_WIREGUARD` - It is entirely up to you whether or not to remove wireguard altogether.
* `DNS_CHOICE` - You'll have to utilize another DNS if you don't have Unbound.
* `CLIENT_NAME` - The wireguard peer's name.
* `MTU_CHOICE` - The wireguard peers will utilize this MTU.

---
### 👉👈 Compatibility with Linux Distro
| OS              | i386               | amd64              | armhf              | arm64              |
| --------------  | ------------------ | ------------------ | ------------------ | ------------------ |
| Ubuntu 14 ≤     |:x:                 |:x:                 |:x:                 |:x:                 |
| Ubuntu 16 ≥     |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Debian 7 ≤      |:x:                 |:x:                 |:x:                 |:x:                 |
| Debian 8 ≥      |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| CentOS 6 ≤      |:x:                 |:x:                 |:x:                 |:x:                 |
| CentOS 7 ≥      |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Fedora 29 ≤     |:x:                 |:x:                 |:x:                 |:x:                 |
| Fedora 30 ≥     |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| RedHat 6 ≤      |:x:                 |:x:                 |:x:                 |:x:                 |
| RedHat 7 ≥      |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Kali 1.0 ≤      |:x:                 |:x:                 |:x:                 |:x:                 |
| Kali 1.1 ≥      |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Arch            |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Raspbian        |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| PopOS           |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Manjaro         |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Mint            |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Alma            |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Alpine          |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| FreeBSD         |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Neon            |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |
| Rocky           |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |:heavy_check_mark:  |

### ☁️ Compatibility with Cloud Providers
| Cloud           | Supported          |
| --------------  | ------------------ |
| AWS             |:heavy_check_mark:  |
| Google Cloud    |:heavy_check_mark:  |
| Linode          |:heavy_check_mark:  |
| Digital Ocean   |:heavy_check_mark:  |
| Vultr           |:heavy_check_mark:  |
| Microsoft Azure |:heavy_check_mark:  |
| OpenStack       |:heavy_check_mark:  |
| Rackspace       |:heavy_check_mark:  |
| Scaleway        |:heavy_check_mark:  |
| EuroVPS         |:heavy_check_mark:  |
| Hetzner Cloud   |:x:                 |
| Strato          |:x:                 |

### 🛡️ Compatibility with Virtualization
| Virtualization  | Supported          |
| --------------  | ------------------ |
| KVM             |:heavy_check_mark:  |
| None            |:heavy_check_mark:  |
| Qemu            |:heavy_check_mark:  |
| LXC             |:heavy_check_mark:  |
| Microsoft       |:heavy_check_mark:  |
| OpenVZ          |:x:                 |
| Docker          |:x:                 |

### 💻 Compatibility with Linux Kernel
| Kernel                 | Supported              |
| ---------------------  | ---------------------  |
| Linux Kernel 3.0 ≤     |:x:                     |
| Linux Kernel 3.1 ≥     |:heavy_check_mark:      |

---
### 🙋 Q&A
Which hosting provider do you recommend?
- [VirMach](https://virmach.com/): Worldwide locations, IPv4 & IPv6 support, starting at $1.00/month
- [Vultr](https://www.vultr.com/?ref=8586251-6G): Worldwide locations, IPv4 & IPv6 support, starting at $3.50/month
- [Digital Ocean](https://m.do.co/c/fb46acb2b3b1): Worldwide locations, IPv4 & IPv6 support, starting at $5/month
- [Linode](https://www.linode.com): Worldwide locations, IPv4 & IPv6 support, starting at $5/month
- [Google Cloud](https://gcpsignup.page.link/H9XL): Worldwide locations, IPv4 support, starting at $3.50/month

Which WireGuard client do you recommend?
- Windows: [WireGuard](https://www.wireguard.com/install/).
- Android: [WireGuard](https://play.google.com/store/apps/details?id=com.wireguard.android).
- macOS: [WireGuard](https://itunes.apple.com/us/app/wireguard/id1451685025).
- iOS: [WireGuard](https://itunes.apple.com/us/app/wireguard/id1441195209).

Is there WireGuard documentation?
- Yes, please head to the [WireGuard Manual](https://www.wireguard.com), which references all the options.

How do I install a wireguard without the questions? (Headless Install)
- ```./wireguard-manager.sh --install```

Are there any good alternative to self-hosting vpn?
- [CloudFlare Warp](https://1.1.1.1/)

Why is all the code in one place?
- Consider a remote control, you can have thirty different remotes each doing a different job, or you may have a single remote that does everything.

Which port do I need to forward for wireguard, and which protocol should I use?
- On the udp protocol, either the port of your choice or the default port of `51820` must be forwarded.

For unbound, which ports do I need to forward?
- Because all DNS traffic is routed through the vpn, you don't need to forward those ports `53`.

What is blocked if I enable the content blocker?
- Advertisement, Tracking, malware, and phishing are all prohibited.

What kind of information is collected and how is it gathered?
- We do not collect or retain any logs; everything takes place on the system, and logs are never sent outside of it.

Official Links
- Homepage: https://www.wireguard.com
- Install: https://www.wireguard.com/install/
- QuickStart: https://www.wireguard.com/quickstart/
- Compiling: https://www.wireguard.com/compilation/
- Whitepaper: https://www.wireguard.com/papers/wireguard.pdf

---
### 🙅 No Content-Blocking vs. Content-Blocking
https://user-images.githubusercontent.com/16564273/125283630-9845d180-e2e6-11eb-8b7d-f30a8f2eae8a.mp4

---
### 📐 Architecture
![image](https://raw.githubusercontent.com/complexorganizations/wireguard-manager/main/assets/Wireguard-Manager.png)

---
### 🤝 Developing
Developing the code without having to clone the repository

[![Open in Visual Studio Code](https://open.vscode.dev/badges/open-in-vscode.svg)](https://open.vscode.dev/complexorganizations/wireguard-manager)

### 🐛 Debugging
After cloning the repo, Then start debugging the code.

```
git clone https://github.com/complexorganizations/wireguard-manager /usr/local/bin/
bash -x /usr/local/bin/wireguard-manager.sh >> /usr/local/bin/wireguard-manager.log
```

---
### 👤 Author
* Name: Prajwal Koirala
* Website: [prajwalkoirala.com](https://www.prajwalkoirala.com)
* Github: [@prajwal-koirala](https://github.com/prajwal-koirala)
* LinkedIn: [@prajwal-koirala](https://www.linkedin.com/in/prajwal-koirala)
* Twitter: [@Prajwal_K23](https://twitter.com/Prajwal_K23)
* Reddit: [@prajwalkoirala23](https://www.reddit.com/user/prajwalkoirala23)
* Twitch: [@prajwalkoirala23](https://www.twitch.tv/prajwalkoirala23)

---
### ⛑️ Support
Give a ⭐️ and 🍴 if this project helped you!

<p align="center">
	<a href="https://github.com/sponsors/Prajwal-Koirala">
		<img alt="Sponsors" src="https://img.shields.io/static/v1?label=Sponsor&message=%E2%9D%A4&logo=GitHub" target="_blank" />
	</a>
</p>

- Monero : `86uFC3LEfQi73rCS2tq6N2YKckbcyvKMCiJKSXEcLyYVW19nHiL9ec2FfaY3iAQEwhSxC7mTEGiFaVbHywirDi4rJjtczfH`
- Ethereum : ``

---
### ❤️ Credits
Open Source Community

---
### 🤝 Sponsors
<table>
  <tbody>
    <tr>
      <td align="center" valign="middle">
        <a href="https://m.do.co/c/fb46acb2b3b1" target="_blank">
          <img width="200px" src="https://raw.githubusercontent.com/complexorganizations/wireguard-manager/main/assets/digitalocean.png">
        </a>
      </td>
      </td>
    </tr><tr></tr>
  </tbody>
</table>

---
### 📝 License
Copyright © 2020 [Prajwal](https://github.com/prajwal-koirala)

[Apache License Version 2.0](https://raw.githubusercontent.com/complexorganizations/wireguard-manager/main/.github/LICENSE)
