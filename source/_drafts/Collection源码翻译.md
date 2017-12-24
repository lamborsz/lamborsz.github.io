---
title: Collection源码翻译
date: 2017-12-20 13:36:19
tags: Java集合
---
*	int size()
<pre><code>Returns the number of elements in this collection. If this collection contains more than <tt>Integer.MAX_VALUE</tt> elements, returns <tt>Integer.MAX_VALUE</tt></code></pre>

  <pre><code>return the number of elements in this collection</code></pre>

  <pre><code>返回collection中元素的个数,若这个collection包含超过Integer.MAX_VALUE这个常量的元素，则返回Integer.MAX_VALUE</code></pre>

  <pre><code>返回值：这个collection的元素个数</code></pre>

*	boolean isEmpty()
<pre><code>Returns <tt>true</tt> if this collection contains no elements.</code></pre>

  <pre><code>return <tt>true</tt> if this collection contains no elements</code></pre>

  <pre><code>当该collection没有元素的时候返回true</code></pre>

  <pre><code>返回值：当该collection没有包含元素的时候返回true</code></pre>

*	boolean contains(Object o)
<pre><code>Returns <tt>true</tt> if this collection contains the specified element. More formally, returns <tt>true</tt> if and only if this collection contains at least one element <tt>e</tt> such that <tt>(o==null&nbsp;?&nbsp;e==null&nbsp;:&nbsp;o.equals(e))</tt>.</code></pre>

  <pre><code>param **o** element whose presence in this collection is to be tested</code></pre>

  <pre><code>return <tt>true</tt> if this collection contains the specified element</code></pre>

  <pre><code>throws **ClassCastException** if the type of the specified element is incompatible with this collection</code></pre>

  <pre><code>throws **NullPointerException** if the specified element is null and this collection does not permit null elements</code></pre>

  <pre><code>当该collection包含特定的元素时返回true,正式的说法是，当且仅当该collection至少包含一个满足下列条件的e元素</code></pre>

  <pre><code>当o和e同时满足为null时为true，或者o!=null,且o.equals(e)为true则为true</code></pre>

  <pre><code>参数:o 是一个存在于该collection中被测试的元素</code></pre>

  <pre><code>返回值：当该collection包含这个规定的元素时，返回true</code></pre>

  >异常抛出：
  >> **ClassCastException** 当这个规定的元素的类型与该collection的类型不相符时抛</code></pre>

  >> **NullPointerException** 当这个规定的元素是null并且该collection并没有允许null元素时抛出</code></pre>

*	Iterator```<E>``` iterator();
<pre><code>Returns an iterator over the elements in this collection.  There are no guarantees concerning the order in which the elements are returned (unless this collection is an instance of some class that provides a guarantee).</code></pre>

  <pre><code>return an <tt>Iterator</tt> over the elements in this collection</code></pre>

  <pre><code>返回collection中元素的迭代器，没有关于元素返回顺序的保证，除非该collection是某些提供保证的类的实例</code></pre>

  <pre><code>返回值：一个该collection元素的迭代器</code></pre>

*	Object[] toArray()
<pre><code>Returns an array containing all of the elements in this collection. If this collection makes any guarantees as to what order its elements are returned by its iterator, this method must return the elements in the same order.</code></pre>

  <pre><code>The returned array will be "safe" in that no references to it are maintained by this collection.  (In other words, this method must allocate a new array even if this collection is backed by an array). The caller is thus free to modify the returned array.</code></pre>

  <pre><code>This method acts as bridge between array-based and collection-based APIs.</code></pre>

  <pre><code>return an array containing all of the elements in this collection</code></pre>

  <pre><code>返回包含此集合中所有元素的数组，如果这个集合保证了它的迭代器返回的元素顺序，这个方法必须以同样相同的顺序返回元素。</code></pre>

  <pre><code>返回的数组是安全的，因为这个集合没有引用它，（换句话说，即使这个集合是由数组支持的，这个方法也必须分配一个新的数组），调用者可以自由修改返回的数组。</code></pre>

  <pre><code>这个方法充当着基于数组和基于集合的API之间的桥梁</code></pre>

  <pre><code>返回值：一个包含该collection全部元素是数组</code></pre>

*	```<T>``` T[] toArray(T[] a)
<pre><code>Returns an array containing all of the elements in this collection; the runtime type of the returned array is that of the specified array. If the collection fits in the specified array, it is returned therein. Otherwise, a new array is allocated with the runtime type of the specified array and the size of this collection.</code></pre>

  <pre><code>If this collection fits in the specified array with room to spare (i.e., the array has more elements than this collection), the element in the array immediately following the end of the collection is set to <tt>null</tt>.  (This is useful in determining the length of this collection <i>only</i> if the caller knows that this collection does not contain any <tt>null</tt> elements.)</code></pre>

  <pre><code>If this collection makes any guarantees as to what order its elements are returned by its iterator, this method must return the elements in the same order.</code></pre>

  <pre><code>Like the {@link #toArray()} method, this method acts as bridge between array-based and collection-based APIs.  Further, this method allows precise control over the runtime type of the output array, and may, under certain circumstances, be used to save allocation costs.</code></pre>

  <pre><code>Suppose <tt>x</tt> is a collection known to contain only strings. The following code can be used to dump the collection into a newly allocated array of <tt>String</tt>:</code></pre>

  <pre><code><pre>String[] y = x.toArray(new String[0]);</code></pre>

  <pre><code>Note that <tt>toArray(new Object[0])</tt> is identical in function to <tt>toArray()</tt>.</code></pre>

  >param
  >> **```<T>```** the runtime type of the array to contain the collection</code></pre>

  >> **a** the array into which the elements of this collection are to be stored, if it is big enough; otherwise, a new array of the same runtime type is allocated for this purpose.</code></pre>

  <pre><code>return an array containing all of the elements in this collection</code></pre>

  >throws
  >> **ArrayStoreException** if the runtime type of the specified array is not a supertype of the runtime type of every element in this collection</code></pre>

  >> **NullPointerException** if the specified array is null</code></pre>

  <pre><code>返回一个包含该collection的全部元素的数组，返回的数组的运行时类型是规定的数组运行时类型如果该collection适合这个规定的数组，就返回进去，否则，将会根据规定数组的运行时类型和collection的大小重新分配一个数组</code></pre>

  <pre><code>如果这个collection适合规定的数组，并且还有空余的空间，例如（数组拥有比这个collection更多的元素）将collection结束之后的数组的元素设置为null这对确定这个collection的长度是很有用的，除非调用者知道该collection不包含任何null元素</code></pre>

  <pre><code>如果该collection根据迭代器对返回元素的顺序做了保证，那么该方法返回的元素顺序也必须一致</code></pre>

  <pre><code>像上一个toArray()方法一样，这个方法也是充当着基于数组和基于集合的API之间的桥梁，此外，该方法允许精准控制输出数组的运行时类型，并且，能在某些情况下可以节省分配成本</code></pre>

  <pre><code>假设x是已知只包含字符串的集合，以下代码可以将集合转存到新分配String数组中</code></pre>

  <pre><code>String[] x = x.toArray(new String[0]);</code></pre>

>注意toArray(new Object[0])在功能上与toArray()相同
>
>参数：
> >**```<T>```** 包含collection的数组的运行时类型
> >**a** 如果这个数组足够大，该collection的元素将会被存储，否则将为此重新分配一个相同运行时类型的数组
>
>返回值：一个包含了该collection全部元素的数组
>
>异常：
> >**ArrayStoreException** 如果指定数组的运行时类型不是该集合中每个元素的运行时类型的超类型，则抛出异常
> >**NullPointerException** 如果规定的数组为空，则抛出异常

*	boolean add(E e)
>Ensures that this collection contains the specified element (optional operation).  Returns <tt>true</tt> if this collection changed as a result of the call.  (Returns <tt>false</tt> if this collection does not permit duplicates and already contains the specified element.)
>
>Collections that support this operation may place limitations on what elements may be added to this collection.  In particular, some collections will refuse to add <tt>null</tt> elements, and others will impose restrictions on the type of elements that may be added. Collection classes should clearly specify in their documentation any restrictions on what elements may be added.
>
>If a collection refuses to add a particular element for any reason other than that it already contains the element, it <i>must</i> throw an exception (rather than returning <tt>false</tt>).  This preserves the invariant that a collection always contains the specified element after this call returns.
>
>param **e** element whose presence in this collection is to be ensured
>
>return <tt>true</tt> if this collection changed as a result of the call
>
>throws:
> >**UnsupportedOperationException** if the <tt>add</tt> operation is not supported by this collection
> >**ClassCastException** if the class of the specified element prevents it from being added to this collection
> >**NullPointerException** if the specified element is null and this collection does not permit null elements
> >**IllegalArgumentException** if some property of the element prevents it from being added to this collection
> >**IllegalStateException** if the element cannot be added at this time due to insertion restrictions
>
>确保该collection包含规定的元素（可选的操作），当该collection的结果因为调用而改变了的时候返回true，（当该collection不允许重复或者已经包含这个规定的元素的时候返回false）
>
>支持这个操作的collection可能会限制哪些元素可能被添加到这个collection中，具体来说，一些collection将拒绝添加null元素，而其他collection将对可能添加的元素类型进行限制，collection类应该在其文档中明确指定可以添加元素的任何限制
>
>如果一个collection因为除了它已经包含该元素之外的任何原因拒绝添加该元素，都必须抛出一个异常（而不是返回false），这可以让collection在调用这个返回值之后能一直包含这个规定的元素保持不变
>
>参数：**e** 在该collection中确保存在的元素
>
>返回值：如果该collection的结果按照调用的更改了则返回true
>
>异常：
> >**UnsupportedOperationException** 如果添加操作不被该collection支持，则抛出异常
> >**ClassCastException** 如果规定元素的类阻止将这个元素添加到collection中，则抛出异常
> >**NullPointerException** 如果规定元素为null并且这个collection不允许null元素，则抛出异常
> >**IllegalArgumentException** 如果一些元素的属性阻止将其添加到collection中，则抛出异常
> >**IllegalStateException** 如果这个元素在这个时间不能插入是由于插入限制，则抛出异常

*	boolean remove(Object o)
>Removes a single instance of the specified element from this collection, if it is present (optional operation).  More formally, removes an element <tt>e</tt> such that <tt>(o==null&nbsp;?&nbsp;e==null&nbsp;:&nbsp;o.equals(e))</tt>, if this collection contains one or more such elements.  Returns <tt>true</tt> if this collection contained the specified element (or equivalently, if this collection changed as a result of the call).
>
>param **o** element to be removed from this collection, if present
>
>return <tt>true</tt> if an element was removed as a result of this call
>
>throws:
>>**ClassCastException** if the type of the specified element is incompatible with this collection
>>**NullPointerException** if the specified element is null and this collection does not permit null elements
>>**UnsupportedOperationException** if the <tt>remove</tt> operation is not supported by this collection
>
>从该collection中移除指定元素的单个实例（如果存在）。更正式地说，移除一个具备一下条件的元素e，
>当o和e同时满足为null时为true，或者o!=null,且o.equals(e)为true则为true
>如果这个collection包含一个或者多个这样的元素，返回true，如果这个collection包含这样规定的元素（或者等效的元素，如果这个collection根据调用的方法改变了）返回true
>
>参数：**o** collection中将要被移除的元素，如果存在
>
>返回值：如果结果某个元素按照调用被移除了，则返回true
>
>异常：
>>**ClassCastException** 如果这个规定的元素与这个collection不相容，则抛出异常
>>**NullPointerException** 如果这个规定的元素为空，并且这个collection没有允许空的元素，则抛出异常
>>**UnsupportedOperationException** 如果这个collection不支持移除这个操作的话，则抛出异常

*	boolean containsAll(Collection```<?>``` c)
>Returns <tt>true</tt> if this collection contains all of the elements in the specified collection.
>
>param  c collection to be checked for containment in this collection
>
>return <tt>true</tt> if this collection contains all of the elements in the specified collection
>
>throws:
>>**ClassCastException** if the types of one or more elements in the specified collection are incompatible with this collection
>>**NullPointerException** if the specified collection contains one or more null elements and this collection does not permit null elements or if the specified collection is null.
>
>如果在规定的collection中包含某个collection的全部元素，则返回true
>
>参数： **c** 检查当前collection是否包含的collection
>
>返回值：如果在规定的collection中包含某个collection的全部元素，则返回true
>
>异常：
>>**ClassCastException** 如果在规定的collection中有一个或者多个元素类型与这个collection不符，则抛出异常
>>**NullPointerException** 如果这个规定的collection包含一个或者多个空的元素，并且这个collection不允许空的元素，则抛出异常

*	boolean addAll(Collection```<? extends E>``` c)
>Adds all of the elements in the specified collection to this collection (optional operation).  The behavior of this operation is undefined if the specified collection is modified while the operation is in progress. (This implies that the behavior of this call is undefined if the specified collection is this collection, and this collection is nonempty.)
>
>param **c** collection containing elements to be added to this collection
>
>return <tt>true</tt> if this collection changed as a result of the call
>
>throws:
>>**UnsupportedOperationException** if the <tt>addAll</tt> operation is not supported by this collection
>>**ClassCastException** if the class of an element of the specified collection prevents it from being added to this collection
>>**NullPointerException** if the specified collection contains a null element and this collection does not permit null elements, or if the specified collection is null
>>**IllegalArgumentException** if some property of an element of the specified collection prevents it from being added to this collection
>>**IllegalStateException** if not all the elements can be added at this time due to insertion restrictions
>
>添加规定collection中的全部元素到这个collection中（可选操作），如果这个规定的collection在操作过程中被修改，则这个操作的行为是没有被定义的，（这意味着，如果这个规定的collection是这个collection，并且这个collection是非空的，则这个调用行为是不明确的？？）
>
>参数：**c** collection中包含的将要添加到这个collection中的元素
>
>返回值：如果这个collection的结果按照调用改变了，则返回true
>
>异常：
>>**UnsupportedOperationException** 如果这个collection不支持添加操作，则抛出异常
>>**ClassCastException** 如果规定元素的类阻止将其添加到此collection中，则抛出异常
>>**NullPointerException** 如果这个规定的collection包含一个null元素并且这个collection不允许null元素，或者这个规定的collection为null，则抛出异常
>>**IllegalStateException** 如果并不是所有的元素都能在这个时间被添加是由于插入限制，则抛出异常

*	boolean removeAll(Collection```<?>``` c)
>Removes all of this collection's elements that are also contained in the specified collection (optional operation).  After this call returns, this collection will contain no elements in common with the specified collection.
>
>param **c** collection containing elements to be removed from this collection
>
>return <tt>true</tt> if this collection changed as a result of the call
>
>throws:
>>**UnsupportedOperationException** if the <tt>removeAll</tt> method is not supported by this collection
>>**ClassCastException** if the types of one or more elements in this collection are incompatible with the specified collection
>>**NullPointerException** if this collection contains one or more null elements and the specified collection does not support null elements or if the specified collection is null
>
>从这个collection移除这些包含规定collection的所有元素（可选操作），得到这个操作的返回值之后，这个collection将不再包含与规定collection相同的元素
>
>参数：**c** 一个从这个collection中移除的包含元素的collection
>
>返回值：如果这个collection的结果按照调用改变了，则返回true
>
>异常：
>>**UnsupportedOperationException** 如果removeAll这个方法并不被该collection支持，则抛出异常
>>**ClassCastException** 如果这个collection中的一个或者多个元素与规定的collection类型不相符，则抛出异常
>**NullPointerException** 如果这个collection包含一个或者多个null的元素并且规定的collection并不支持null元素，或者这个规定的collection为null,则抛出异常

*	default boolean removeIf(Predicate```<? super E>``` filter)
	>```
default boolean removeIf(Predicate<? super E> filter) {
    Objects.requireNonNull(filter);
    boolean removed = false;
    final Iterator<E> each = iterator();
    while(each.hasNext()){
      if(filter.test(each.next())){
          each.remove();
          removed = true;
      }
    }
    return removed;
}
>```
>Removes all of the elements of this collection that satisfy the given predicate.  Errors or runtime exceptions thrown during iteration or by the predicate are relayed to the caller.
>
>param **filter** a predicate which returns {@code true} for elements to be removed
>
>return {@code true} if any elements were removed
>
>throws：
>>**NullPointerException** if the specified filter is null
>>**UnsupportedOperationException** if elements cannot be removed from this collection.  Implementations may throw this exception if a matching element cannot be removed or if, in general, removal is not supported.
>
>删除满足给定的描述的所有集合的元素，在迭代过程中和由描述抛出的错误或运行时异常将传递给调用者
>
>参数：filter 对于返回值为true的被移除的元素的描述
>
>返回值：如果任何元素被移除了，则返回true
>
>异常：
>>**NullPointerException** 如果这个规定的filter为null
>>**UnsupportedOperationException** 如果元素不能从这个collection中删除。如果不能删除匹配的元素或者不支持删除，实现类可能会抛出此异常
>从1.8开始的新特性

*	boolean retainAll(Collection```<?>``` c)
>Retains only the elements in this collection that are contained in the specified collection (optional operation).  In other words, removes from this collection all of its elements that are not contained in the specified collection.
>
>param **c** collection containing elements to be retained in this collection
>
>return <tt>true</tt> if this collection changed as a result of the call
>
>throws:
>>**UnsupportedOperationException** if the <tt>retainAll</tt> operation is not supported by this collection
>>**ClassCastException** if the types of one or more elements in this collection are incompatible with the specified collection
>>**NullPointerException** if this collection contains one or more null elements and the specified collection does not permit null elements or if the specified collection is null
>
>只保留被包含在规定collection中的collection的元素（可选操作），对于其他元素，则直接移除
>
>参数：**c** 一个被这个collection包含的具有元素的collection
>
>返回值：如果这个集合的结果按照调用改变了，则返回true
>
>异常：
>>**UnsupportedOperationException** 如果这个collection不支持retainAll操作，则抛出异常
>>**ClassCastException** 如果这个collection中的元素有一个或者多个与规定的collection中不相符，则抛出异常
>>**NullPointerException** 如果这个collection包含一个或者多个null元素，并且规定的collection不允许null元素或者这个规定的collection为null

*	void clear()
>Removes all of the elements from this collection (optional operation). The collection will be empty after this method returns.
>
>throws **UnsupportedOperationException** if the <tt>clear</tt> operation is not supported by this collection
>
>移除这个collection中的全部元素（可选操作），当这个方法返回之后，这个collection将会为空
>
>异常：**UnsupportedOperationException** 如果这个collection不支持clear操作，则抛出异常

*	boolean equals(Object o)
>Compares the specified object with this collection for equality.
>
>将指定对象与collection比较

*	int hasCode()
>Returns the hash code value for this collection.  While the <tt>Collection</tt> interface adds no stipulations to the general contract for the <tt>Object.hashCode</tt> method, programmers should take note that any class that overrides the <tt>Object.equals</tt> method must also override the <tt>Object.hashCode</tt> method in order to satisfy the general contract for the <tt>Object.hashCode</tt> method. In particular, <tt>c1.equals(c2)</tt> implies that <tt>c1.hashCode()==c2.hashCode()</tt>.
>
>return the hash code value for this collection
>
>返回这个collection的hash值，虽然Collection接口不会为Object.hashCode方法的一般合约添加规定，但是程序员应该注意，任何重写Object.equals方法的类都应该重写Object.hashCode方法来满足Object.hashCode方法的通常合约，特别地，c1.equals(c2)意味着c1.hashCode()==c2.hashCode()

*	总结
>为什么要看源码？
>>就拿这个Collection接口来说吧，看了源码，我们能知道在collection中能有哪些方法，这些方法是干什么的，这些操作要怎么用，一旦有类实现了这个Collection，我们就能使用这些方法，这对我们深入理解Java是有很大帮助的，有些比较打的框架，理解起来有困难的时候也能通过看源码来慢慢捋清

	>如何看源码？
	>>我是用的idea看的，在里面写下想要看的源码内容，比如要看Collection这个接口的内容，直接写下Collection，然后选中右键Go To --> Declaration就可以进入对应的源码了，操作如下如：![写入想要查看的源码](http://img.blog.csdn.net/20171125215046499?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)![选择goto查看](http://img.blog.csdn.net/20171125215124462?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)![查看源码](http://img.blog.csdn.net/20171125215249360?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	>
	>Others
	>>当我们进入源码某个源码之后，我们就能对其祖先及后辈进行以前难以触及的研究了，具体有哪些类依赖于这个接口，具体有哪些接口继承于该接口，还是拿Collection接口作为例子，具体如下:
	>	点击接口名右边的绿色向下箭头圆球
	![选择接口名](http://img.blog.csdn.net/20171125223123241?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	>选择我们比较熟悉的ArrayList
	![选择ArrayList](http://img.blog.csdn.net/20171125223531321?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	>我们可以看见ArrayList是继承AbstractList类并且实现List接口
	![ArrayList](http://img.blog.csdn.net/20171125224048031?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	>我们继续往上追溯看到AbstractList类	，我们可以看到AbstractList类继承AbstractCollection类，并且实现List接口
	![AbstractList](http://img.blog.csdn.net/20171125224406864?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	>最后看到AbstractCollection类和List接口
	![AbstractCollection类](http://img.blog.csdn.net/20171125225208994?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	![List接口](http://img.blog.csdn.net/20171125225048487?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	于是最后根据这几层简单的追根溯源，总结出了如下UML图：
	![UML图](http://img.blog.csdn.net/20171125230943276?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvTGFtYm9yZ2hpbnN6/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/SouthEast)
	具体集合的结构，比我写出来的要复杂很多，我这里只是提供一个学习的方式，源码代表了目前我们写的Java的全部，私以为自己研究源码比看任何参考书和教学视频都要有用。
