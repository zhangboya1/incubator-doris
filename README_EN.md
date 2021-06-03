# Apache Doris Baidu Mirror

Here is a mirror repository of [Apache Doris](https://github.com/apache/incubator-doris) maintained by the Baidu Doris(Palo) team.

This mirror repository is only used to release a [PATCH version(tags)](https://semver.org/) based on the official Release version of Apache Doris. Including quick bug fixes and new feature updates.

These PATCH versions have been tested and launched within Baidu, and all code submissions are stored in the official repository and are recommended for use.

Please see [here](https://github.com/baidu-doris/incubator-doris/tags) for all PATCH versions

## Special Statement

**The names Apache, Apache Doris, and Doris belong to the Apache Software Foundation.**

**This repo is NOT the official release version of Doris, but it is fully compatible with the Apache Doris. Please go to [Official Website](doris.apache.org) to download the official version.**

# Usage

The current [Official Release Version](https://github.com/apache/incubator-doris/tags) of Apache Doris is:

* 0.9.0
* 0.10.0
* 0.11.0
* 0.12.0
* 0.13.0

This warehouse mainly releases PATCH version based on the official MAJOR and MINOR version. Such as:

* 0.9.22-release
* 0.10.23-release
* 0.11.44-release
* 0.12.21-release
* 0.13.12-release

All PATCH versions can be safely upgraded from the corresponding official MAJOR and MINOR version. The PATCH versions themselves are also compatible and can be upgraded safely. Examples are as follows:

* Official `0.12.0-rc02` can be upgraded to `0.12.21-release`
* `0.11.10-release` can be upgraded to `0.11.44-release`
* `0.11.44-release` can be upgraded to `0.12.21-release`

It is recommended to upgrade to the latest PATCH version before upgrading to the next MAJOR and MINOR version. Examples are as follows:

1. The currently used version is `0.11.10-release` and I want to upgrade to version 0.12.
2. First upgrade to `0.11.44-release`, which is the latest PATCH version of 0.11.
3. Upgrade to `0.12.21-release`, which is the latest PATCH version of 0.12.

The PATCH version can also be upgraded safely from or to the official release version. The following upgrade sequence is safe

1. `0.11.10-release` Baidu repo
2. `0.11.44-release` Baidu repo
3. `DORIS-0.12-rc02` Official repo
4. `0.12.21-release` Baidu repo

## Doris pre-compiled binary download

In some cases, users may not be able to successfully obtain Doris binary files through source code compilation. Here we provide a pre-compiled binary download corresponding to the release version

* We still **strongly recommend** users to generate binary files through source code compilation.
* The pre-compiled binary files provided here can only be executed on CentOS 7.3, Intel(R) Xeon(R) Gold 6148 CPU @ 2.40GHz. In other systems or CPU models, the program may not run due to different glibc versions or instruction sets supported by the CPU.
* The FE part of the pre-compiled binary file is compiled with Oracle JDK 1.8. Please make sure that Oracle JDK 1.8 is still used at runtime.
* The pre-compiled contains the following components
    1. Frontend
    2. Backend
    3. Broker
    4. Frontend plugins jars
    5. Spark-Doris-Connector jars

### Download link

[Download](http://palo.baidu.com/docs/%E4%B8%8B%E8%BD%BD%E4%B8%93%E5%8C%BA/%E9%A2%84%E7%BC%96%E8%AF%91%E7%89%88%E6%9C%AC%E4%B8%8B%E8%BD%BD)
