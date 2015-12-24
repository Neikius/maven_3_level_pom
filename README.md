# maven_3_level_pom

Two different 3 level examples:

*Three level pom hierarchy, mvn install on 0 and 1, then mvn help:effective-pom on 2, all works
testSuperPom_level{0|1|2}


*Three level pom hierarchy, super.pom references org.eclipse.scout:maven_rt_plugin_config-master:2.0; l2.pom references super.pom;
after doing mvn install on super.pom doing mvn help:effective-pom on l2.pom project yields a result that is missing <pluginManagement> section from maven_rt_plugin_config-master.
Funnily enough the "correct" effective pom is shown in the eclipse pom editor, while maven seems to do it differently and hence l2 project is useless regarding build plugins.
test.{super|l2}.pom
