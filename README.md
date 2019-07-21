# scala
sbt manual
一、下载scala
1. https://www.scala-lang.org/，两种方式一种是Scala IDE，一种是SBt，我选择后者
2. 解压sbt-1.2.8，配置环境变量
3. 配置sbt工作目录和aliyun的ivy2仓库，在conf/sbtconfig.txt下面
-Dsbt.boot.directory=D:/scala/sbt-1.2.8/.sbt/boot
-Dsbt.global.base=D:/scala/sbt-1.2.8/data/.sbt
-Dsbt.ivy.home=D:/.ivy2
-Dsbt.repository.config=D:/scala/sbt-1.2.8/conf/repo.properties
-Dsbt.repository.secure=false
4. 配置repo.properties
[repositories]
  local
  aliyun: http://maven.aliyun.com/nexus/content/groups/public/
  typesafe: http://repo.typesafe.com/typesafe/ivy-releases/, [organization]/[module]/(scala_[scalaVersion]/)(sbt_[sbtVersion]/)[revision]/[type]s/[artifact](-[classifier]).[ext], bootOnly
  sonatype-oss-releases
  maven-central
  sonatype-oss-snapshots
