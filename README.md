# 🚀 CVE-2010-1938 FTP Off-by-One Exploit

A simple Python script to test an off-by-one vulnerability in the OPIE library (CVE-2010-1938). This vulnerability affects certain FTP servers and may allow for Denial of Service (DoS) or arbitrary code execution.

![Python](https://img.shields.io/badge/python-v3.9%2B-blue)
![FTP Exploit](https://img.shields.io/badge/FTP-Exploit-red)
![CVE](https://img.shields.io/badge/CVE-2010--1938-orange)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📜 Description

This script targets a known vulnerability (CVE-2010-1938) in the OPIE library used in some FTP servers. By sending a specially crafted username, the script attempts to cause a stack overflow in the FTP server, potentially leading to remote code execution.

## 💡 Features

- **Adjustable payload size** to fine-tune the exploit.
- Sends the payload in **fragments** to avoid detection and prevent immediate server crashes.
- Customizable **target IP and port** for penetration testing.

## 🚨 Disclaimer

This tool is for educational purposes only. The author is not responsible for any misuse of this script. Always obtain proper authorization before running any exploit.

---

## 🚀 Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/nexxus67/cve-2010-1938.git
    cd cve-2010-1938
    ```

2. Run the exploit with following options:
    ```bash
    python3 exploit.py your-target-ip

    also, you can check the length that provokes the crash with

    python3 exploit.py your-target-ip --fuzz

    once you found the length (for example 257), try different byte-size in that position

    python3 exploit.py 192.168.1.100 --byte-test 00 --length 257
    python3 exploit.py 192.168.1.100 --byte-test ff --length 257
    ```

3. The script will attempt to exploit the vulnerability by sending the payload to the target FTP server.

---

## ⚙️ Requirements

- Python 3.9+
- Socket module (comes pre-installed with Python)

---

## 📖 How it works

1. **Connection to the target**: The script establishes a socket connection with the target FTP server.
2. **Payload delivery**: The payload is delivered in fragments to avoid overwhelming the server.
3. **Exploit trigger**: A `PASS` command is sent after the payload to trigger the off-by-one vulnerability.
4. **Feedback**: The server's response is logged to observe success or failure.

---

## 🚧 To-Do

- Add more sophisticated payload crafting.
- Implement payloads for remote code execution (RCE) based on server feedback.
- Enhance error handling and output formatting.

---

## 🛠️ Development

Contributions are welcome! Feel free to open issues or submit pull requests.

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

⚠️ **Warning**: Unauthorized use of this script on servers you do not own or have explicit permission to test is illegal.

