# rDownloader packages for apt and dnf

The signed apt and dnf repositories of [rDownloader](https://rdownloader.net), a local-first
download manager with a web interface, for x86-64 and arm64. Served at <https://degoya.github.io/rdownloader-packages>.

Debian and Ubuntu:

```bash
sudo install -d -m 0755 /etc/apt/keyrings
curl -fsSL https://degoya.github.io/rdownloader-packages/rdownloader.asc | sudo tee /etc/apt/keyrings/rdownloader.asc > /dev/null
curl -fsSL https://degoya.github.io/rdownloader-packages/rdownloader.sources | sudo tee /etc/apt/sources.list.d/rdownloader.sources > /dev/null
sudo apt update
sudo apt install rdownloader
```

Fedora (dnf) and openSUSE (zypper):

```bash
sudo curl -fsSL -o /etc/yum.repos.d/rdownloader.repo https://degoya.github.io/rdownloader-packages/rdownloader.repo
sudo dnf install rdownloader
# openSUSE: sudo zypper addrepo https://degoya.github.io/rdownloader-packages/rdownloader.repo && sudo zypper install rdownloader
```

`apt upgrade` and `dnf upgrade` then install every new release. The repository indexes and the
rpm packages are signed with the key `47562DABFCFC3F17C78567CE395FA7C2B11721D1`; compare it with the fingerprint dnf shows
on the first install, or with `gpg --show-keys /etc/apt/keyrings/rdownloader.asc`. The last
2 versions of each package stay here for a downgrade (`apt install rdownloader=<version>`,
`dnf downgrade rdownloader`).

The files are written by the release workflow of
[degoya/rDownloader](https://github.com/degoya/rDownloader) with every release — issues and
changes go there, not here. The handbook's installation page:
<https://github.com/degoya/rDownloader/wiki/installation>.
