基数排序 算法
=========

适用问题的描述
----------------

**基数排序**算法 要解决的问题是要解决的问题是 排序问题，以下是排序问题的说明：

输入：n个数的一个序列<a1，a2，...，an>

输出：输入序列的一个排列<a1'，a2'，...，an'>，满足a1'<=a2'<=....<=an'。

算法性能
---------

最坏情况下时间复杂度：O(d(n+k))。

平均/期望的时间复杂度：O(d(n+k))。

其中，排序的数的位数最高为d，其中n个数里每一个数共有k种取值。

虽然基数排序循环地对每一位排了d次，不过比起计数排序，它不需要那么多空间的数组进行随机读写，算法运行时占用空间更小。

书中提出这个算法的教学目的
-----------------------------

基数排序最早是用于卡片机上的一类算法，

对于一个十进制数来说，每一位有0~9共十种可能，因此k为10，

本算法假设要排序的数都是一些d位k进制整数，或者要排序的数都能（精度不变地）转换为相同规格的n个d位k进制整数。

基数排序算法先按最低有效位对数字进行排序，直到最高位。其中对单位数的排序算法是稳定的（比如计数排序）。

在实现中，这里我们默认待排序数组的数据都是3位十进制数。

算法伪代码
-----------

```
//A为待排序数组，数组中的元素都是一些d位整数
RADIX-SORT(A, d)
	for i = 1 to d
		使用稳定的排序算法根据d位对A中元素排序
```