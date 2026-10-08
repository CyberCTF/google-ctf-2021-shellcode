# Google CTF 2021: abc arm and amd

[abc arm and amd](https://github.com/google/google-ctf/tree/4a8f8d7808254d40f226ac2ab4604601e0e57d57/2021/quals/misc-shellcode), a misc challenge from [Google CTF](https://capturetheflag.withgoogle.com/) 2021
(the official archive [google/google-ctf](https://github.com/google/google-ctf), by Google): write one printable payload of at most 280 bytes that prints the flag on both x86-64 and arm64.
This repository runs it with [Isoloom](https://www.isoloom.com): [`isoloom.yml`](isoloom.yml) describes the machine,
built by the challenge's own Dockerfile, vendored unchanged in [`app/`](app).

| Machine | Service |
| --- | --- |
| challenge | the abc arm and amd service (socat + nsjail) on port 1337, published on 1337 |

## Run it

```bash
isoloom generate
isoloom run docker
```

Then connect with `nc localhost 1337`. The challenge runs in nsjail under kCTF's setup script, so the machine is privileged. The same spec runs as Docker on a local VM (`docker-vm`), on a
cloud VM (`cloud-docker`) or on Kubernetes. Lab guide: the official write-up [`solution/sol.py`](https://github.com/google/google-ctf/blob/4a8f8d7808254d40f226ac2ab4604601e0e57d57/2021/quals/misc-shellcode/solution/sol.py) in the archive.

Upstream version and commit: [UPSTREAM.md](UPSTREAM.md).

## Licence

Apache-2.0, as the Google CTF archive ([LICENSE](LICENSE)). The third-party software inside the image keeps its own
licence. This challenge is deliberately vulnerable: keep it isolated.
