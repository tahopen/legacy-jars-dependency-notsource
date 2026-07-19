# Tahopen Legacy Jars Dependency (Not Source)

This repository serves as a centralized private collection of legacy JAR files and their corresponding POM definitions. These artifacts are either no longer available in standard public Maven repositories (like Maven Central) or have become difficult to resolve due to broken transitive dependencies in the Pentaho/Eclipse ecosystems.

## Purpose
Some projects within the **TahOpen** ecosystem rely on specific versions of legacy dependencies—such as early SWT versions or proprietary Pentaho-specific builds—that are critical for Java 11 compatibility. 

Instead of relying on manual, inconsistent installations into local `.m2` folders, this repository acts as a **Source of Truth** for these missing artifacts, ensuring reproducible builds across different development environments.

## How to Use

### Option 1: Local Installation (Recommended for Development)
To register these artifacts into your local Maven cache so they are treated as official dependencies, use the following command pattern for each JAR:

```bash
mvn install:install-file \
   -Dfile=./path/to/jar/filename.jar \
   -DgroupId=[GROUP_ID] \
   -DartifactId=[ARTIFACT_ID] \
   -Dversion=[VERSION] \
   -Dpackaging=jar \
   -DgeneratePom=true
