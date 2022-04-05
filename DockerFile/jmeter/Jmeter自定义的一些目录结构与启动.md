### Dockered Jmeter自定义的一些目录结构

file directory in docker
* /jmeterdocker
* /jmeterdocker/test
* /jmeterdocker/test/input/jmx #jmx测试脚本
* /jmeterdocker/test/input/testdata #jmeter的测试数据
* /jmeterdocker/test/report/html #jmeter生成的html报告
* /jmeterdocker/test/report/jtl #jmeter生成的jtl报告
* /jmeterdocker/test/report/outputdata #jmeter生成的csv文件，某些测试用例会生成csv数据文件，这些数据文件会被其它测试用例使用

file directory in host 参照file directory in docker设置即可


***
### 启动dockered jmeter容器

```
docker run --name="jmeter1" --net="host" -v /tmp/jmeterspace/test/input/jmx:/jmeterdocker/test/input/jmx \
            -v /tmp/jmeterspace/test/input/testdata:/jmeterdocker/test/input/testdata \
            -v /tmp/jmeterspace/test/report/html:/jmeterdocker/test/report/html \
            -v /tmp/jmeterspace/test/report/jtl:/jmeterdocker/test/report/jtl \
            -v /tmp/jmeterspace/test/report/outputputdata:/jmeterdocker/test/report/outputdata \
            -it -d cxs1103/jmeter:v1.1
```