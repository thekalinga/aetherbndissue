aetherbndissue
==============

BND Aether integration issue using headless build


The dependency resolution works only in Eclipse, but the headless build
fails with the following exception

SLF4J: Failed to load class "org.slf4j.impl.StaticLoggerBinder".
SLF4J: Defaulting to no-operation (NOP) logger implementation
SLF4J: See http://www.slf4j.org/codes.html#StaticLoggerBinder for
further details.
[INFO] Scanning for projects...
[INFO] + D:\Fresh\com.acme.bnd.aether.issue
java.lang.ClassCastException: Cannot cast
org.apache.maven.repository.internal.DefaultVersionResolver to
org.eclipse.aether.impl.VersionResolver
at java.lang.Class.cast(Unknown Source)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.newInstance(DefaultServiceLocator.java:166)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstances(DefaultServiceLocator.java:139)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstance(DefaultServiceLocator.java:125)
at
org.eclipse.aether.impl.DefaultServiceLocator.getService(DefaultServiceLocator.java:288)
at
org.eclipse.aether.internal.impl.DefaultRepositorySystem.initService(DefaultRepositorySystem.java:145)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.newInstance(DefaultServiceLocator.java:169)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstances(DefaultServiceLocator.java:139)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstance(DefaultServiceLocator.java:125)
at
org.eclipse.aether.impl.DefaultServiceLocator.getService(DefaultServiceLocator.java:288)
at
aQute.bnd.deployer.repository.aether.AetherRepository.init(AetherRepository.java:176)
at
aQute.bnd.deployer.repository.aether.AetherRepository.get(AetherRepository.java:344)
at aQute.bnd.build.Project.getBundle(Project.java:917)
at aQute.bnd.build.Project.getBundles(Project.java:497)
at aQute.bnd.build.Project.parseBuildpath(Project.java:411)
at aQute.bnd.build.Project.prepare(Project.java:267)
at aQute.bnd.build.Project.getTarget(Project.java:1221)
at
aQute.bnd.mavenplugin.ConfigureMavenProject.transferBndProjectSettingsToMaven(ConfigureMavenProject.java:223)
at
aQute.bnd.mavenplugin.InitializeForBnd.afterProjectsRead(InitializeForBnd.java:56)
at org.apache.maven.DefaultMaven.doExecute(DefaultMaven.java:274)
at org.apache.maven.DefaultMaven.execute(DefaultMaven.java:156)
at org.apache.maven.cli.MavenCli.execute(MavenCli.java:537)
at org.apache.maven.cli.MavenCli.doMain(MavenCli.java:196)
at org.apache.maven.cli.MavenCli.main(MavenCli.java:141)
at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
at java.lang.reflect.Method.invoke(Unknown Source)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced(Launcher.java:290)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launch(Launcher.java:230)
at
org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode(Launcher.java:409)
at
org.codehaus.plexus.classworlds.launcher.Launcher.main(Launcher.java:352)
java.lang.IllegalArgumentException: version resolver has not been
specified
at
org.eclipse.aether.internal.impl.DefaultRepositorySystem.setVersionResolver(DefaultRepositorySystem.java:173)
at
org.eclipse.aether.internal.impl.DefaultRepositorySystem.initService(DefaultRepositorySystem.java:145)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.newInstance(DefaultServiceLocator.java:169)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstances(DefaultServiceLocator.java:139)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstance(DefaultServiceLocator.java:125)
at
org.eclipse.aether.impl.DefaultServiceLocator.getService(DefaultServiceLocator.java:288)
at
aQute.bnd.deployer.repository.aether.AetherRepository.init(AetherRepository.java:176)
at
aQute.bnd.deployer.repository.aether.AetherRepository.get(AetherRepository.java:344)
at aQute.bnd.build.Project.getBundle(Project.java:917)
at aQute.bnd.build.Project.getBundles(Project.java:497)
at aQute.bnd.build.Project.parseBuildpath(Project.java:411)
at aQute.bnd.build.Project.prepare(Project.java:267)
at aQute.bnd.build.Project.getTarget(Project.java:1221)
at
aQute.bnd.mavenplugin.ConfigureMavenProject.transferBndProjectSettingsToMaven(ConfigureMavenProject.java:223)
at
aQute.bnd.mavenplugin.InitializeForBnd.afterProjectsRead(InitializeForBnd.java:56)
at org.apache.maven.DefaultMaven.doExecute(DefaultMaven.java:274)
at org.apache.maven.DefaultMaven.execute(DefaultMaven.java:156)
at org.apache.maven.cli.MavenCli.execute(MavenCli.java:537)
at org.apache.maven.cli.MavenCli.doMain(MavenCli.java:196)
at org.apache.maven.cli.MavenCli.main(MavenCli.java:141)
at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
at java.lang.reflect.Method.invoke(Unknown Source)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced(Launcher.java:290)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launch(Launcher.java:230)
at
org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode(Launcher.java:409)
at
org.codehaus.plexus.classworlds.launcher.Launcher.main(Launcher.java:352)
[INFO]

[INFO]
------------------------------------------------------------------------
[INFO] Building com.acme.bnd.aether.issue 0.0.1-SNAPSHOT
[INFO]
------------------------------------------------------------------------
[INFO]
[INFO] --- bnd-maven-plugin:1.0.2:prepare (default-prepare) @
com.acme.bnd.aether.issue ---
java.lang.ClassCastException: Cannot cast
org.apache.maven.repository.internal.DefaultVersionResolver to
org.eclipse.aether.impl.VersionResolver
at java.lang.Class.cast(Unknown Source)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.newInstance(DefaultServiceLocator.java:166)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstances(DefaultServiceLocator.java:139)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstance(DefaultServiceLocator.java:125)
at
org.eclipse.aether.impl.DefaultServiceLocator.getService(DefaultServiceLocator.java:288)
at
org.eclipse.aether.internal.impl.DefaultRepositorySystem.initService(DefaultRepositorySystem.java:145)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.newInstance(DefaultServiceLocator.java:169)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstances(DefaultServiceLocator.java:139)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstance(DefaultServiceLocator.java:125)
at
org.eclipse.aether.impl.DefaultServiceLocator.getService(DefaultServiceLocator.java:288)
at
aQute.bnd.deployer.repository.aether.AetherRepository.init(AetherRepository.java:176)
at
aQute.bnd.deployer.repository.aether.AetherRepository.get(AetherRepository.java:344)
at aQute.bnd.build.Project.getBundle(Project.java:917)
at aQute.bnd.build.Project.getBundles(Project.java:497)
at aQute.bnd.build.Project.parseBuildpath(Project.java:411)
at aQute.bnd.build.Project.prepare(Project.java:267)
at aQute.bnd.build.Project.getTarget(Project.java:1221)
at
aQute.bnd.mavenplugin.ConfigureMavenProject.transferBndProjectSettingsToMaven(ConfigureMavenProject.java:223)
at
aQute.bnd.mavenplugin.ConfigureMavenProject.execute(ConfigureMavenProject.java:61)
at
org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo(DefaultBuildPluginManager.java:101)
at
org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:209)
at
org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:153)
at
org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:145)
at
org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject(LifecycleModuleBuilder.java:84)
at
org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject(LifecycleModuleBuilder.java:59)
at
org.apache.maven.lifecycle.internal.LifecycleStarter.singleThreadedBuild(LifecycleStarter.java:183)
at
org.apache.maven.lifecycle.internal.LifecycleStarter.execute(LifecycleStarter.java:161)
at org.apache.maven.DefaultMaven.doExecute(DefaultMaven.java:320)
at org.apache.maven.DefaultMaven.execute(DefaultMaven.java:156)
at org.apache.maven.cli.MavenCli.execute(MavenCli.java:537)
at org.apache.maven.cli.MavenCli.doMain(MavenCli.java:196)
at org.apache.maven.cli.MavenCli.main(MavenCli.java:141)
at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
at java.lang.reflect.Method.invoke(Unknown Source)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced(Launcher.java:290)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launch(Launcher.java:230)
at
org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode(Launcher.java:409)
at
org.codehaus.plexus.classworlds.launcher.Launcher.main(Launcher.java:352)
java.lang.IllegalArgumentException: version resolver has not been
specified
at
org.eclipse.aether.internal.impl.DefaultRepositorySystem.setVersionResolver(DefaultRepositorySystem.java:173)
at
org.eclipse.aether.internal.impl.DefaultRepositorySystem.initService(DefaultRepositorySystem.java:145)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.newInstance(DefaultServiceLocator.java:169)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstances(DefaultServiceLocator.java:139)
at
org.eclipse.aether.impl.DefaultServiceLocator$Entry.getInstance(DefaultServiceLocator.java:125)
at
org.eclipse.aether.impl.DefaultServiceLocator.getService(DefaultServiceLocator.java:288)
at
aQute.bnd.deployer.repository.aether.AetherRepository.init(AetherRepository.java:176)
at
aQute.bnd.deployer.repository.aether.AetherRepository.get(AetherRepository.java:344)
at aQute.bnd.build.Project.getBundle(Project.java:917)
at aQute.bnd.build.Project.getBundles(Project.java:497)
at aQute.bnd.build.Project.parseBuildpath(Project.java:411)
at aQute.bnd.build.Project.prepare(Project.java:267)
at aQute.bnd.build.Project.getTarget(Project.java:1221)
at
aQute.bnd.mavenplugin.ConfigureMavenProject.transferBndProjectSettingsToMaven(ConfigureMavenProject.java:223)
at
aQute.bnd.mavenplugin.ConfigureMavenProject.execute(ConfigureMavenProject.java:61)
at
org.apache.maven.plugin.DefaultBuildPluginManager.executeMojo(DefaultBuildPluginManager.java:101)
at
org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:209)
at
org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:153)
at
org.apache.maven.lifecycle.internal.MojoExecutor.execute(MojoExecutor.java:145)
at
org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject(LifecycleModuleBuilder.java:84)
at
org.apache.maven.lifecycle.internal.LifecycleModuleBuilder.buildProject(LifecycleModuleBuilder.java:59)
at
org.apache.maven.lifecycle.internal.LifecycleStarter.singleThreadedBuild(LifecycleStarter.java:183)
at
org.apache.maven.lifecycle.internal.LifecycleStarter.execute(LifecycleStarter.java:161)
at org.apache.maven.DefaultMaven.doExecute(DefaultMaven.java:320)
at org.apache.maven.DefaultMaven.execute(DefaultMaven.java:156)
at org.apache.maven.cli.MavenCli.execute(MavenCli.java:537)
at org.apache.maven.cli.MavenCli.doMain(MavenCli.java:196)
at org.apache.maven.cli.MavenCli.main(MavenCli.java:141)
at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
at sun.reflect.NativeMethodAccessorImpl.invoke(Unknown Source)
at sun.reflect.DelegatingMethodAccessorImpl.invoke(Unknown Source)
at java.lang.reflect.Method.invoke(Unknown Source)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launchEnhanced(Launcher.java:290)
at
org.codehaus.plexus.classworlds.launcher.Launcher.launch(Launcher.java:230)
at
org.codehaus.plexus.classworlds.launcher.Launcher.mainWithExitCode(Launcher.java:409)
at
org.codehaus.plexus.classworlds.launcher.Launcher.main(Launcher.java:352)
[INFO] [bnd] classpath [osgi:classes:jar:project:system]
[INFO]
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @
com.acme.bnd.aether.issue ---
[WARNING] Using platform encoding (Cp1252 actually) to copy filtered
resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory
D:\Fresh\com.acme.bnd.aether.issue\src\main\resources
[INFO]
[INFO] --- maven-compiler-plugin:3.1:compile (default-compile) @
com.acme.bnd.aether.issue ---
[INFO] Nothing to compile - all classes are up to date
[INFO]
[INFO] --- maven-resources-plugin:2.6:testResources
(default-testResources) @ com.acme.bnd.aether.issue ---
[WARNING] Using platform encoding (Cp1252 actually) to copy filtered
resources, i.e. build is platform dependent!
[INFO] skip non existing resourceDirectory
D:\Fresh\com.acme.bnd.aether.issue\src\test\resources
[INFO]
[INFO] --- maven-compiler-plugin:3.1:testCompile (default-testCompile) @
com.acme.bnd.aether.issue ---
[INFO] No sources to compile
[INFO]
[INFO] --- maven-surefire-plugin:2.17:test (default-test) @
com.acme.bnd.aether.issue ---
[INFO]
[INFO] --- bnd-maven-plugin:1.0.2:bundle (default-bundle) @
com.acme.bnd.aether.issue ---
[ERROR] Workspace -----------------
Errors
000: Service creation failed for type interface
org.eclipse.aether.impl.VersionResolver using impl class
org.apache.maven.repository.internal.DefaultVersionResolver: Cannot cast
org.apache.maven.repository.internal.DefaultVersionResolver to
org.eclipse.aether.impl.VersionResolver
001: Service creation failed for type interface
org.eclipse.aether.RepositorySystem using impl class
org.eclipse.aether.internal.impl.DefaultRepositorySystem: version
resolver has not been specified

[ERROR] [E0] Service creation failed for type interface
org.eclipse.aether.impl.VersionResolver using impl class
org.apache.maven.repository.internal.DefaultVersionResolver: Cannot cast
org.apache.maven.repository.internal.DefaultVersionResolver to
org.eclipse.aether.impl.VersionResolver
[ERROR] [E1] Service creation failed for type interface
org.eclipse.aether.RepositorySystem using impl class
org.eclipse.aether.internal.impl.DefaultRepositorySystem: version
resolver has not been specified
[ERROR] Project com.acme.bnd.aether.issue
[ERROR] [E0] Unexpected
commons-io:commons-io;version=2.4;strategy=exact,commons-daemon:commons-daemon;version=1.0.1,junit;version=latest,hamcrest-core;version=latest,
error java.lang.IllegalArgumentException: Failed to initialise Aether
repository system,
[ERROR] [W0] The JAR is empty: The instructions for the JAR named
com.acme.bnd.aether.issue did not cause any content to be included, this
is likely wrong
[INFO]
------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO]
------------------------------------------------------------------------
[INFO] Total time: 3.095s
[INFO] Finished at: Fri Aug 22 15:57:25 EDT 2014
[INFO] Final Memory: 19M/155M
[INFO]
------------------------------------------------------------------------
[ERROR] Failed to execute goal
biz.aQute.bnd:bnd-maven-plugin:1.0.2:bundle (default-bundle) on project
com.acme.bnd.aether.issue: Problem building the project. Project
com.acme.bnd.aether.issue has failed -> [Help 1]
[ERROR]
[ERROR] To see the full stack trace of the errors, re-run Maven with the
-e switch.
[ERROR] Re-run Maven using the -X switch to enable full debug logging.
[ERROR]
[ERROR] For more information about the errors and possible solutions,
please read the following articles:
[ERROR] [Help 1]
http://cwiki.apache.org/confluence/display/MAVEN/MojoExecutionException
