# jboss-all-in-one-for-debug
jbossをデバックする際にクラスが見つからない場合があるため、module配下のすべてのjar(class)を一つのjarにする

gradle.propertiesにjbossのモジュールフォルダへのパスを設定する

```
$ cat gradle.properties 
jbossModuleHome=/home/hanzo/.jboss/jboss-eap-7.4/modules
```

module配下のすべてのjar(class)を一つのjarにする


```
gradle task createJar
```

## 参考1

https://www.baeldung.com/gradle-fat-jar
