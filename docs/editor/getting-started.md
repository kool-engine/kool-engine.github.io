---
layout: default
title: Getting Started
parent: Editor
nav_order: 1
---

# Getting Started
{: .fs-9 .no_toc }

[Launch the web-editor][web-editor]{: .btn .btn-primary .fs-5 .mb-4 .mt-4 }

The editor runs locally in the JVM as well as in the browser. The [web-version][web-editor] offers the one-click solution
for getting started with the editor. However, since the web-version can't compile any code, you should use the
JVM version for any serious testing. You can still start with the web-version and use the `Save Project` button
in the upper right corner to download the example project, which you can then run locally. Alternatively you can
clone the [kool templates] and use the `kool-editor-template` as a starting point.

{: .warning }
The editor is still in an early state and I can't yet guarantee any backwards compatibility of future versions.
Hence, using it for serious projects is not yet recommended.

### Running the editor locally
The recommended workflow for an editor project is to open the downloaded project in [IntelliJ] (or any other
IDE of your choice) and run the kool editor in parallel. To do so, open the previously downloaded project in
IntelliJ and wait until the gradle build-script is synced (it should happen automatically).

Now start the kool editor by running the `runEditor` gradle task either from the Gradle tab in IntelliJ or from
a terminal with: 
```sh
./gradlew runEditor
```
The editor should open up and you should see the same example scene as in the web-editor with the benefit that
you are able to edit code as well.


[web-editor]: https://kool-engine.github.io/live/kool-editor/
[kool templates]: https://github.com/kool-engine/kool-templates
[IntelliJ]: https://www.jetbrains.com/idea/download