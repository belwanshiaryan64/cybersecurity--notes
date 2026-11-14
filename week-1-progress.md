# Week 1: Linux Command Line & Networking Fundamentals

## Part 1: OverTheWire Bandit (Levels 0–10)
Completed foundational Linux command-line challenges via SSH in Windows PowerShell, focusing on file inspection, filtering, pipes, and basic decoding.

### Key Commands & Techniques
* **`ssh <user>@bandit.labs.overthewire.org -p 2220`** — Connected remotely to target Linux environments over a custom port.
* **`ls -la`** — Listed all directory contents in long format, revealing hidden files prefixed with a dot (`.`).
* **`cat ./-file` / `cat "./--spaces in filename--"`** — Used relative path prefixes (`./`) and quotes to read files starting with dashes or containing spaces without triggering command flag errors.
* **`file ./*`** — Identified true file types (`ASCII text` vs. binary `data`) across multiple files before opening them.
* **`find . -type f -size 1033c ! -executable`** — Located specific files recursively across subdirectories using exact byte size (`c`) and permission filters.
* **`find / -user bandit7 -group bandit6 -size 33c 2>/dev/null`** — Searched the entire filesystem by file ownership and redirected `Permission denied` errors (`stderr`) to `/dev/null`.
* **`grep "keyword" data.txt`** — Filtered large text files to isolate lines matching a specific string.
* **`sort data.txt | uniq -u`** — Chained commands with a pipe (`|`) to sort lines alphabetically and isolate the single non-duplicate entry.
* **`strings data.txt | grep "=="`** — Extracted human-readable ASCII strings from a binary file and filtered for specific delimiters.
* **`base64 -d data.txt`** — Decoded Base64-encoded text back into readable plaintext.

---

## Part 2: TryHackMe — Network Fundamentals
Completed **What is Networking?** and **Intro to LAN** under the *Pre Security* learning path.

### Core Takeaways
* **IP Address vs. MAC Address:** An IP address is a logical, changeable network address (e.g., `192.168.1.10`) used to route traffic across networks, while a MAC address is a permanent physical hardware identifier burned into a Network Interface Card (NIC).
* **Switch vs. Router:** A **Switch** connects devices within a Local Area Network (LAN) and forwards frames directly to the target device using MAC addresses. A **Router** connects separate networks together (such as a LAN to the internet) using IP addresses.
* **Subnetting:** Dividing a large network into smaller sub-networks using a Subnet Mask (e.g., `255.255.255.0`) to improve efficiency and contain potential security breaches.
* **ARP (Address Resolution Protocol):** Resolves a known IP address to an unknown physical MAC address on a local network via broadcast requests.
* **DHCP (Dynamic Host Configuration Protocol):** Automatically assigns available IP addresses, subnet masks, and default gateways to devices joining a network.
* **ICMP (`ping`):** Tests basic reachability and round-trip latency between two network hosts.
