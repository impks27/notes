# notes

The Gradle Daemon is enabled by default since version 3.0. However, the official documentation https://docs.gradle.org/4.2/userguide/gradle_daemon.html#when_should_i_not_use_the_gradle_daemon until 4.2.1 stated that you shouldn't use the daemon in continuous integration servers.

It is recommended that the Daemon is used in all developer environments. It is recommend to disable the Daemon for Continuous Integration and build server environments.

The Daemon enables faster builds, which is particularly important when a human is sitting in front of the build. For CI builds, stability and predictability is of utmost importance. Using a fresh runtime (i.e. process) for each build is more reliable as the runtime is completely isolated from previous builds.

This recommendations has changed since then, see Disabling the Daemon https://docs.gradle.org/4.4.1/userguide/gradle_daemon.html#sec:disabling_the_daemon

Since Gradle 3.0, we enable Daemon by default and recommend using it for both developers' machines and Continuous Integration servers. However, if you suspect that Daemon makes your CI builds unstable, you can disable it to use a fresh runtime for each build since the runtime is completely isolated from any previous builds.
