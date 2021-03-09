# Guion
Guion is a fork of [Skript](https://github.com/SkriptLang/Skript) whose target is to enable experimental features to be part of it at the cost of stability.

## Requirements
Guion requires **Paper** to work. Unlike Skript, Spigot is not supported, though, it may still run on it.

Guion supports only the **latest** patch versions of Minecraft 1.13+.
For example, this means that 1.16.5 is supported, but 1.16.4 is *not*.
Testing with all old patch versions is not feasible for us.

Minecraft 1.12 and earlier are not, and will not be supported. New Minecraft
versions will be supported as soon as possible.

## Download
Guion uses a rolling release cycle, you'll find an artifact on the actions tab, at the latest commit build.

## Documentation
Documentation for Guion is not yet available.

## Reporting Issues
Please see [contribution guidelines](https://github.com/FranKusmiruk/Guion/blob/master/.github/contributing.md)
before reporting issues.

## A Note About Add-ons
Addons are not supported, and considering Guion's target, API is bound to actively change so compatibility with Skript addons is not assured.

## Compiling
Guion uses Gradle for compilation. Use your command prompt of preference and
navigate to Guion's source directory. Then you can just call Gradle to compile
and package Skript for you:

```bash
./gradlew clean build # on UNIX-based systems (mac, linux)
gradlew clean build # on Windows
```

You can get source code by cloning this repository through Git.

### Testing
Guion has some tests written in Skript. Running them requires a Minecraft
server, but our build script can fetch it for you. Running tests is easy:

```
./gradlew (quickTest|skriptTest|skriptTestFull)
```

<code>quickTest</code> runs the test suite on newest supported server.
<code>skriptTest</code> additionally runs the tests on oldest supported
server. <code>skriptTestFull</code> runs tests on **ALL** supported versions.

By running tests, you agree to Mojang's End User License Agreement.

### Importing to Eclipse
With new Eclipse versions, there is integrated Gradle support, and it actually works now.
So, first get latest Eclipse, then import Guion as any Gradle project. Just
make sure to **keep** the configuration when the importer asks for that!

If you encounter strange issues, make sure you follow the instructions above and have
actually downloaded latest Eclipse or update your installation correctly.

### Importing to IDEA
You'll need to make sure that nullness annotations are working correctly. Also,
when sending pull requests, make sure not to change IDEA configuration files
that may have been stored in the repository.

## Contributing
Please review our [contribution guidelines](https://github.com/FranKusmiruk/Guion/blob/master/.github/contributing.md).
In addition to that, if you are contributing Java code, check our
[coding conventions](https://github.com/FranKusmiruk/Guion/blob/master/code-conventions.md).

## Maven Repository
If you use Skript as (soft) dependency for your plugin, and use maven or Gradle,
this is for you.

First, you need to add the JitPack repository at the **END** of all your repositories. Guion is not available in Maven Central.
```gradle
repositories {
    jcenter()
    ...
    maven {
        url 'https://jitpack.io'
    }
}
```

Or, if you use Maven:
```maven
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
</repositories>
```

Then you can add Guion as a dependency.
```gradle
dependencies {
    implementation 'com.github.FranKusmiruk:Guion:master'
}
```

> Note: If Gradle isn't able to resolve Guion's dependencies, just [disable the resolution of transitive dependencies](https://docs.gradle.org/current/userguide/managing_transitive_dependencies.html#sub:disabling_resolution_transitive_dependencies) for Guion in your project.

Or, if you use Maven:
```
<dependency>
    <groupId>com.github.FranKusmiruk.Guion</groupId>
    <artifactId>Guion</artifactId>
    <version>master</version>
</dependency>
```

## Relevant Links
* [SkriptLang's Skript](https://github.com/SkriptLang/Skript)
* [skUnity forums](https://forums.skunity.com)
* [Add-on releases at skUnity](https://forums.skunity.com/forums/addon-releases)
* [Skript Chat Discord invite](https://discord.gg/0lx4QhQvwelCZbEX)
* [Skript Hub](https://skripthub.net)
* [Original Skript at Bukkit](https://dev.bukkit.org/bukkit-plugins/skript) (inactive)

Note that these resources are not maintained by Skript's developers. Don't
contact us about any problems you might have with them.

## Developers
You can find all contributors [here](https://github.com/FranKusmiruk/Guion/graphs/contributors).

All code is owned by its writer, licensed for others under GPLv3 (see LICENSE)
unless otherwise specified.
