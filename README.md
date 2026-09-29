# ThreatSpire HoneyPot — Community Edition releases

Download the free ThreatSpire HoneyPot Community Edition (IT sensors) installers from the
[Releases](../../releases) page.

| Platform | Asset |
| --- | --- |
| Linux / AMD64 | `threatspire-honeypot-community-<version>-linux-amd64.zip` (or `.tar.gz`) |
| Raspberry Pi / Linux ARM64 | `threatspire-honeypot-community-<version>-linux-arm64.zip` (or `.tar.gz`) |

Unpack, then run `sudo ./install.sh`; see `README-INSTALL.md` inside the bundle.

## Verify your download

Each release includes a `SHA256SUMS.txt` signed with the ThreatSpire CE release key
(`releases@threatspire.com`, fingerprint `BBDF 0CB0 2481 5B35 69C0 88DF 7FBA CD15 99E5 1508`).
The public key is [`threatspire-community-signing-key.asc`](threatspire-community-signing-key.asc).

```bash
gpg --import threatspire-community-signing-key.asc
gpg --verify threatspire-honeypot-community-<version>-SHA256SUMS.txt.asc threatspire-honeypot-community-<version>-SHA256SUMS.txt
shasum -a 256 -c threatspire-honeypot-community-<version>-SHA256SUMS.txt
```

This repository hosts release binaries only. More at [threatspire.com](https://www.threatspire.com).
