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

作成したjarは、デバック用途で以下のようにmavenで利用する。decompilerは別途自分で設定すること。

ライブラリをプロジェクトのlibsに配置する。

```
cp build/libs/jboss-all-in-one-for-debug-1.0.jar ${project.basedir}/libs
```

参考

```
     <dependency>
       <groupId>jboss-eap74-library</groupId>
       <artifactId>jboss-all-in-one-for-debug</artifactId>
       <version>1.0</version>
       <systemPath>${project.basedir}/libs/jboss-all-in-one-for-debug-1.0.jar</systemPath>
       <scope>system</scope>
     </dependency>
```


## 参考1

https://www.baeldung.com/gradle-fat-jar
