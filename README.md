[English](https://github.com/baidu-doris/incubator-doris/blob/master/README_EN.md)

# Apache Doris 百度镜像库

这里是由 Baidu Doris(Palo) 团队维护的 [Apache Doris](https://github.com/apache/incubator-doris) 的镜像库。

该镜像库仅用于发布基于 Apache Doris 官方 Release 版本的 [3 位迭代版本(tags)](https://semver.org/lang/zh-CN/)。包括快速的 Bug 修复和新功能更新。

这些 3 位迭代版本都在百度内部进行过测试和上线，并且所有代码提交均存在与官方仓库中，推荐使用。

所有 3 位迭代版本请看 [这里](https://github.com/baidu-doris/incubator-doris/tags)

## 使用说明

目前 Apache Doris 的 [官方Release版本](https://github.com/apache/incubator-doris/tags) 为：

* 0.9.0
* 0.10.0
* 0.11.0
* 0.12.0
* 0.13.0

本仓库主要基于 2 位官方版本发布 3 位迭代版本。如：

* DORIS-0.9.22-release
* DORIS-0.10.23-release
* DORIS-0.11.44-release
* DORIS-0.12.21-release
* DORIS-0.13.12-release

所有 3 位版本可以安全的从对应的官方 2 位版本升级。3 位版本本身也是兼容的，可以安全升级。举例如下：

* 官方 `0.12.0-rc02` 可以升级至 `DORIS-0.12.21-release`
* `DORIS-0.11.10-release` 可以升级至 `DORIS-0.11.44-release`
* `DORIS-0.11.44-release` 可以升级至 `DORIS-0.12.21-release`

建议在升级 2 位版本之前，先升级到对应的最新的 3 位版本后，再升级 2 位版本。举例如下：

1. 当前使用版本为 `DORIS-0.11.10-release`，想升级到 0.12 版本。
2. 首先升级到 `DORIS-0.11.44-release`，即 0.11 的最新 3 位版本。
3. 再升级到 `DORIS-0.12.21-release`，即 0.12 的最新 3 位版本。

3 位迭代版本也可以安全的和官方 2 位版本升级。如以下的升级序列是安全的

1. `DORIS-0.11.10-release`  Baidu 库
2. `DORIS-0.11.44-release`  Baidu 库
3. `0.12-rc02`  官方库
4. `DORIS-0.12.21-release`  Baidu 库

## Doris 预编译二进制下载

某些情况下，可能用户无法顺利的通过源代码编译的方式得到 Doris 的二进制文件。这里我们提供对应三位版本的预编译二进制下载

* 我们依然**强烈推荐**用户自行通过源码编译产生二进制文件。
* 这里提供的预编译二进制文件仅在 CentOS 7.3, Intel(R) Xeon(R) Gold 6148 CPU @ 2.40GHz 上执行通过。在其他系统或 CPU 型号下，可能会因为 glibc 版本或者 CPU 支持的指令集不同，而导致程序无法运行。
* 预编译二进制文件的 FE 部分使用 Oracle JDK 1.8 编译，请确保运行时依然使用 Oracle JDK 1.8 版本。
* 预编译包含如下组件
    1. Frontend
    2. Backend
    3. Broker
    4. Frontend plugins jars
    5. Spark-Doris-Connector jars

### 下载链接

* [0.12.21-release (447MB)](https://palo-cloud-repo-bd.bd.bcebos.com/baidu-doris-release/DORIS-0.12.21-release.tar.gz) [更新于 2020-08-11]
* [0.13.9-release (547MB)](https://palo-cloud-repo-bd.bd.bcebos.com/baidu-doris-release/DORIS-0.13.9-release.tar.gz) [更新于 2020-10-21]
* [0.13.11-release (552MB)](https://palo-cloud-repo-bd.bd.bcebos.com/baidu-doris-release/DORIS-0.13.11-release.tar.gz) [更新于 2020-11-15]

    * Change Log

        1. 新增功能

            * 支持持久化存储在运行时修改的FE或BE配置参数。[#4704](https://github.com/apache/incubator-doris/pull/4704)
            * 支持通过 ALTER TABLE 语句修改外部表。[#4699](https://github.com/apache/incubator-doris/pull/4699)
            * 支持通过 ODBC 协议访问 PostgreSQL 外部表。[#4798](https://github.com/apache/incubator-doris/pull/4798)
            * BE 端 Web 页面支持生成 CPU 和 Heap 性能报告。[#4632](https://github.com/apache/incubator-doris/pull/4632)

        2. 严重 Bug 修复

            * 修复 BE 端 Compaction 任务可能导致 BE 宕机的问题。[#4829](https://github.com/apache/incubator-doris/pull/4829)
            * 修复导入任务调度时因异常未捕获，导致作业一直处于 Loading 状态的问题。[#4796](https://github.com/apache/incubator-doris/pull/4796)
            * 修复重启 Master FE 可能导致部分已完成的导入作业状态变成 UNKNOWN 的问题。[#4869](https://github.com/apache/incubator-doris/pull/4869)
            * 修复重命名表可能导致新表名和物化视图重名的问题。[#4870](https://github.com/apache/incubator-doris/pull/4870)

* [0.13.12-release (560MB)](https://palo-cloud-repo-bd.bd.bcebos.com/baidu-doris-release/DORIS-0.13.12-release.tar.gz) [更新于 2020-12-14]

    * 76 Commits added
    * Change Log

        1. 新增功能

            * 支持更多的列类型变换。
            * 支持一种新的 Join Reorder 算法。

                使用一种更合理的方式进行 SQL 中 Join 顺序调整，以尽量避免 Cross Join。该算法在 TPC-DS 的 #17 #25 #29 #37 #82 有显著效果。
                
                该功能为实验性质，可以通过会话变量 `enable_cost_based_join_reorder` 开启。默认关闭。

            * 支持通过 BE 端计算 SQL 中的常量表达式。

                支持对 SQL 中的所有常量表达式发送到 BE 端进行计算。该功能扩展了原先在 FE 端进行常量折叠的功能。但可能产生更多的 RPC 开销。

                该功能为实验性质，可以通过会话变量 `enable_fold_constant_by_be` 开启。默认关闭。

            * 优化了 Unique Key 模型表的读取效率，在部分场景下提升 20% - 40% 的效率。

            * 禁止分区列值为 NULL。

                可以通过会话变量 `allow_partition_column_nullable` 来禁止。默认为 false。

            * 增强了部分 MySQL 生态工具的连接兼容性。
            
        2. 严重 Bug 修复

            * 修复在 Compaction 失败后，垃圾文件未清除导致磁盘空间写满的问题。[#4964](https://github.com/apache/incubator-doris/pull/4964)

## Docker 编译环境镜像下载

某些原因可能导致通过 `docker pull` 的方式下载 `docker.io/apachedoris/doris-dev:build-env-1.2` 这个镜像非常缓慢。你可以通过以下链接将镜像下载到本地后，在通过 `docker load` 命令加载镜像：

[下载 docker.io/apachedoris/doris-dev:build-env-1.2](https://palo-cloud-repo-bd.bd.bcebos.com/baidu-doris-release/apachedoris-build-env-1.2)

`docker load --input apachedoris-build-env-1.2`

之后可以通过 `docker images` 查看到该镜像。

## 百度数据仓库 Palo

百度数据仓库 Palo 提供基于 Doris 的企业级数据仓库托管服务，新用户可0元免费试用3个月。

**试用、多云支持、私有化部署**等请前往：[https://cloud.baidu.com/product/palo.html](https://cloud.baidu.com/product/palo.html) 详询。

欢迎关注 ApacheDoris 官方微信公众号获取更多使用案例和技术文章。

![](https://github.com/baidu-doris/incubator-doris/blob/master/docs/resources/doris-wechat.jpg)
