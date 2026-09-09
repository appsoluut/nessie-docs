## Setup

Distribution of Android libraries is done using a Maven server. The design system is divided
into four libraries.

### Fundamentals

The fundamentals include Color and Layout definitions for the design system.

### Typography

The typography includes the NSSans font and TextStyle definitions.

### Icons

The icons include all the icons and logos used by the design system.

### Components

The components include all the default components from the design system.

### Installation

To import the libraries you need to define the Maven repository in your `build.gradle`. This is
a private Maven server, for access details please contact us.

```groovy
repositories {
    google()
    mavenLocal()
    mavenCentral()
    maven {
        url = "https://nexus.topaas.ns.nl/repository/NS_DSM_MAVEN/"
    }
}
```

> **TIP:** To use snapshots instead of releases, change the maven URL to
> <https://nexus.topaas.ns.nl/repository/NS_DSM_MAVEN_Snapshots/>

To use the components declare the following dependency.

```groovy
dependencies {
    implementation "nl.ns.nessie:android-components:3.15.1"
}
```

If you want to make your own components using the fundamentals you can specify each library
separately. (All three are automatically included if you use the components).

```groovy
dependencies {
    api "nl.ns.nessie:android-fundamentals:3.15.1"
    api "nl.ns.nessie:android-typography:3.15.1"
    api "nl.ns.nessie:android-icons:3.15.1"
}
```

## Usage
Simply import the relevant package into your file.

```kotlin
import nl.ns.nessie.components.button.NesButton
```
