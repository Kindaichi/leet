## My Leetcode repo

### 2016-02-02
- 209.[Minimum Size Subarray Sum](https://leetcode.com/problems/minimum-size-subarray-sum/)

    在一个正数数组中找出长度最小的子数组使其和大于等于给定值

    [code](229.py) O(n)

    思路:

    1. 枚举子数组```(i,j)``` (i,j分别代表起始位置和终止位置)是可以得到正确答案的,复杂度为```O(n^3)```

    2. 方法1中起始点相同的数组求和可以累加,而且一旦和满足要求后,不用再考虑后面的终止位置.但复杂度仍然有```O(n^2)```

    3. 利用题目的重要性质.数组中的元素都是正数.

        设对于给定的```i```,```j'```为使子数组```(i,j)```满足条件的最小值.则子数组```(i+1,j')```仍然有可能满足条件,但```(i+1,j'-1)```是不可能满足的.所以在处理完开始于i的子数组后,处理i+1子数组时,结束位置只需从j'开始考虑.每一个元素最多会进行两次操作(被累加到sum和从sum减去),所以复杂度为O(n)

- 319.[Bulb Switcher](https://leetcode.com/problems/bulb-switcher/)

    按规定开(turn on)关(turn off)或取反(toggle)灯,问最后开着等的数量.

    round1: 打开所有灯

    round2: 关闭所有偶数索引灯(从1开始计数)

    round3: 取反所有3整数倍索引灯

    ...以此类推

    [code](319.py) O(1)

    思路:
    这是一道脑筋急转弯题..

    首先直观感受,如果灯泡的索引能整除的数越多,其被toggle的次数就会越多,如果是质数,只会toggle两次.

    每盏灯的最终开关状态有toggle次数的奇偶性决定.如果是奇数为开,偶数为关.

    例如索引为8的灯,其能被1,2,4,8整除,一共4次toggle,为偶数,灯最终关闭.我们发现,因子具有某种"对称性",即i为k的因子,则k/i也为k的因子,如果i != k/i,则两因子不相同,需要两次toggle.除了平方数之外,任何数的因子数均为偶数.所以最后灯开的数量就等于<=n 的平方数个数.

- 289.[Game of Life](https://leetcode.com/problems/game-of-life/)

    矩形board,每个点两种状态(1:alive,0:dead),按照四个规则进行演变,要求进行inplace演变.

    [code](229.py)

    思路:

    直接模拟,用一个set存储改变过的位置.在每个节点八领域alive节点查找时,需要查看该节点是否在本轮修改过,如果修改过则状态取反来得到为修改的状态.

- 225.[Implement Stack using Queues](https://leetcode.com/problems/implement-stack-using-queues/)

    利用队列实现栈

     only push to back, peek/pop from front, size, and is empty operations are valid.

     略,搞不懂这道题..可以实现但效率比普通栈要低

- 203.[Remove Linked List Elements](https://leetcode.com/problems/remove-linked-list-elements/)

    在链表中删除特定值的节点

    [code](203.py)
- 199.[Binary Tree Right Side View](https://leetcode.com/problems/binary-tree-right-side-view/)

   给出二叉树的右视角节点

   [code](199.py)

   思路:
    右节点优先dfs,保存当前已打印的最大层次.

- 93.[Restore IP Addresses](https://leetcode.com/problems/restore-ip-addresses/)

    给定一个数字字符串,给出所有可行的ip解析结果.

    [code](93.py)

    思路:

    深度搜索,注意剪枝(字符串长度).注意0开头的非零数字是不允许的.

- 105.[Construct Binary Tree from Preorder and Inorder Traversal](https://leetcode.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)

    [code](105.py)

    preorder确定当前节点,inorder确定两侧节点,递归构造节点即可

- 128.Longest Consecutive Sequence

    给定一个无须数组,给出最长的连续数列的长度,要求O(n)

    TODO

### 2016-02-03

- 318.[Maximum Product of Word Lengths](https://leetcode.com/problems/maximum-product-of-word-lengths/)

  求两个字符串长度的最大乘积.要求两字符串不能有共同字母.

  [code](318.cpp)

  思路:

  用一个32位整数就可以表达一个字符串对26个小写字母的拥有情况.判断量字符串是否有公共字母只需用&位运算判断.

- 116.[Populating Next Right Pointers in Each Node](https://leetcode.com/problems/populating-next-right-pointers-in-each-node/)

    完美二叉树每一层构建一个链表,要求空间复杂度O(1)

    [code](116.py)

    思路:

    利用完美二叉树的特点,递归处理每个节点即可(但是递归的话空间复杂度就不是O(1)了)
