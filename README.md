# 🦫 Prometheus for Ktor Servers
> *Prometheus implementation to be used with Ktor servers.*
>
> [:scroll: **Documentation**](https://auguwu.github.io/ktor-prometheus)

<!-- [:scroll: **Documentation**](https://docs.floofy.dev/libs/ktor/prometheus/api) -->

## What is this?
This is a simple plugin to implement Prometheus metrics with the Prometheus Java clients, since I find it way easier to create gauges, counters, histograms, etc with the official Java clients.

## Example
```ktor
import dev.floofy.ktor.plugins.prometheus.Prometheus

fun Application.module() {
  routing {}
  
  install(Prometheus) {
    registry = MyCollectorRegistry() // uses the default collector registry
    
    addCounters(
      Counter.builder()
        .name("owo.da.uwu")
        .description("owo da uwus!")
    )
  }
}
```

This will install the **PrometheusRegistry** which is used to fetch the counters, gauges, histograms, and more and it will create a route to scrape the metrics.

# Installation
## Gradle
### Kotlin DSL
```kotlin
repositories {
    maven {
        url = uri("https://maven.floofy.dev/repo/releases")
    }
}

dependencies {
    implementation("dev.floofy.ktor:plugin-prometheus:<VERSION>")
}
```

### Groovy DSL
```groovy
repositories {
    maven {
        url "https://maven.floofy.dev/repo/releases"
    }
}

dependencies {
    implementation "dev.floofy.ktor:plugin-prometheus:<VERSION>"
}
```

## Maven
```xml
<repositories>
    <repository>
        <id>noel-maven</id>
        <url>https://maven.floofy.dev/repo/releases</url>
    </repository>
</repositories>
```

```xml
<dependencies>
    <dependency>
        <groupId>dev.floofy.ktor</groupId>
        <artifactId>prometheus-plugin</artifactId>
        <version>{{VERSION}}</version>
        <type>pom</type>
    </dependency>
</dependencies>
```

## License
**ktor-prometheus** is released under the **MIT License** with love (* ^ ω ^) by **Noel**. 💜
