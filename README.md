# eclipselink-logsep

Patched EclipseLink 2.7.14 jar with custom SQL bind parameter separator.

## Base Artifact

Original dependency:

```xml
<dependency>
    <groupId>org.eclipse.persistence</groupId>
    <artifactId>eclipselink</artifactId>
    <version>2.7.14</version>
</dependency>
```

## Fork Version

`2.7.14-fork2`

## Custom Changes

Modified class:

```text
org.eclipse.persistence.internal.databaseaccess.DatabaseCall
```

Modified method:

```text
appendLogParameters(...)
```

### Change

Bind parameters in EclipseLink SQL logs are separated using:

```text
\u07aa
```

instead of the default:

```text
", "
```

### Reason

The default comma separator makes automated log parsing difficult because commas may also appear inside text values.

Using a dedicated separator simplifies reliable parsing of SQL bind parameters in log output.

## Patch Documentation

The source modification is documented in:

```text
patches/DatabaseCall.patch
```

## Maven / JitPack

Repository:

```xml
<repositories>
    <repository>
        <id>jitpack.io</id>
        <url>https://jitpack.io</url>
    </repository>
</repositories>
```

Dependency:

```xml
<dependency>
    <groupId>com.github.HannesSchmidt1337</groupId>
    <artifactId>eclipselink-logsep</artifactId>
    <version>v2.7.14-fork2</version>
</dependency>
```
