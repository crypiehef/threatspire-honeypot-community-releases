# ThreatSpire HoneyPot — Community Edition releases

Download the free ThreatSpire HoneyPot Community Edition (IT sensors) installers from the
[Releases](../../releases) page.

**Latest release: v1.0.0** (Linux AMD64 and Raspberry Pi / ARM64).

## What's included

A medium-interaction honeypot that runs as two hardened native systemd services (a sensor and a
management service) and never executes attacker input.

- **IT sensors:** SSH, Telnet, HTTP/HTTPS, RDP, SMB (with a read-only decoy file share and a
  canary-token document), F5 BIG-IP APM, SIP/VoIP, RTSP (decoy IP-camera video), Matter/IP,
  MySQL, MSSQL, Redis, LDAPv3/AD, and a configurable generic raw-TCP listener.
- **MITRE ATT&CK mapping** of captured activity (Enterprise matrix).
- **Local web console** (loopback only) for live events, IOCs and sensor settings.
- **Threat-intel export:** REST (native / STIX 2.1 / MISP) and a TAXII 2.1 server.
- **Not included:** the OT/ICS sensors and the ThreatSpire tenant control plane, which are part of
  the commercial edition. For healthcare devices see the
  [Hospital Honeypot Community Edition](https://github.com/crypiehef/hospital-honeypot-community).

## Community reporting

The Community Edition anonymously reports what its sensors capture to the ThreatSpire community
endpoint (`https://console.threatspire.com`) with no configuration. It helps the ThreatSpire team
study attacker behavior and improves the community's threat data.

- **Reported per event:** the sensor name, event type, timestamps, session ID, the **attacker's**
  source IP, derived IOCs, MITRE ATT&CK technique IDs, a short excerpt of the attacker's own
  payload, the honeypot version, and the host name of the machine it runs on. The report is
  authenticated with a shared build key, not an account.
- **Identification:** the ThreatSpire server identifies a node only by the public IP the report
  arrives from, which is used to count nodes by country and region. The host name is not stored.
- **Reliability:** failed reports are retried and progress is tracked, so events are not dropped.

If you are not comfortable with this, do not run the Community Edition; there is no
account or sign-up involved either way.

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

## License

The Software is free to use and may be redistributed unmodified under the terms in [LICENSE](LICENSE). The source code is proprietary.

This repository hosts release binaries only. More at [threatspire.com](https://www.threatspire.com).
