# Shamiko

<center>こっっ…　これで勝ったと思うなよ―――!!</center>

### Introduction
Shamiko is a Zygisk module to hide Magisk root, Zygisk itself and Zygisk modules.

Shamiko read the denylist from Magisk for simplicity but it requires denylist enforcement to be disabled first.

### Usage
1. Install Shamiko and enable Zygisk and reboot
2. Configure denylist to add processes for hiding
3. *DO NOT* turn on denylist enforcement

#### Whitelist
- You can create an empty file `/data/adb/shamiko/whitelist` to turn on whitelist mode and it can be triggered without reboot
- Whitelist has significant performance and memory consumption issue, please use it only for testing
- Only apps that was previously granted root from Magisk can access root
- If you need to grant a new app root access, disable whitelist first

### Changelog
#### 0.2.0
1. Support font modules since Android S
2. Fix module's description

#### 0.3.0
1. Support whitelist (enable by creating an empty file `/data/adb/shamiko/whitelist`)
2. Always unshare (useful for old platforms and isolated processes in new platforms)
3. Request Magisk 23017+, which allows us to strip Java daemon and change denylist regardless of enforcement status
4. Temporarily disable showing status in module description (need to find a new way for it)
5. Support module update since Magisk 23017

#### 0.4.0
1. Add module files checksum
2. Bring status show back
3. Add running status file at `/data/adb/shamiko/.tmp/status`

### 0.4.1
1. Add more hide mechanisms

### 0.4.2
1. Fix app zygote crash on Android 10-

### 0.4.3
1. Fix tmp mount being detected

### 0.4.4
1. Fix module description not showing correctly

### 0.6
1. Hide more trace of Zygisk

### 0.7
1. Support Magisk 26.0
2. Fix font loading
3. Hide more traces of Magisk

### 0.7.1
1. Merge Magisk and KernelSU branch

### 0.7.2
1. Fix a bug causing Zygisk on KernelSU failed to unload
2. Abandon a useless fix leading to more detection
3. Clean service.sh

### 0.7.3
1. Follow root profile on KernelSU

### 0.7.4
1. Support new Zygisk loading mechanisms
2. Fix some issues on Android 11 and below
3. Fix compatibility for Zygisk on KernelSU on Magisk

### 0.7.5
1. Refine hide mechanism, passing more detection (e.g., E-CNY, Play ver 12306)

### 1.0
1. Hide more traces of Zygisk, passing more detection (e.g., ACE, GoTyme Bank, MyTransport.SG, ZainCash, DBS PayLah!, Singpass, Marriott, BPI, Apps using liapp, Apps using Arxan like CaixaBank Sign, etc.)
2. Better support KSU
3. Hide some traces introduced by other modules (e.g. PlayIntegrityFix)
4. Guards the peace of Machikado

### 1.0.1
1. Fix Android 10

### 1.1
1. Support Magisk Canary 27003
2. Provide better hiding for font modules
3. Drop redudant resetprop handling
4. Minor bug fixes and compatibility updates

### 1.1.1
1. Fix crash when using together with some modules

### 1.2
1. Refine hiding mechanism
2. Fix minor bugs

### 1.2.1
1. Drop dependency on tmpfs workdir and don't rely on any mounts
2. Refine hiding mechanism
3. Improve stability and compatibility

### 1.2.2
1. Fix a few instability and performance issues
2. Fix support for 32bit apps

### 1.2.3
1. Fix root impl check
