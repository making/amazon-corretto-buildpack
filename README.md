# amazon-corretto-buildpack

## How to use Amazon Corretto with Cloud Foundry Java Buildpack

Use online buildpack and spefify `https://raw.githubusercontent.com/making/amazon-corretto-buildpack/master` to the JRE `repository_root`.

``` yaml
applications:
- name: demo-correto
  path: target/demo-corretto-0.0.1-SNAPSHOT.jar
  buildpacks:
  # online buildpack
  - https://github.com/cloudfoundry/java-buildpack.git#v4.17.2
  env:
    JBP_CONFIG_OPEN_JDK_JRE: '{ jre: { repository_root: "https://raw.githubusercontent.com/making/amazon-corretto-buildpack/master" } }'
```

Correto 8 is used by default as of Java Buildpack 4.17. If you prefer Corretto 11, configure `version`.

```yaml
applications:
- name: demo-correto
  path: target/demo-corretto-0.0.1-SNAPSHOT.jar
  buildpacks:
  - https://github.com/cloudfoundry/java-buildpack.git#v4.17.2
  env:
    JBP_CONFIG_OPEN_JDK_JRE: '{ jre: { version: 11.+, repository_root: "https://raw.githubusercontent.com/making/amazon-corretto-buildpack/master" } }'
```
