# scala sbt manual 手册
# 一、下载scala
## 1. <a>https://www.scala-lang.org/<a>，两种方式一种是Scala IDE，一种是SBt，我选择后者<a>https://www.scala-sbt.org/1.x/docs/Installing-sbt-on-Windows.html</a>
## 2. 解压sbt-1.2.8，配置环境变量
## 3. 配置sbt工作目录和aliyun的ivy2仓库，在conf/sbtconfig.txt下面
-Dsbt.boot.directory=D:/scala/sbt-1.2.8/.sbt/boot
-Dsbt.global.base=D:/scala/sbt-1.2.8/data/.sbt
-Dsbt.ivy.home=D:/.ivy2
-Dsbt.repository.config=D:/scala/sbt-1.2.8/conf/repo.properties
-Dsbt.repository.secure=false
## 4. 配置repo.properties
[repositories]
  local
  aliyun: http://maven.aliyun.com/nexus/content/groups/public/
  typesafe: http://repo.typesafe.com/typesafe/ivy-releases/, [organization]/[module]/(scala_[scalaVersion]/)(sbt_[sbtVersion]/)[revision]/[type]s/[artifact](-[classifier]).[ext], bootOnly
  sonatype-oss-releases
  maven-central
  sonatype-oss-snapshots

# Create the project
cd to an empty folder.
Run the following command sbt new scala/hello-world.g8. This pulls the ‘hello-world’ template from GitHub. It will also create a target folder, which you can ignore.
When prompted, name the application hello-world. This will create a project called “hello-world”.
Let’s take a look at what just got generated:
- hello-world
    - project (sbt uses this to install manage plugins and dependencies)
        - build.properties
    - src
        - main
            - scala (All of your scala code goes here)
                -Main.scala (Entry point of program) <-- this is all we need for now
    build.sbt (sbt's build definition file)

# Running the project
cd into hello-world.
Run sbt. This will open up the sbt console.
Type ~run. The ~ is optional and causes sbt to re-run on every file save, allowing for a fast edit/run/debug cycle. sbt will also generate a target directory which you can ignore.
Modifying the code
Open the file src/main/scala/Main.scala in your favorite text editor.
Change “Hello, World!” to “Hello, New York!”
If you haven’t stopped the sbt command, you should see “Hello, New York!” printed to the console.
You can continue to make changes and see the results in the console.
# Adding a dependency
Open up build.sbt and add the following line:
libraryDependencies += "org.scala-lang.modules" %% "scala-parser-combinators" % "1.1.0"
