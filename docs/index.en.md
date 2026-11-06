# Overview

[![GitHub](https://img.shields.io/github/license/SilviaSWR/asgi-webdav)](https://github.com/SilviaSWR/asgi-webdav/blob/main/LICENSE)
![Pytest Workflow Status](https://github.com/SilviaSWR/asgi-webdav/actions/workflows/check-pytest.yml/badge.svg)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![GitHub Downloads](https://img.shields.io/github/downloads/SilviaSWR/asgi-webdav/total)](https://github.com/SilviaSWR/asgi-webdav/releases)

An asynchronous WebDAV server implementation, Support multi-provider, multi-account and permission control.

!!! note "About this fork"

    This documentation is published from the [SilviaSWR/asgi-webdav](https://github.com/SilviaSWR/asgi-webdav)
    fork; the original project and documentation were created by
    [Rex Zhang](https://github.com/rexzhang). The fork is not published on PyPI.

## Features

- [ASGI](https://asgi.readthedocs.io) standard
- WebDAV standard: [RFC4918](https://www.ietf.org/rfc/rfc4918.txt)
- Support multi-provider: FileSystemProvider, MemoryProvider, WebHDFSProvider
- Support multi-account and permission control
- Support optional anonymous user
- Support optional home directory
- Support store password in raw/hashlib/LDAP(experimental) mode
- Full asyncio file IO
- Passed all [litmus(0.13)](http://www.webdav.org/neon/litmus) test, except 1 warning(A security alert that will not be triggered in an ASGI environment.)
- Browse the file directory in the browser
- Support HTTP Basic/Digest authentication
- Support response in Gzip/Zstd
- Compatible with macOS finder and Window10 Explorer

## Quick Start

```shell
docker pull ghcr.io/silviaswr/asgi-webdav
docker run -dit --restart unless-stopped \
  -p 8000:8000 \
  -e UID=1000 -e GID=1000 \
  -v /your/data:/data \
  --name asgi-webdav ghcr.io/silviaswr/asgi-webdav
```

## Default Account

|            | value      | description                     |
| ---------- | ---------- | ------------------------------- |
| username   | `username` | -                               |
| password   | `password` | -                               |
| permission | `["+"]`    | Allow access to all directories |

## View in Browser

![](web-dir-browser-screenshot.png)
