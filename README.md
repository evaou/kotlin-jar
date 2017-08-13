# Kotlin Jar
Create an executable Kotlin JAR via Gradle

### Implementation 
Add the following piece in *build.gradle*

    jar {
        manifest {
            attributes 'Main-Class': 'domoya.jar.MainKt'
        }
        from {
            configurations.compile.collect { it.isDirectory() ? it : zipTree(it) }
        }
    }

### How to run JAR 

    $ ./gradlew clean build 
    $ java -jar build/libs/kotlin-jar.jar
