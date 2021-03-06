pyhttpcap
=========

解析和显示pcap格式中的http数据包内容

pyhttpcap是一个用python编写的分析pcap格式文件中http数据包的脚本，它会忽略非TCP/HTTP的数据包。
它可以对http请求/响应按TCP连接进行分组，显示http包的包头和包体内容，自动处理chunked/gzip，自动转换字符编码。

使用：
=========
假设使用tcpdump抓包：
+ tcpdump -wtest.pcap tcp port 80

那么：
+ pyhttp test.pcap    //列出所有http请求
+ pyhttp -v test.pcap    //同时输出http req/resp head
+ pyhttp -vv test.pcap   //同事输出http req/resp 文本类型的包体

此外，可以使用-p, -i指定源和目标的ip/端口，这是只输出符合指定条件的数据:
+ pyhttp -p55419 -vv test.pcap
+ pyhttp -i192.168.109.91 -vv test.pcap

使用-d输出抓到的package 信息:
+ pyhttp -p55419 -vvd test.pcap

使用-e指定http包体的编码
+ pyhttp -i192.168.109.91 -p80 -vv -eutf-8 -vv test.pcap

附带一个arm指令集的tcpdump，可用于android手机抓包.


Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. <br />

You may obtain a copy of the License at
> http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License. <br />
