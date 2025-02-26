[![GitHub license](https://img.shields.io/github/license/r4sas/PBinCLI.svg)](https://github.com/r4sas/PBinCLI/blob/master/LICENSE)
[![GitHub tag](https://img.shields.io/github/tag/r4sas/PBinCLI.svg)](https://github.com/r4sas/PBinCLI/tags/)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/4f24f43356a84621bbd9078c4b3f1b70)](https://www.codacy.com/gh/r4sas/PBinCLI/dashboard?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=r4sas/PBinCLI&amp;utm_campaign=Badge_Grade)

PBinCLI
=====

PBinCLI is command line client for [PrivateBin](https://github.com/PrivateBin/PrivateBin/) written on Python 3.

Installing
-----
```bash
virtualenv --python=python3 venv
. venv/bin/activate
pip install pbincli
```

Usage
-----
By default pbincli configured to use `https://paste.i2pd.xyz/` for sending and receiving pastes. No proxy used by default.

You can create config file with variables `server` and `proxy` in `~/.config/pbincli/pbincli.conf` to use different settings.

Example contents:

```ini
server=https://paste.i2pd.xyz/
proxy=http://127.0.0.1:3128
```

Run inside `venv` command:

```bash
pbincli send --text "Hello!"
```

Or use stdin input to read text for paste:

```bash
pbincli send - <<EOF
Hello! This is test paste!
EOF
```

It will send string `Hello! This is test paste!` to PrivateBin.

To send file use `--file` or `-f` with filename. Example:

```bash
pbincli send -c "My document" -f info.pdf
```

To retrieve paste from server, use `get` command with paste info.

It must be formated like `pasteID#passphrase`. Example:

```bash
pbincli get 49eeb1326cfa9491#vfeortoVWaYeJlviDdhxQBtj5e0I2kArpynrtu/tnGs=
```
More info you can find by typing

```bash
pbincli [-h] {send, get, delete}
```

TODO
----
Write a more complete usage documentation.

License
-------
This project is licensed under the MIT license, which can be found in the file
[LICENSE](https://github.com/r4sas/PBinCLI/blob/master/LICENSE) in the root of the project source code.
