# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

Apache Atlas Overview
=====================

Apache Atlas framework is an extensible set of core
foundational governance services – enabling enterprises to effectively and
efficiently meet their compliance requirements within Hadoop and allows
integration with the whole enterprise data ecosystem.

This will provide true visibility in Hadoop by using both a prescriptive
and forensic model, along with technical and operational audit as well as
lineage enriched by business taxonomical metadata.  It also enables any
metadata consumer to work inter-operably without discrete interfaces to
each other -- the metadata store is common.

The metadata veracity is maintained by leveraging Apache Ranger to prevent
non-authorized access paths to data at runtime.
Security is both role based (RBAC) and attribute based (ABAC).


Build Process
=============

1. Get Atlas sources to your local directory, for example with following commands
   $ cd <your-local-directory>
   $ git clone https://github.com/apache/atlas.git
   $ cd atlas

   # Checkout the branch or tag you would like to build
   #
   # to checkout a branch
     $ git checkout <branch>

   # to checkout a tag
     $ git checkout tags/<tag>

2. Execute the following commands to build Apache Atlas ,please set java version is jdk8

   $ export MAVEN_OPTS="-Xms2g -Xmx2g"
   $ mvn clean install -DargLine="--add-opens java.base/java.util=ALL-UNNAMED" -DskipTests
   $ mvn clean package -Pdist -Dmaven.test.skip=true

3. After above build commands successfully complete, you should see the following files

   distro/target/apache-atlas-<version>-bin.tar.gz
   distro/target/apache-atlas-<version>-hbase-hook.tar.gz
   distro/target/apache-atlas-<version>-hive-hook.tar.gz
   distro/target/apache-atlas-<version>-impala-hook.tar.gz
   distro/target/apache-atlas-<version>-kafka-hook.tar.gz
   distro/target/apache-atlas-<version>-server.tar.gz
   distro/target/apache-atlas-<version>-sources.tar.gz
   distro/target/apache-atlas-<version>-sqoop-hook.tar.gz
   distro/target/apache-atlas-<version>-storm-hook.tar.gz
   distro/target/apache-atlas-<version>-falcon-hook.tar.gz

4. For more details on installing and running Apache Atlas, please refer to https://atlas.apache.org/#/Installation


适配CDH6.3.2 对应组件的版本信息:

| 组件                               | 版本                     |
| ------------------------------------ | -------------------------- |
| Hadoop                             | 3.0.0+cdh6.3.2           |
| HBase                              | 2.1.0+cdh6.3.2           |
| Hive                               | 2.1.1+cdh6.3.2           |
| Impala                             | 3.2.0+cdh6.3.2           |
| Java 8                             | java version "1.8.0_181" |
| Kafka                              | 2.2.1+cdh6.3.2           |
| Solr                               | 7.4.0+cdh6.3.2           |
| spark                              | 2.4.0+cdh6.3.2           |
| ZooKeeper                          | 3.4.5+cdh6.3.2           |
