---
title: Oracle操作之--表空间
date: 2017-12-20 12:42:01
tags: Oracle
---
* 创建表空间：
<pre><code>create tablespace spacename//表空间名字 datafile 'filename.dbf'//数据文件名字 size 10M;</code></pre>

* 创建完成后查询：
<pre><code>select tablespace_name from dba_tablespaces where tablespace_name='SPACENAME';</code></pre>

* 查询表空间的状态：
<pre><code>select status from dba_tablespaces where tablespace_name='SPACENAME';</code></pre>

* 修改表空间的状态：
<pre><code>alter tablespace SPACENAME read only/read write</code></pre>

* 添加数据文件：
<pre><code>alter tablespace SPACENAME add datafile 'test2_datafile.dbf' size 10M;</code></pre>

* 删除数据文件：
<pre><code>alter tablespace SPACENAME drop datafile 'test2_datafile.dbf';</code></pre>

* 删除表空间：
<pre><code>drop tablespace SPACENAME including contents;//including contents目的是一并删除表空间里面的数据文件</code></pre>
