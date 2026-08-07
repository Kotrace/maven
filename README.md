# luxgroup-maven

A static [Maven repository](https://maven.apache.org/) served over GitHub Pages at
**`https://maven.luxgroup.dev`**. Anonymous pull — no credentials.

## Consume

```kotlin
// settings.gradle.kts
dependencyResolutionManagement {
    repositories {
        maven { url = uri("https://maven.luxgroup.dev") }
    }
}
// build.gradle.kts
implementation("dev.luxgroup:kotrace:0.1.0")
```

## Contents

| Artifact | Source repo |
|---|---|
| `dev.luxgroup:kotrace` | [`Kotrace/kotrace`](https://github.com/Kotrace/kotrace) |

## Publish into it

From a source repo's build, point `maven-publish` at a local checkout of this repo and publish, then
commit + push here. GitHub Pages serves the new files. Example (kotrace):

```bash
./gradlew publishAllPublicationsToLuxGroupMavenRepository -Pkotrace.maven.repo.dir=/path/to/this/checkout
```

`CNAME` pins the custom domain; `.nojekyll` stops GitHub Pages from hiding the `_`-prefixed metadata.