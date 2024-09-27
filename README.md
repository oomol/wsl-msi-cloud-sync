# Sync WSL MSI to [R2]

This project is used to sync the WSL MSI installer to the [R2] bucket.

Because in some areas downloading GitHub releases directly may result in network fluctuations and packet loss issues, we will upload the WSL installation package to [Cloudflare R2] and use CDN to accelerate it.

This project will not be synchronized frequently (we will decide based on our business needs.), and we do not guarantee that previous versions of the WSL installation package will be retained.

## Usage

1. First request: <https://static.oomol.com/wsl-msi/latest.json>
2. Get `x64.url` or `arm64.url` from latest.json
3. Use `x64.url` or `arm64.url` to download

## Description

latest.json format:

```json
{
  "version": "WSL Tag",
  "date": "Sync Date(e.g. 2024-07-30T13:06:31Z)",
  "x64": {
    "url": "Download URL",
    "sha256": "x64.msi SHA256",
    "size": 123456789
  },
  "arm64": {
    "url": "Download URL",
    "sha256": "arm64.msi SHA256",
    "size": 123456789
  }
}
```

[R2]: https://www.cloudflare.com/r2
[Cloudflare R2]: https://developers.cloudflare.com/r2/
