---
title: Glossary
pcx_content_type: concept
weight: 6
meta:
  title: Glossary | Keyless SSL
  description: Learn more about the common terms related to Keyless SSL.
---

# Glossary

## Cloudflare Keyless SSL key server (“key server”)

The key server is a daemon that you run on your own infrastructure. The key server receives inbound requests from Cloudflare’s keyless client on TCP port `2407` (by default) so you must make sure that your firewall and other access control lists permit these requests from [Cloudflare’s IP ranges](https://www.cloudflare.com/ips/).

Your key servers are contacted by Cloudflare during the TLS handshake process and must be online to terminate new TLS connections. Existing sessions can be resumed using unexpired TLS session tickets without needing to contact the key server.

## Cloudflare Keyless SSL client (“keyless client”)

The keyless client is a process that runs on Cloudflare’s infrastructure. The keyless client makes outbound requests to your key server on TCP port `2407` for assistance in establishing new TLS sessions.