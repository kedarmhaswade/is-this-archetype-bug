# is-this-archetype-bug
As a good citizen, I tried to create a "test-case" that is easily reproducible.

# Details
I want to create an app whose structure is somewhat different than the traditional Java project. It's not much different, but just has
this structure:
```
<project-root>
    | --- Readme.md
    | --- Readme.developer.md
    | --- dxapp.json
    | --- pom.xml
    | --- src (the conventional sources, Java and test)
```
So, I created the structure like:
```
├── src
│   ├── main
│   │   └── resources
│   │       ├── META-INF
│   │       │   └── maven
│   │       │       └── archetype-metadata.xml
│   │       └── archetype-resources
│   │           ├── Readme.developer.md
│   │           ├── Readme.md
│   │           ├── dxapp.json
│   │           ├── pom.xml
│   │           └── src
│   │               ├── main
│   │               │   ├── java
│   │               │   │   └── main
│   │               │   │       └── __mainRunner__.java
│   │               │   └── resources
│   │               │       └── logback.xml
│   │               └── test
│   │                   ├── java
│   │                   │   └── main
│   │                   │       └── __mainRunner__Test.java
│   │                   └── resources

```
And I added the relevant line in this line [archetype descriptor's fileset](https://github.com/kedarmhaswade/is-this-archetype-bug/blob/master/src/main/resources/META-INF/maven/archetype-metadata.xml#L18).

And I believe this is the bug.
