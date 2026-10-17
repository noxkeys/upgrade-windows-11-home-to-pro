# How to Upgrade Windows 11 Home to Pro

A step-by-step guide to upgrading **Windows 11 Home to Windows 11 Pro** without reinstalling Windows or losing your files. It also works for **Windows 10 Home to Pro**.

Maintained by [Noxkeys](https://noxkeys.com/), an online store for genuine software licences. Corrections are welcome.

---

## Table of contents

- [Quick answer](#quick-answer)
- [Windows 11 Home vs Pro](#windows-11-home-vs-pro)
- [Do you need Pro?](#do-you-need-pro)
- [Before you upgrade](#before-you-upgrade)
- [Method 1: Upgrade with a Pro product key (recommended)](#method-1-upgrade-with-a-pro-product-key-recommended)
- [Method 2: Upgrade through the Microsoft Store](#method-2-upgrade-through-the-microsoft-store)
- [Method 3: Upgrade using the generic Pro key, then activate](#method-3-upgrade-using-the-generic-pro-key-then-activate)
- [Method 4: Upgrade from Command Prompt](#method-4-upgrade-from-command-prompt)
- [How to confirm the upgrade worked](#how-to-confirm-the-upgrade-worked)
- [Troubleshooting](#troubleshooting)
- [Where to get a Windows 11 Pro key](#where-to-get-a-windows-11-pro-key)
- [FAQ](#faq)
- [References](#references)

---

## Quick answer

1. Open **Settings → System → Activation**
2. Click **Change** next to *Change product key*
3. Enter a genuine **Windows 11 Pro** product key
4. Click **Start** and let Windows restart

Your files, apps and settings stay exactly as they were. The upgrade usually takes 5 to 10 minutes.

---

## Windows 11 Home vs Pro

| Feature                                   | Home                    | Pro                      |
| ----------------------------------------- | ----------------------- | ------------------------ |
| Device encryption                         | Yes (on supported PCs)  | Yes                      |
| **BitLocker** full-drive encryption       | No                      | Yes                      |
| **Remote Desktop** (connect *to* this PC) | No                      | Yes                      |
| **Hyper-V** virtual machines              | No                      | Yes                      |
| **Windows Sandbox**                       | No                      | Yes                      |
| **Group Policy Editor** (gpedit.msc)      | No                      | Yes                      |
| Join a company domain / Microsoft Entra ID | No                     | Yes                      |
| Windows Update for Business (delay updates) | No                    | Yes                      |
| Assigned Access (kiosk mode)              | No                      | Yes                      |
| Maximum RAM                               | 128 GB                  | 2 TB                     |
| Maximum CPU sockets                       | 1                       | 2                        |
| Local account setup during install        | Restricted              | Easier                   |

Everything in Home is also in Pro. Pro only **adds** features.

---

## Do you need Pro?

**Upgrade to Pro if you:**

- Want to encrypt your drives with **BitLocker** (laptops, business data)
- Need to connect to this PC remotely with **Remote Desktop**
- Run virtual machines with **Hyper-V**, or test software safely in **Windows Sandbox**
- Want to control updates and settings with **Group Policy**
- Need to join a work domain or Microsoft Entra ID
- Work as a developer, IT professional, freelancer or small business

**Home is enough if you** only browse, stream, study, game and use Office apps.

---

## Before you upgrade

- [ ] Windows 11 Home is **activated** (Microsoft requires this for Methods 1 and 2)
- [ ] You are signed in with an **administrator** account
- [ ] The PC is connected to the **internet**
- [ ] Pending **Windows Updates** are installed
- [ ] You have a genuine **Windows 11 Pro product key** (or will buy Pro from the Microsoft Store)
- [ ] Important files are backed up (recommended, though the upgrade keeps your data)

**Check your current edition:** go to *Settings → System → About* and look at **Edition** under *Windows specifications*.

---

## Method 1: Upgrade with a Pro product key (recommended)

This is the fastest and most common method.

1. Press **Win + I** to open Settings
2. Go to **System → Activation**
3. Click **Change** next to *Change product key*, and select **Yes** if User Account Control asks
4. Enter your **25-character Windows 11 Pro key** and click **Next**
5. Click **Start** to begin the upgrade
6. Windows restarts once or twice. Don't turn off the PC

When it's finished, Windows 11 Pro is installed and activated.

---

## Method 2: Upgrade through the Microsoft Store

1. Go to **Settings → System → Activation**
2. Expand **Upgrade your edition of Windows**
3. Click **Open Store** next to *Upgrade in the Microsoft app*
4. Buy the **Windows 11 Pro upgrade** and follow the prompts

This is official but usually the most expensive option. The licence is tied to your Microsoft account.

---

## Method 3: Upgrade using the generic Pro key, then activate

Use this if you want to switch to Pro first and activate later, or if your Pro key won't trigger the upgrade on Home.

1. Go to **Settings → System → Activation → Change product key**
2. Enter Microsoft's **generic Windows 11 Pro key**:

   ```
   VK7JG-NPHTM-C97JM-9MPGT-3V66T
   ```

3. Click **Start**. Windows upgrades to Pro and restarts
4. Go back to **Settings → System → Activation → Change product key**
5. Enter your **genuine Windows 11 Pro key** to activate

> **Note:** the generic key only changes the edition. Windows stays **not activated** until you enter a genuine Pro key. More generic keys are listed in [Windows 11 & 10 Product Keys](https://github.com/webex9/windows-11-10-product-keys).

---

## Method 4: Upgrade from Command Prompt

Open **Command Prompt (Admin)** and run:

```bat
:: Check the current edition
DISM /Online /Get-CurrentEdition

:: Upgrade the edition using your Pro key
changepk.exe /ProductKey XXXXX-XXXXX-XXXXX-XXXXX-XXXXX
```

Windows upgrades to Pro and restarts. If it isn't activated afterwards, run:

```bat
slmgr /ipk XXXXX-XXXXX-XXXXX-XXXXX-XXXXX
slmgr /ato
```

---

## How to confirm the upgrade worked

1. Go to **Settings → System → About**. *Edition* should say **Windows 11 Pro**
2. Go to **Settings → System → Activation**. *Activation state* should say **Active**

Or from Command Prompt:

```bat
:: Shows the edition and licence channel
slmgr /dli

:: Shows whether activation is permanent
slmgr /xpr
```

---

## Troubleshooting

| Problem                                                     | Fix                                                                     |
| ----------------------------------------------------------- | ----------------------------------------------------------------------- |
| "This product key didn't work" (`0xC004F050`)               | Check the key for typos, and make sure it is a **Pro** key, not Home    |
| Key accepted but Windows doesn't upgrade                    | Use [Method 3](#method-3-upgrade-using-the-generic-pro-key-then-activate) |
| Upgraded to Pro but shows "Windows isn't activated"         | Enter your genuine Pro key under *Change product key*                  |
| `0xC004C008`: key already used on another PC                | Each PC needs its own key. Contact the seller for a replacement        |
| `0xC004F074`: no KMS server could be contacted              | A KMS key was used. Replace it with a retail Pro key                   |
| Upgrade stuck at a percentage                               | Wait at least 30 minutes, then restart and try again                   |

More error codes and fixes: [Windows 11 & 10 Activation Errors and Fixes](https://github.com/webex9/windows-11-10-activation-errors).

---

## Where to get a Windows 11 Pro key

| Option                   | Notes                                                        |
| ------------------------ | ------------------------------------------------------------ |
| Microsoft Store          | Official in-app upgrade, usually the highest price           |
| New PC with Pro          | Pre-installed by the manufacturer (OEM)                     |
| Authorised key seller    | Genuine retail key at a lower price, delivered by email     |

Genuine **Windows 11 Pro** keys with instant email delivery are available at **[noxkeys.com](https://noxkeys.com/)**.

> Avoid unofficial activators and "crack" tools. They often contain malware and can stop working after a Windows update.

---

## FAQ

**Will I lose my files when upgrading from Home to Pro?**
No. The upgrade keeps all your files, apps and settings. Backing up first is still recommended.

**How long does the upgrade take?**
Usually 5 to 10 minutes, including one or two restarts.

**Do I need to reinstall Windows?**
No. The upgrade happens in place.

**Can I use a Windows 10 Pro key to upgrade Windows 11 Home?**
Yes. A genuine Windows 10 Pro key works on Windows 11 too.

**Can I go back from Pro to Home?**
Not directly. Moving from Pro to Home requires a clean install of Windows 11 Home.

**Is the upgrade free?**
No. You need to buy a Windows 11 Pro licence, either from the Microsoft Store or from an authorised seller.

**Does upgrading to Pro make Windows faster?**
No. Pro adds features but doesn't change performance.

**Is Windows 10 Home to Pro still worth it?**
Windows 10 reached end of support on October 14, 2025. Upgrading to **Windows 11 Pro** is the better choice if your PC supports it.

---

## References

- [Microsoft Support – Upgrade Windows Home to Windows Pro](https://support.microsoft.com/en-us/windows/upgrade-windows-home-to-windows-pro-ef34d520-e73f-3198-c525-d1a218cc2818)
- [Microsoft – Compare Windows 11 Home and Pro](https://www.microsoft.com/en-us/windows/compare-windows-11-home-vs-pro-versions)
- [Windows 11 & 10 Product Keys](https://github.com/webex9/windows-11-10-product-keys) – generic and KMS keys for every edition
- [Windows 11 & 10 Activation Errors and Fixes](https://github.com/webex9/windows-11-10-activation-errors) – error codes explained
- [Microsoft Office 2024, 2021 & 2019 Product Keys](https://github.com/webex9/microsoft-office-2024-2021-2019-product-keys)
- [Windows Server 2025, 2022 & 2019 Product Keys](https://github.com/webex9/windows-server-2025-2022-2019-product-keys)
- [Noxkeys – Genuine Windows 11 Pro keys](https://noxkeys.com/)

---

⭐ **If this helped, star the repo** so others can find it. Last updated: October 2026.
