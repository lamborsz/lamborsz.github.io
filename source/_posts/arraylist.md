---
title: 集合之--ArrayList操作
date: 2017-12-16 01:00:03
tags: Java集合
---


*	插入元素

	>逐条加入
	<pre><code>ArrayList<String> alist = new ArrayList();
	alist.add("lambo");</code></pre>

	>在指定地点加入
	<pre><code>alist.add(1,"lambo2")</code></pre>

  >将另一个ArrayList加入当前ArrayList
	<pre><code>ArrayList alist2 = new ArrayList();
    alist2.add("lambos");
    alist.addAll(alist2);</code></pre>

*	删除元素

  >删除对应位置的内容
    <pre><code>alist.remove(1);</code></pre>

  >删除整个ArrayList
	<pre><code>alist.clear();</code></pre>

  >按照条件删除对应字段
	<pre><code>alist.removeIf(str -> str.length() > 5)//这里删除的是长度5以上的字段，使用的是Lambda表达式，具体的Lambda以后在详细说明</code></pre>

*	遍历
>iterator遍历
	<pre><code>Iterator it = alist.iterator();
    while (it.hasNext()) {
        it.next();
    }</code></pre>

	>for循环遍历
	<pre><code>for (int i = 0; i < alist.size(); i++) {
            alist.get(i);
        }</code></pre>

  >for each循环遍历
	<pre><code>for (String s:alist) {
            System.out.println(s);
        }</code></pre>

*	总结
>ArrayList和LinkedList由于都是实现的List类，所以大部分操作都是类似的，熟悉了LinkedList的相关操作，ArrayList大部分也就都会了，但是这里要说明的这两个list的不同之处，方便在实际开发中进行选择
	>>ArrayList是**基于索引的数据结构**，通过索引来**读取数据比较快**，但ArrayList有个**扩容操作**，会消耗一定资源，并且对于**添加和删除效率比较差**，因为执行添加删除操作之后ArrayList要重新排布插入点或删除点后面的全部数据，越靠前，消耗越大。

	>>LinkedList是**基于链表的数据结构**，**读取数据是比较慢**，因为它要从第一个节点往后遍历，但是对于**插入删除数据，LinkedList是比较快的**，因为LinkedList的节点与节点之间是不连续的，是通过记录上一个节点和下一个节点将整个list串起来的，所以在执行插入删除操作时，只需要修改对应的上一个节点和下一个节点就好。
