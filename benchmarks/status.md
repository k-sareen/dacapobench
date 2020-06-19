|bm | updated | jdk 8 | jdk 11 | clean | scratch | validation | small | default | large | huge | latency |
|-|-|-|-|-|-|-|-|-|-|-|-|
|avrora|✓|✓|✓|✓|✓|✓|✓|✓|✓|||
|batik|✓|✓|✓|✓|✓|✓|✓|✓|✓|✓||
|cassandra|✓|✓|✓|✓|✓|✓|✓|✓|✓||?|


### TODO
* Data is read only
  * check that benchmarks never write to dat director
* Packaging
  * Checksum all jars and data (not just huge)
  * Consider packaging everything aside from huge as a zip
  * have all within a folder of the same root name as the jar
  * have them all copied into place as part of the ant build
  * create a single dacapo zip that contains the jar, the dat and jar folders
* Cassandra: further calibration required.   Not clear that workload configs are affecting heap size.
* Eclipse
  * The data needs to be generated by the build, not pre-existing.
  * Current status (edef047):
    * Same version, but basically working out of data dir now
    * ant eclipse
    * cd clean/dat/eclipse
    * unzip ~/devel/dacapo/dacapobench/benchmarks/bms/eclipse/outdat/eclipse.zip 
    * unzip ~/devel/dacapo/dacapobench/benchmarks/bms/eclipse/data/dummyjre.zip 
    * mv jre/lib .
    * then it works fine and passes.