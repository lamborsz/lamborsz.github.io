---
title: Oracle操作之--表
date: 2017-12-20 12:30:29
tags: Oracle
---
*	创建：
>创建一个userinfo表，里面的字段有id,username,userpasswd
<pre><code>create table userinfo
(id number(6,0),
username varchar2(20),
userpasswd varchar2(20)
redate date);</code></pre>

  > 创建表的时候可以自己来指定表的表空间
  <pre><code>create table userinfo2
  (id number(6,0),
  username varchar2(20),
  userpasswd varchar2(20) tablespace sys);</code></pre>
  <br>如果不指定表空间，创建的表将默认为system表空间</br>
  <br>若创建表后想知道该表有哪些字段，可以使用desc userinfo查询</br>


* 修改：
>修改表名
<pre><code>rename userinfo to new_userinfo</code></pre>

  >修改表的字段名
<pre><code>alter table userinfo
rename column id to new_id;</code></pre>

	>在userinfo表中添加一个remarks字段
<pre><code>alter table userinfo
add remarks varchar2(500);</code></pre>

	>修改remarks字段的长度
  <pre><code>alter table userinfo
modify remarks varchar2(400);</code></pre>

* 删除：

	>删除字段
<pre><code>删除userinfo表中的remarks字段
	alter table userinfo
drop column remarks;</code></pre>

	>> 删除表
  表的截断,即删掉表中的全部数据，但是表还存在
<pre><code>truncate table userinfo</code></pre>

  >> 表的删除
<pre><code>drop table userinfo</code></pre>
