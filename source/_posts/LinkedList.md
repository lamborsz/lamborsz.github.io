---
title: 集合之--LinkedList操作
date: 2017-12-18 09:38:51
tags: Java集合
---


*	插入元素
  >逐条加入
	<pre><code>LinkedList<String> list = new LinkedList<>();
	list.add("lambo");</code></pre>

	>在指定地点插入元素
	<pre><code>LinkedList<String> list = new LinkedList<>();
	list.add(0,"lambo");</code></pre>

	>将另外一个LinkedList的内容添加到当前LinkedList中
	<pre><code>LinkedList<String> list2 = new LinkedList<>();
	list2.addAll(list);
	</code></pre>

	>在头部或者尾部加入元素
  <pre><code>LinkedList<String> list = new LinkedList<>();
	list.addFirst("lambo");
	list.addLast("lambosz");</code></pre>

	>other
	<pre><code>LinkedList同样支持clone(),将一个LinkedList复制给另一个LinkedList
	list2 = (LinedList<String>) list.clone();</code></pre>

* 删除元素

	>移除指定位置的元素
	<pre><code>list.remove(0);</code></pre>

	>清除整个LinkedList
	<pre><code>list.clear();</code></pre>

	>移除首部或尾部的元素
	<pre><code>list.removeFirst();
	list.removeLast();</code></pre>

	>移除第一个或最后一个值为指定值的元素
	<pre><code>list.removeFirstOccurrence("lambo");
	list.removeLastOccurrence("lambo");</code></pre>
* 遍历

	>迭代器遍历
	<pre><code>LinkedList<Integer> list = new LinkedList<>();
	for(int i = 0;i < 10000 ;i++){
	    list.add(i);
	}
	Iterator<Integer> iterator = list.iterator();
	while(iterator.hasNext()){
	    iterator.next();
	}</code></pre>

	>for循环遍历
	<pre><code>for(int j = 0;j<list.size();j++){
	    list.get(i);
	}</code></pre>

	>for each循环遍历
	<pre><code>for(Integer i:list){
	    list.get(i)
	}</code></pre>

	>其他遍历
	<pre><code>LinkedList<Integer> list2 = new LinkedList<>();
	list2.addAll(list);
	while(list2.size()!=0){
	    list2.pollFirst();
	}//使用pollFirst()或者pollLast()来遍历</code></pre>
  <pre><code>LinkedList<Integer> list3 = new LinkedList<>();
	list3.addAll(list);
	while(list3.size()!=0){
		 list3.removeFirst();
	}//使用removeFirst()或者removeLast()来遍历</code></pre>

* 总结

	>LinkedList包含了一个index和一个element，index用来指向位置，element用来存放内容，所以在插入删除的时候能通过index很快的找到插入删除点，**可以实现高效地插入删除**，并且每个element之间并不干扰，所以LinkedList的内容是**可以重复的**，并且有了index，所以同时它也是**有序的**


----------
承接自我上一篇博客[集合中的类](http://blog.csdn.net/Lamborghinsz/article/details/78580985)，接下来会继续展开
