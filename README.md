# amass
`Amass` is a powerful tool for network mapping and attack surface discovery, commonly used for DNS enumeration and subdomain discovery. Here's how to use it, along with examples and expected outputs.

### Installation

If `Amass` is not already installed on your Kali Linux system, you can install it using:

```bash
sudo apt-get install amass
```

### Basic Usage

The basic syntax for using `Amass` is:

```bash
amass <command> <options>
```

### Common Commands

1. **Subdomain Enumeration**:
   To discover subdomains for a given domain, use the `enum` command:

   ```bash
   amass enum -d example.com
   ```

   **Expected Output**:
   ```
   [INFO] Enumerating subdomains for example.com
   [INFO] Found: www.example.com
   [INFO] Found: api.example.com
   [INFO] Found: blog.example.com
   ```

2. **Using Multiple Sources**:
   You can specify multiple data sources for subdomain enumeration:

   ```bash
   amass enum -d example.com -src
   ```

   **Expected Output**:
   ```
   [INFO] Enumerating subdomains for example.com
   [INFO] Source: passive DNS
   [INFO] Found: www.example.com
   [INFO] Source: brute force
   [INFO] Found: api.example.com
   ```

3. **Active Enumeration**:
   For active enumeration, use the `-active` flag:

   ```bash
   amass enum -d example.com -active
   ```

   **Expected Output**:
   ```
   [INFO] Enumerating subdomains for example.com
   [INFO] Active enumeration started
   [INFO] Found: www.example.com
   [INFO] Found: staging.example.com
   ```

4. **Output to File**:
   To save results to a file, use the `-o` option:

   ```bash
   amass enum -d example.com -o output.txt
   ```

   This command will save the discovered subdomains in `output.txt`.

### Conclusion

`Amass` is a versatile tool for gathering information about domains and their associated subdomains. By utilizing various commands and options, you can customize your enumeration process to suit your needs. Regular use of `Amass` can help enhance your reconnaissance efforts during penetration testing or security assessments.



                                           ALTERNATIVE
Amass is a powerful tool in Kali Linux for network mapping and information gathering. It's used to identify and enumerate network hosts, domains, and IP addresses. Here's a brief overview of how to use Amass:

**Installation**

Amass is typically pre-installed in Kali Linux. If not, you can install it using:

```
sudo apt-get install amass
```

**Basic Usage**

The basic syntax for using Amass is:

```
amass [options] <target>
```

Where `<target>` is the domain name, IP address, or network range you want to scan.

**Common Options**

- `-d` or `--domain`: Specify the domain to scan.
- `-i` or `--ip`: Specify the IP address to scan.
- `-n` or `--network`: Specify the network range to scan (CIDR notation).
- `-o` or `--output`: Specify the output file for the scan results.
- `-v` or `--verbose`: Increase the verbosity of the scan output.

**Examples**

1. **Domain Scan**:

```
amass -d example.com
```

This command will scan the `example.com` domain and enumerate hostnames, IP addresses, and other network resources.

**Expected Output**:
```
[+] IP Addresses:
  - 192.0.2.1
  - 2001:db8::1

[+] Hostnames:
  - example.com
  - www.example.com
  - mail.example.com

[+] Subdomains:
  - blog.example.com
  - shop.example.com
```

2. **IP Address Scan**:

```
amass -i 192.0.2.1
```

This command will scan the IP address `192.0.2.1` and gather information about the host, including open ports and services.

**Expected Output**:
```
[+] IP Address: 192.0.2.1
[+] Hostname: example.com
[+] Open Ports:
  - 22/tcp (ssh)
  - 80/tcp (http)
  - 443/tcp (https)
```

3. **Network Scan**:

```
amass -n 192.0.2.0/24
```

This command will scan the `192.0.2.0/24` network range and enumerate hosts, IP addresses, and other network resources.

**Expected Output**:
```
[+] Network Range: 192.0.2.0/24
[+] Hosts:
  - 192.0.2.1 (example.com)
  - 192.0.2.2 (another.example.com)
  - 192.0.2.3 (third.example.com)

[+] IP Addresses:
  - 192.0.2.1
  - 192.0.2.2
  - 192.0.2.3
```

These are just a few examples of how to use Amass. The tool offers many more options and features to help you gather information about networks and hosts.






                                     ALTERNATIVE
`Amass` is a powerful tool in Kali Linux used for network mapping and reconnaissance, particularly for discovering subdomains and performing DNS enumeration. Here's how to use it, along with examples and expected output.

### Installation

If `Amass` is not already installed, you can install it using:

```bash
sudo apt-get install amass
```

### Basic Usage

The basic syntax for using `Amass` is:

```bash
amass <command> [options]
```

### Common Commands

1. **Enum**: This command is used for subdomain enumeration.

   ```bash
   amass enum -d example.com
   ```

   **Expected Output**:
   ```
   Subdomain enumeration for example.com
   [INFO] Enumerating subdomains for example.com
   [INFO] Found: www.example.com
   [INFO] Found: api.example.com
   [INFO] Found: blog.example.com
   ```

2. **Brute Force**: To brute force subdomains using a wordlist.

   ```bash
   amass enum -d example.com -brute -w /path/to/wordlist.txt
   ```

   **Expected Output**:
   ```
   [INFO] Brute forcing subdomains for example.com
   [INFO] Found: test.example.com
   [INFO] Found: dev.example.com
   ```

3. **Passive Enumeration**: To find subdomains using passive sources.

   ```bash
   amass enum -passive -d example.com
   ```

   **Expected Output**:
   ```
   [INFO] Passive enumeration for example.com
   [INFO] Found: www.example.com
   [INFO] Found: mail.example.com
   ```

4. **Output to File**: To save the results to a file.

   ```bash
   amass enum -d example.com -o subdomains.txt
   ```

   This command will create a file named `subdomains.txt` containing the found subdomains.

### Conclusion

`Amass` is a versatile tool for discovering subdomains and performing reconnaissance. By utilizing its various options and commands, you can gather valuable information about a target domain, aiding in security assessments and penetration testing.





                                      ALTERNATIVE
`Amass` is a powerful tool included in Kali Linux that is used for network mapping and external asset discovery. It is particularly useful for penetration testers and security researchers to gather information about a target's attack surface. Below is an overview of how to use `Amass`, along with examples and expected outputs.

### Installation

In most cases, `Amass` comes pre-installed with Kali Linux. If it is not installed, you can easily install it using:

```bash
sudo apt update
sudo apt install amass
```

### Basic Usage

`Amass` operates through various subcommands, each serving a different purpose. Here are the primary subcommands:

1. **intel**: Collect intelligence on the target.
2. **enum**: Perform enumeration and mapping of the target.
3. **viz**: Visualize enumeration results.
4. **track**: Track changes between enumerations.
5. **db**: Manage the Amass graph database.

### Examples

1. **Basic Subdomain Enumeration**:
   To discover subdomains of a target domain, you can use the following command:

   ```bash
   amass enum -d example.com
   ```

   **Expected Output**:
   ```
   [INFO] Enumerating subdomains for example.com
   [INFO] Found subdomain: www.example.com
   [INFO] Found subdomain: api.example.com
   ```

2. **Passive Mode Enumeration**:
   If you want to perform a passive scan without directly interacting with the target, use:

   ```bash
   amass enum -passive -d example.com
   ```

   **Expected Output**:
   ```
   [INFO] Passive enumeration for example.com
   [INFO] Found subdomain: mail.example.com
   [INFO] Found subdomain: blog.example.com
   ```

3. **Active Enumeration**:
   To perform a more aggressive scan that includes DNS resolution, use:

   ```bash
   amass enum -active -d example.com
   ```

   **Expected Output**:
   ```
   [INFO] Active enumeration for example.com
   [INFO] Found subdomain: www.example.com (Resolved IP: 192.0.2.1)
   [INFO] Found subdomain: api.example.com (Resolved IP: 192.0.2.2)
   ```

4. **Collecting Intelligence**:
   To gather intelligence about a target, you can use the `intel` subcommand:

   ```bash
   amass intel -d example.com
   ```

   **Expected Output**:
   ```
   [INFO] Collecting intelligence for example.com
   [INFO] Found related domains: example.org, example.net
   ```

5. **Visualizing Results**:
   To visualize the results of your enumeration, you can use:

   ```bash
   amass viz -d example.com
   ```

   This command will generate a visual representation of the discovered domains and their relationships.

### Conclusion

`Amass` is a versatile tool that provides comprehensive capabilities for subdomain enumeration and attack surface mapping. By using its various subcommands, you can gather valuable information about a target's infrastructure, which is essential for effective penetration testing and security assessments.

---
Learn more:
1. [How to Use OWASP Amass: An Extensive Tutorial - Dionach](https://www.dionach.com/how-to-use-owasp-amass-an-extensive-tutorial/)
2. [Amass -- Mapping Attack Surface Automatically](https://www.kalilinux.in/2021/12/amass-mapping-attack-surface.html)
3. [Amass Network Mapping Tool in Kali Linux | Siberoloji](https://blog.siberoloji.com/amass-network-mapping-tool-kali-linux/)
