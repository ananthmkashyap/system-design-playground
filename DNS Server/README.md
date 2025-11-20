# Local Authoritative DNS Server (CoreDNS)

This project demonstrates how to build a local authoritative DNS server using CoreDNS, Docker, and custom BIND-style zone files.
It is intended as a system-design learning project to show how DNS works internally, from zone files to authoritative resolution.

## Overview
### This project sets up:
1. A CoreDNS authoritative DNS server running in Docker
2. A custom DNS zone (mytest.local) with A, MX, TXT, and NS records
3. A Corefile that loads the zone using the file plugin
4. Local DNS resolution using dig
5. A clear demonstration of how authoritative DNS works end-to-end

## Running the Project:
1. Run CoreDNS with:
```docker
docker compose up -d
```

2. Use dig to test DNS resolution:
```dig
dig @127.0.0.1 -p 5353 www.mytest.local A +noall +answer
```