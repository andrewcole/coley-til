# How to get OS version information in Linux

This command gets you information on the Linux **distribution**:
```
cat /etc/os-release
```

As Raspberry Pi OS is based on Debian, the above command will return Debian information. To get Raspberry Pi OS information, use the following command:
```
cat /etc/rpi-issue
```

## Versions in the wild

Versions I've seen in the wild (ie my personal network):

| OS | Release Date | /etc/os-release Name | /etc/os-release Version | /etc/rpi-issue reference |
| -- | ----------- |----------- |----------- |----------- |
| Raspberry Pi OS | 2024-10-22 | Debian GNU/Linux | 12 (bookworm) | 2024-10-22 |
| Raspberry Pi OS | 2023-05-03 | Debian GNU/Linux | 11 (bullseye) | 2023-05-03 |
| Debian 12 | 2023-06-10 | Debian GNU/Linux | 12 (bookworm) | n/a |
## References

* [os-release(5)](https://www.linux.org/docs/man5/os-release.html)
