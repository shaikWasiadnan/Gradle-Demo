///Fatjar:
task fatJar(type: Jar) {
    manifest {
        attributes 'Main-Class': 'org.example.Main'(Name of main file)
    }

    duplicatesStrategy = DuplicatesStrategy.EXCLUDE

    from {
        configurations.runtimeClasspath.collect { it.isDirectory() ? it : zipTree(it) }
    }

    with jar
}
///Fat jar///

///Command to build normal jar --->   ./gradlew build       Then ./gradlew build/libs/name of .jar file

/// comands to build a fat jar ---->  ./gradlew fatjar      T5hen ./gradlew build/libs/name of .jar file

///Normal jar

jar{
 Manifest{
  attributes ('Main-Class': 'org.example.Main' (name of main class)
 }
}


/// Every time before building jar Clear the previous jar file with command  ./gradlew clean
