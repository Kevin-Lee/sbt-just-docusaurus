# sbt-docusaur
sbt plugin for Docusaurus


[![Build Status](https://github.com/Kevin-Lee/sbt-docusaur/workflows/Build%20All/badge.svg)](https://github.com/Kevin-Lee/sbt-docusaur/actions?workflow=Build+All)
[![Release Status](https://github.com/Kevin-Lee/sbt-docusaur/workflows/Release/badge.svg)](https://github.com/Kevin-Lee/sbt-docusaur/actions?workflow=Release)
[ ![Download](https://api.bintray.com/packages/kevinlee/sbt-plugins/sbt-docusaur/images/download.svg) ](https://bintray.com/kevinlee/sbt-plugins/sbt-docusaur/_latestVersion)


> **NOTE: sbt-docusaur hasn't been released yet**
> 
> **More detailed docs will be added once it's released.**

```sbt
addSbtPlugin("io.kevinlee" % "sbt-docusaur" % "0.1.0")
```

```sbt
lazy val root = (project in file("."))
  .enablePlugins(DocusaurPlugin)
  .settings(
    organization := "com.some.org",
    name         := "project-name",
    docusaurDir := (ThisBuild / baseDirectory).value / "website",
    docusaurBuildDir := docusaurDir.value / "build",
    gitHubPagesOrgName := "github-username",
    gitHubPagesRepoName := "project-name"
  )
```

```sbt
sbt:project-name> docusaurInstall
[info] Successfully run npm for Docusaurus install
[info]   - command: npm run install
[info]
[info]   > fsevents@1.2.13 install /path/to/project-name/website/node_modules/watchpack-chokidar2/node_modules/fsevents
[info]   > node install.js
[info]
[info]     SOLINK_MODULE(target) Release/.node
[info]     CXX(target) Release/obj.target/fse/fsevents.o
[info]     SOLINK_MODULE(target) Release/fse.node
[info]
[info]   > fsevents@1.2.13 install /path/to/project-name/website/node_modules/webpack-dev-server/node_modules/fsevents
[info]   > node install.js
[info]
[info]     SOLINK_MODULE(target) Release/.node
[info]     CXX(target) Release/obj.target/fse/fsevents.o
[info]     SOLINK_MODULE(target) Release/fse.node
[info]
[info]   > core-js@2.6.11 postinstall /path/to/project-name/website/node_modules/core-js
[info]   > node -e "try{require('./postinstall')}catch(e){}"
[info]
[info]   Thank you for using core-js ( https://github.com/zloirock/core-js ) for polyfilling JavaScript standard library!
[info]
[info]   The project needs your help! Please consider supporting of core-js on Open Collective or Patreon:
[info]   > https://opencollective.com/core-js
[info]   > https://www.patreon.com/zloirock
[info]
[info]   Also, the author of core-js ( https://github.com/zloirock ) is looking for a good job -)
[info]
[info]
[info]   > ejs@2.7.4 postinstall /path/to/project-name/website/node_modules/ejs
[info]   > node ./postinstall.js
[info]
[info]   Thank you for installing EJS: built with the Jake JavaScript build tool (https://jakejs.com/)
[info]
[info]   added 1603 packages from 672 contributors and audited 1604 packages in 30.257s
[info]
[info]   122 packages are looking for funding
[info]     run `npm fund` for details
[info]
[info]   found 0 vulnerabilities
[info]
[info]
[success] Total time: 32 s, completed 27 Jun. 2020, 5:52:58 pm

```

```sbt
sbt:project-name> docusaurBuild
[info] Successfully run npm for Docusaurus build
[info]   - command: npm run run build
[info]
[info]   > website@0.0.0 build /path/to/project-name/website
[info]   > docusaurus build
[info]
[info]   Creating an optimized production build...
[info]   ℹ Compiling Client
[info]   ℹ Compiling Server
[info]   ✔ Client: Compiled successfully in 10.70s
[info]   ✔ Server: Compiled successfully in 12.74s
[info]
[info]   Success! Generated static files in build.
[info]
[info]
[success] Total time: 16 s, completed 27 Jun. 2020, 5:55:15 pm

```

```sbt
sbt:project-name> publishToGitHubPages
```
