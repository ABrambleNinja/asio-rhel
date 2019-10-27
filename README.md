# asio-rhel
Forked from https://src.fedoraproject.org/rpms/asio.git to build for RHEL/CentOS 8

## How to build
1. Install the Development tools (includes rpm-build)
```bash
sudo dnf group install "Development Tools"
```
2. Install rpmdevtools (for spectool)
```bash
sudo dnf install rpmdevtools
```
3. Install asio build dependencies
```bash
sudo dnf install boost-devel openssl-devel
```
4. Clone repo with git and cd into the folder
```bash
cd asio-rhel
```
5. Create build/SOURCES dir
```bash
mkdir -p build/SOURCES
```
6. Download asio source tarball with spectool
```bash
spectool -g -C build/SOURCES asio.spec
```
7. Build packages with rpmbuild
```bash
rpmbuild --define "_topdir `pwd`/build" -ba asio.spec
```
8. Install asio-devel package
```bash
sudo dnf install ./build/RPMS/x86_64/asio-devel-1.10.8-*.el8.x86_64.rpm
```
