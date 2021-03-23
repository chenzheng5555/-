## 目录

### 简单

|                             题目                             |                             说明                             |     知识点     |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :------------: |
| [1. 两数之和](#[1. 两数之和](https://leetcode-cn.com/problems/two-sum/)) |                找数组内某两个数，其和为指定值                |      hash      |
| [20. 有效的括号](#[20. 有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)) |                   判断由括号的排列是否有效                   |       栈       |
| [21. 合并两个有序链表](#[21. 合并两个有序链表](https://leetcode-cn.com/problems/merge-two-sorted-lists/)) |                    使合并后的链表仍然有序                    |   递归、迭代   |
| [119. 杨辉三角 II](#[119. 杨辉三角 II](https://leetcode-cn.com/problems/pascals-triangle-ii/)) |                     求第n行杨辉三角的值                      | 迭代、数值运算 |
| [232. 用栈实现队列](#[232. 用栈实现队列](https://leetcode-cn.com/problems/implement-queue-using-stacks/)) |                      使用两个栈实现队列                      |    队列+栈     |
| [448. 找到所有数组中消失的数字](#[448. 找到所有数组中消失的数字](https://leetcode-cn.com/problems/find-all-numbers-disappeared-in-an-array/)) | 长度为n的数组，求数组中1-n缺少的整数[41. 缺失的第一个正数](#[41. 缺失的第一个正数](https://leetcode-cn.com/problems/first-missing-positive/)) |    原地修改    |
| [485. 最大连续1的个数](#[485. 最大连续1的个数](https://leetcode-cn.com/problems/max-consecutive-ones/)) |                计算数组中连续1子串的最大长度                 |      迭代      |
| [561. 数组拆分 I](#[561. 数组拆分 I](https://leetcode-cn.com/problems/array-partition-i/)) |             数组分为n对，使得每对最小值之和最大              |      排序      |
| [566. 重塑矩阵](#[566. 重塑矩阵](https://leetcode-cn.com/problems/reshape-the-matrix/)) |                        矩阵的reshape                         |      遍历      |
| [643. 子数组最大平均数 I](#[643. 子数组最大平均数 I](https://leetcode-cn.com/problems/maximum-average-subarray-i/)) |                 长度为k且平均值最大的子序列                  |    滑动窗口    |
| [665. 非递减数列](#[665. 非递减数列](https://leetcode-cn.com/problems/non-decreasing-array/)) |              最多一次改变，使得数组为非递减数列              |  统计修改次数  |
| [697. 数组的度](#[697. 数组的度](https://leetcode-cn.com/problems/degree-of-an-array/)) |    子序列 重复元素出现的最大次数与原数组相同的最长子序列     |      哈希      |
| [703. 数据流中的第 K 大元素](#[703. 数据流中的第 K 大元素](https://leetcode-cn.com/problems/kth-largest-element-in-a-stream/)) |                新加元素后，求数组第K大的元素                 |     最小堆     |
| [724. 寻找数组的中心索引](#[724. 寻找数组的中心索引](https://leetcode-cn.com/problems/find-pivot-index/)) |                     索引两边元素之和相等                     |      遍历      |
| [766. 托普利茨矩阵](#[766. 托普利茨矩阵](https://leetcode-cn.com/problems/toeplitz-matrix/)) |               相邻右下角元素等于当前元素的矩阵               |      遍历      |
| [832. 翻转图像](#[832. 翻转图像](https://leetcode-cn.com/problems/flipping-an-image/)) |                      水平翻转再反转图片                      |      交换      |
| [867. 转置矩阵](#[867. 转置矩阵](https://leetcode-cn.com/problems/transpose-matrix/)) |                        矩阵的转置操作                        |      遍历      |
| [888. 公平的糖果棒交换](#[888. 公平的糖果棒交换](https://leetcode-cn.com/problems/fair-candy-swap/)) |              交互两数组的某个元素，使数组和相等              |      哈希      |
| [1047. 删除字符串中的所有相邻重复项](#[1047. 删除字符串中的所有相邻重复项](https://leetcode-cn.com/problems/remove-all-adjacent-duplicates-in-string/)) |              不断重复删除字符串中存在的相邻字符              |       栈       |
| [1742. 盒子中小球的最大数量](#[1742. 盒子中小球的最大数量](https://leetcode-cn.com/problems/maximum-number-of-balls-in-a-box/)) |                        求整数各位之和                        |      哈希      |
| [1779. 找到最近的有相同 X 或 Y 坐标的点](#[1779. 找到最近的有相同 X 或 Y 坐标的点](https://leetcode-cn.com/problems/find-nearest-point-that-has-the-same-x-or-y-coordinate/)) |                           找最小值                           |      遍历      |
| [1784. 检查二进制字符串字段](#[1784. 检查二进制字符串字段](https://leetcode-cn.com/problems/check-if-binary-string-has-at-most-one-segment-of-ones/)) |               判断字符串只包含一个全是1的子串                |      遍历      |
|                                                              |                                                              |                |



### 中等

|                             题目                             |                             说明                             |      知识点       |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :---------------: |
| [2. 两数相加](#[2. 两数相加](https://leetcode-cn.com/problems/add-two-numbers/)) |           整数在链表中逆序存储，求两个这样整数的和           |       链表        |
| [3. 无重复字符的最长子串](#[3. 无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)) |                不含有重复字符的最长子串的长度                |    双指针+统计    |
| [22. 括号生成](#[22. 括号生成](https://leetcode-cn.com/problems/generate-parentheses/)) |       给定括号的对数，生成所有可能的并且有效的括号组合       |       回溯        |
| [24. 两两交换链表中的节点](#[24. 两两交换链表中的节点](https://leetcode-cn.com/problems/swap-nodes-in-pairs/)) |                   两两交换链表中元素的位置                   |       链表        |
| [48. 旋转图像](#[48. 旋转图像](https://leetcode-cn.com/problems/rotate-image/)) |                         原地旋转图像                         |       交互        |
| [73. 矩阵置零](#[73. 矩阵置零](https://leetcode-cn.com/problems/set-matrix-zeroes/)) |                    原地将0所在的行列清零                     |     迭代+延迟     |
| [92. 反转链表 II](#[92. 反转链表 II](https://leetcode-cn.com/problems/reverse-linked-list-ii/)) |                       翻转链表的一部分                       |       链表        |
| [131. 分割回文串](#[131. 分割回文串](https://leetcode-cn.com/problems/palindrome-partitioning/)) |          一个字符串可能的分割情况，每个子串为回文串          |   回溯+动态规划   |
| [150. 逆波兰表达式求值](#[150. 逆波兰表达式求值](https://leetcode-cn.com/problems/evaluate-reverse-polish-notation/)) |                    根据逆波兰表达式求结果                    |        栈         |
| [227. 基本计算器 II](#[227. 基本计算器 II](https://leetcode-cn.com/problems/basic-calculator-ii/)) | [224. 基本计算器](#[224. 基本计算器](https://leetcode-cn.com/problems/basic-calculator/))，增加了*和/ |        栈         |
| [300. 最长递增子序列](#[300. 最长递增子序列](https://leetcode-cn.com/problems/longest-increasing-subsequence/)) | 求递增的最长子序列[354.俄罗斯套娃信封问题](#[354. 俄罗斯套娃信封问题](https://leetcode-cn.com/problems/russian-doll-envelopes/)) |     动态规划      |
| [331. 验证二叉树的前序序列化](#[331. 验证二叉树的前序序列化](https://leetcode-cn.com/problems/verify-preorder-serialization-of-a-binary-tree/)) |            验证一个字符串是否符合二叉树的前序遍历            |  二叉树前序遍历   |
| [341. 扁平化嵌套列表迭代器](#[341. 扁平化嵌套列表迭代器](https://leetcode-cn.com/problems/flatten-nested-list-iterator/)) |                       嵌套列表的迭代器                       |        栈         |
| [424. 替换后的最长重复字符](#[424. 替换后的最长重复字符](https://leetcode-cn.com/problems/longest-repeating-character-replacement/)) |         任意替换K个字符，使得重复字符构成的子串最长          |   滑动窗口+统计   |
| [503. 下一个更大元素 II](#[503. 下一个更大元素 II](https://leetcode-cn.com/problems/next-greater-element-ii/)) |           一个循环数组，给出每个元素下一个更大元素           |  栈存储递减序列   |
| [567. 字符串的排列](#[567. 字符串的排列](https://leetcode-cn.com/problems/permutation-in-string/)) |            判断一个字符串是否为另一个字符串的排序            |    双指针+统计    |
| [907. 子数组的最小值之和](#[907. 子数组的最小值之和](https://leetcode-cn.com/problems/sum-of-subarray-minimums/)) |                 求所有连续子数组的最小值之和                 |  栈存储递增序列   |
| [978. 最长湍流子数组](#[978. 最长湍流子数组](https://leetcode-cn.com/problems/longest-turbulent-subarray/)) |                     相邻元素大小不断变化                     |      双指针       |
| [1004. 最大连续1的个数 III](#[1004. 最大连续1的个数 III](https://leetcode-cn.com/problems/max-consecutive-ones-iii/)) | [485 ](#[485. 最大连续1的个数](https://leetcode-cn.com/problems/max-consecutive-ones/))、[424](#[424. 替换后的最长重复字符](https://leetcode-cn.com/problems/longest-repeating-character-replacement/))、[1208](#[1208. 尽可能使字符串相等](https://leetcode-cn.com/problems/get-equal-substrings-within-budget/))、 |   滑动窗口+统计   |
| [1052. 爱生气的书店老板](#[1052. 爱生气的书店老板](https://leetcode-cn.com/problems/grumpy-bookstore-owner/)) |                  大小为k的窗口内，增加的数                   |     滑动窗口      |
| [1143. 最长公共子序列](#[1143. 最长公共子序列](https://leetcode-cn.com/problems/longest-common-subsequence/)) | 匹配的最长子序列、可以不连续[115. 不同的子序列](#[115. 不同的子序列](https://leetcode-cn.com/problems/distinct-subsequences/))、 |     动态规划      |
| [1208. 尽可能使字符串相等](#[1208. 尽可能使字符串相等](https://leetcode-cn.com/problems/get-equal-substrings-within-budget/)) |   两字符串对应的子串 各位置的差之和<cost，求子串长度最大值   |     滑动窗口      |
| [1423. 可获得的最大点数](#[1423. 可获得的最大点数](https://leetcode-cn.com/problems/maximum-points-you-can-obtain-from-cards/)) |              在数组尾和首取数，取K个，使和最大               |     滑动窗口      |
| [1438. 绝对差不超过限制的最长连续子数组](#[1438. 绝对差不超过限制的最长连续子数组](https://leetcode-cn.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)) |           最大值最小值之差不大于limit的最长子序列            | 滑动窗口+单调队列 |
| [1631. 最小体力消耗路径](#[1631. 最小体力消耗路径](https://leetcode-cn.com/problems/path-with-minimum-effort/)) |               最短路径，值为相邻节点的最大差值               | 并查集、dijkstra  |
| [1743. 从相邻元素对还原数组](#[1743. 从相邻元素对还原数组](https://leetcode-cn.com/problems/restore-the-array-from-adjacent-pairs/)) |                给出相邻元素组成的对，求原数组                |     哈希+遍历     |
| [1780. 一个数字是否可以表示成三的幂的和](#[1780. 判断一个数字是否可以表示成三的幂的和](https://leetcode-cn.com/problems/check-if-number-is-a-sum-of-powers-of-three/)) |                一个数能否表示为3的不同幂之和                 |       进制        |
| [1785. 构成特定和需要添加的最少元素](#[1785. 构成特定和需要添加的最少元素](https://leetcode-cn.com/problems/minimum-elements-to-add-to-form-a-given-sum/)) |               总和与目标值的差值与给定值的倍数               |       遍历        |
| [1792.最大平均通过率](#[1792. 最大平均通过率](https://leetcode-cn.com/problems/maximum-average-pass-ratio/)) |                 分子分母同时加一，增量的比较                 |     优先队列      |
|                                                              |                                                              |                   |

### 困难

|                             题目                             |                             说明                             |               知识点                |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :---------------------------------: |
| [4. 寻找两个正序数组的中位数](#[4. 寻找两个正序数组的中位数](https://leetcode-cn.com/problems/median-of-two-sorted-arrays/)) |          两个正序排列数组组合，其正序排列后的中位数          |          双指针、二分查找           |
| [23. 合并K个升序链表](#[23. 合并K个升序链表](https://leetcode-cn.com/problems/merge-k-sorted-lists/)) | [21. 合并两个有序链表](#[21. 合并两个有序链表](https://leetcode-cn.com/problems/merge-two-sorted-lists/))的扩展 |      最小堆（优先队列）、分治       |
| [25. K 个一组翻转链表](#[25. K 个一组翻转链表](https://leetcode-cn.com/problems/reverse-nodes-in-k-group/)) |                      链表每K个进行翻转                       |                链表                 |
| [30. 串联所有单词的子串](#[30. 串联所有单词的子串](https://leetcode-cn.com/problems/substring-with-concatenation-of-all-words/)) |             单词任意排列后，能否作为字符串的子串             |                哈希                 |
| [32. 最长有效括号](#[32. 最长有效括号](https://leetcode-cn.com/problems/longest-valid-parentheses/)) |                      括号匹配的最长子串                      |       动态规划、栈、双向遍历        |
| [37. 解数独](#[37. 解数独](https://leetcode-cn.com/problems/sudoku-solver/)) |                        求9*9数独的解                         |          递归、位运算优化           |
| [41. 缺失的第一个正数](#[41. 缺失的第一个正数](https://leetcode-cn.com/problems/first-missing-positive/)) |              O(n)/O(1)复杂度求未出现的最小整数               |              就地哈希               |
| [115. 不同的子序列](#[115. 不同的子序列](https://leetcode-cn.com/problems/distinct-subsequences/)) |                       匹配的子序列个数                       |              动态规划               |
| [124. 二叉树中的最大路径和](#[124. 二叉树中的最大路径和](https://leetcode-cn.com/problems/binary-tree-maximum-path-sum/)) |                求二叉树里路径和最大的一条路径                |              动态规划               |
| [132. 分割回文串 II](#[132. 分割回文串 II](https://leetcode-cn.com/problems/palindrome-partitioning-ii/)) | [131. 分割回文串](#[131. 分割回文串](https://leetcode-cn.com/problems/palindrome-partitioning/))中最小的分割次数 |              动态规划               |
| [224. 基本计算器](#[224. 基本计算器](https://leetcode-cn.com/problems/basic-calculator/)) |                给表达式字符串，计算表达式结果                |             栈+括号扩展             |
| [354. 俄罗斯套娃信封问题](#[354. 俄罗斯套娃信封问题](https://leetcode-cn.com/problems/russian-doll-envelopes/)) |            求两个维度上，都严格递增，的最长数组。            |         动态规划、二分查找          |
| [420. 强密码检验器](#[420. 强密码检验器](https://leetcode-cn.com/problems/strong-password-checker/)) |                     变为强密码所需的操作                     |              优先队列               |
| [480. 滑动窗口中位数](#[480. 滑动窗口中位数](https://leetcode-cn.com/problems/sliding-window-median/)) |         长度为k的窗口在数组上滑动，求窗口内的中位数          | 最大堆和最小堆（优先队列+延迟删除） |
| [564. 寻找最近的回文数](#[564. 寻找最近的回文数](https://leetcode-cn.com/problems/find-the-closest-palindrome/)) |               给字符串表示的数，求最近的回文数               |           字符串+详细讨论           |
| [629. K个逆序对数组](#[629. K个逆序对数组](https://leetcode-cn.com/problems/k-inverse-pairs-array/)) |         数字1-n组成的数组，其中逆序对为k的数组的个数         |           动态规划+窗口和           |
| [730. 统计不同回文子序列](https://leetcode-cn.com/problems/count-different-palindromic-subsequences/) | 不同回文子序列的个数[1458. 两个子序列的最大点积](https://leetcode-cn.com/problems/max-dot-product-of-two-subsequences/) |              动态规划               |
| [765. 情侣牵手](#[765. 情侣牵手](https://leetcode-cn.com/problems/couples-holding-hands/)) |              使情侣全坐在相邻座位需要调整的次数              |        并查集、dfs、连通分量        |
| [862. 和至少为 K 的最短子数组](#[862. 和至少为 K 的最短子数组](https://leetcode-cn.com/problems/shortest-subarray-with-sum-at-least-k/)) |                    求满足要求的最短子数组                    |         前缀和+递增双端队列         |
| [906. 超级回文数](#[906. 超级回文数](https://leetcode-cn.com/problems/super-palindromes/)) | 自己是回文数，平方也是，[564. 寻找最近的回文数](#[564. 寻找最近的回文数](https://leetcode-cn.com/problems/find-the-closest-palindrome/)) |                乘法                 |
| [940. 不同的子序列 II](#[940. 不同的子序列 II](https://leetcode-cn.com/problems/distinct-subsequences-ii/)) | 不同子序列的个数[730. 统计不同回文子序列](https://leetcode-cn.com/problems/count-different-palindromic-subsequences/) |              动态规划               |
| [992. K 个不同整数的子数组](#[992. K 个不同整数的子数组](https://leetcode-cn.com/problems/subarrays-with-k-different-integers/)) |                 k个不同整数构成的子数组个数                  |       双指针+统计（问题改变）       |
| [995. K 连续位的最小翻转次数](#[995. K 连续位的最小翻转次数](https://leetcode-cn.com/problems/minimum-number-of-k-consecutive-bit-flips/)) |          一次翻转k位，使数组全为1需要的最小翻转次数          |               位运算                |
| [1044. 最长重复子串](#[1044. 最长重复子串](https://leetcode-cn.com/problems/longest-duplicate-substring/)) |                        快速字符串hash                        |         二分查找+字符串哈希         |
| [1074. 子矩阵数量](#[1074. 元素和为目标值的子矩阵数量](https://leetcode-cn.com/problems/number-of-submatrices-that-sum-to-target/)) |                   元素和满足要求的子矩阵数                   |              遍历+哈希              |
| [1172. 餐盘栈](#[1172. 餐盘栈](https://leetcode-cn.com/problems/dinner-plate-stacks/)) |                  模拟多个stack按规定操作，                   |                模拟                 |
| [1178. 猜字谜](#[1178. 猜字谜](https://leetcode-cn.com/problems/number-of-valid-words-for-each-puzzle/)) |                    求每个字谜对应的谜底数                    |           二进制状态压缩            |
| [1458. 两个子序列的最大点积](https://leetcode-cn.com/problems/max-dot-product-of-two-subsequences/) | 子序列的最大点积[1143. 最长公共子序列](#[1143. 最长公共子序列](https://leetcode-cn.com/problems/longest-common-subsequence/)) |              动态规划               |
| [1610. 可见点的最大数目](#[1610. 可见点的最大数目](https://leetcode-cn.com/problems/maximum-number-of-visible-points/)) | 可见角度能看见的最多点数，区间和的最大值[503](#[503. 下一个更大元素 II](https://leetcode-cn.com/problems/next-greater-element-ii/)) |              滑动窗口               |
| [1622. 奇妙序列](#[1622. 奇妙序列](https://leetcode-cn.com/problems/fancy-sequence/)) |                        数组整体的加法                        |         线段数组、乘法逆元          |
| [1782. 统计点对的数目](#[1782. 统计点对的数目](https://leetcode-cn.com/problems/count-pairs-of-nodes/)) |                    边数满足要求的顶点对数                    |            双指针求和，             |
| [LCP 14. 切分数组](#[LCP 14. 切分数组](https://leetcode-cn.com/problems/qie-fen-shu-zu/)) |          子数组两端元素最小公约数>1；分割的最少次数          |          质数因子+动态规划          |
| [17.26. 稀疏相似度](#[面试题 17.26. 稀疏相似度](https://leetcode-cn.com/problems/sparse-similarity-lcci/)) |                          数组的交集                          |           数组元素的哈希            |
| [17.24. 最大子矩阵](#[面试题 17.24. 最大子矩阵](https://leetcode-cn.com/problems/max-submatrix-lcci/)) | [1074. 元素和为目标值](#[1074. 元素和为目标值的子矩阵数量](https://leetcode-cn.com/problems/number-of-submatrices-that-sum-to-target/))、[862. 和至少为 K ](#[862. 和至少为 K 的最短子数组](https://leetcode-cn.com/problems/shortest-subarray-with-sum-at-least-k/)) |              动态规划               |

### 题解

#### [1. 两数之和](https://leetcode-cn.com/problems/two-sum/)

```c++
//使用哈希表来存储目标值与当前元素的差，如果未来某个值对于该差值，则找到一个结果。返回。
class Solution{
public:
    vector<int> twoSum(vector<int> &nums, int target){
        unordered_map<int, int> hashTab;
        for (int i = 0; i < nums.size(); ++i)
        {
            if (hashTab.find(nums[i]) != hashTab.end()) //如果哈希表中存在当前值
                return {hashTab[nums[i]], i};
            hashTab[target - nums[i]] = i;
        }
        return {};
    }
};
```

#### [2. 两数相加](https://leetcode-cn.com/problems/add-two-numbers/)

```c++
//模拟加法过程，和链表操作。
class Solution {
public:
    ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {
        ListNode *head = l1, *pre = l1;
        int carry = 0;
        while (l1 && l2){ //同时遍历两个链表
            int sum = l1->val + l2->val + carry;
            carry = sum / 10, l1->val = sum % 10;
            pre = l1, l1 = l1->next;
            l2 = l2->next;
        }
        if (!l1) //原来存储结果的链表完了，将另一个链表剩余部分作为存放结果的地方。
            pre->next = l2, l1 = l2;
        while (l1){
            int sum = l1->val + carry;
            carry = sum / 10, l1->val = sum % 10;
            pre = l1, l1 = l1->next;
        }
        if (carry) //有进位
            pre->next = new ListNode(1);
        return head;
    }
};
```

#### [3. 无重复字符的最长子串](https://leetcode-cn.com/problems/longest-substring-without-repeating-characters/)

```c++
//设立一个数组来存储当前窗口中各元素的个数，当新加入的元素导致其出现个数超过2，需要移动左边界，使窗口内的各元素出现次数为1.
//leetcode使用的固定左边界，扩展右边界。
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int left = 0, right = 0, len = 0;
        vector<int> cnt(128, 0);
        while (right < s.size()) {
            cnt[s[right]]++;
            while (cnt[s[right]] > 1)//查找值等于当前元素的位置，左边界移到下一位置，使窗口内各字符不会重复出现
                cnt[s[left++]]--;
            right++;
            len = max(len, right - left);
        }
        return len;
    }
};
```

#### [4. 寻找两个正序数组的中位数](https://leetcode-cn.com/problems/median-of-two-sorted-arrays/)

```c++
//依次合并两个数组，直到到达合并数组的中间时，可以直接求得中位数。
class Solution {
public:
    double findMedianSortedArrays(vector<int> &nums1, vector<int> &nums2){
        int i = 0, j = 0, cnt = 0;
        int m = nums2.size(), n = nums1.size();
        int mid = (m + n - 1) / 2;
        while (cnt < mid && i < n && j < m){ //找中位数的位置，丢弃前(m+n)/2-1个元素
            if (nums1[i] < nums2[j])
                i++;
            else
                j++;
            cnt++;
        }
        if (cnt < mid){ //一个数组遍历完
            while (cnt < mid){
                i == n ? j++ : i++;
                cnt++;
            }
        }

        double x;
        if ((m + n) % 2){  //根据数组个数的奇偶性确定中位数。
            if (i == n)
                x = nums2[j];
            else if (j == m)
                x = nums1[i];
            else
                x = min(nums1[i], nums2[j]);
        }
        else{
            if (i == n)
                x = nums2[j] + nums2[j + 1];
            else if (j == m)
                x = nums1[i] + nums1[i + 1];
            else{//需要找接下来最小的两个数。
                int min1 = min(nums1[i], nums2[j]), min2;
                if (nums1[i] < nums2[j])
                    i++;
                else
                    j++;
                if (i == n)
                    min2 = nums2[j];
                else if (j == m)
                    min2 = nums1[i];
                else
                    min2 = min(nums1[i], nums2[j]);
                x = min1 + min2;
            }
            x /= 2;
        }
        return x;
    }
};
//相同的方法，更少的代码。
class Solution {
public:
    double findMedianSortedArrays(vector<int>& nums1, vector<int>& nums2) {
        int left, right, i = 0, j = 0, k = 0; //left和right用来存放第(m+n)/2和第(m+n)/2+1小的值
        int n = nums1.size(), m = nums2.size();
        while (k <= (m + n) / 2) {
            left = right;
            if (i < n && (j >= m || nums1[i] < nums2[j]))
                right = nums1[i++];
            else
                right = nums2[j++];
            k++;
        }
        if ((m + n) & 1)
            return right;
        else
            return (left + right) / 2.0;
    }
};
//该题为目标为找出正确的划分线。可以选择在小的数组进行查找划分的位置，
```

#### [20. 有效的括号](https://leetcode-cn.com/problems/valid-parentheses/)

```c
//方法：堆栈使用的典型案例，左括号压入，遇到右括号弹出。其他情况无效。
#define ISLEFT(c) (c == '(' || c == '{' || c == '[')
#define ISMATCH(a, b) (a == '(' && b == ')' || a == '{' && b == '}' || a == '[' && b == ']')
#define MAXSIZE 10000
struct stack {
    char data[MAXSIZE/2 + 1];
    int top;
};
// 输入s [1,10000]
bool isValid(char *s) 
{
    struct stack st;
    st.top = -1;
    while (*s){
        if (ISLEFT(*s) && st.top < MAXSIZE) //输入为左括号，且小于栈的大小
            st.data[++st.top] = *s;
        else if (st.top != -1 && ISMATCH(st.data[st.top], *s)) //输入右括号且与栈顶匹配
            st.top--;
        else //在字符串未读完的情况下，不可能匹配成功。
            return false; //break;
        s++;
    }
    return st.top == -1; //栈清空，字符串全匹配
}

```

#### [21. 合并两个有序链表](https://leetcode-cn.com/problems/merge-two-sorted-lists/)

```c
//方法：依次比较两个链表的头，指向值小的链表，该链表指针往后移一位，直到有个链表遍历完。
#include <stdio.h>
#include <stdlib.h>
struct ListNode {
    int val;
    struct ListNode *next;
};

struct ListNode *mergeTwoLists(struct ListNode *l1, struct ListNode *l2)
{
    //增加头节点，不需要单独处理开始节点。
    struct ListNode *head = (struct ListNode *)malloc(sizeof(struct ListNode));
    head->next = NULL;
    struct ListNode *p = head;

    while (l1 && l2){
        if (l1->val > l2->val){
            p->next = l2;
            l2 = l2->next;
        }else{
            p->next = l1;
            l1 = l1->next;
        }
        p = p->next;
    }

    if (l1)
        p->next = l1;
    else
        p->next = l2;
    
    p=head->next;
    free(head);
    return p;
}

//递归方法
struct ListNode *mergeTwoLists(struct ListNode *l1, struct ListNode *l2)
{
    if (!l1)
        return l2;
    if (!l2)
        return l1;
    if (l1->val < l2->val){ //当前l1小，则头应该为l1,让接下来的l1和l2比较。
        l1->next = mergeTwoLists(l1->next, l2);
        return l1;
    }
    l2->next = mergeTwoLists(l1, l2->next);
    return l2;
}
/*
//根据数组创建无头链表
struct ListNode *creat(int *array, int size)
{
    struct ListNode *q, *head = NULL;
    int i = 0;
    while (i < size){
        struct ListNode *p = (struct ListNode *)malloc(sizeof(struct ListNode));
        p->val = array[i++];
        p->next = NULL;
        if (!head)
            head = p, q = p;
        else
            q->next = p;
        q = p;
    }
    return head;
}

void print(struct ListNode *p)
{
    printf("p=[");
    while (p){
        printf("%d,", p->val);
        p = p->next;
    }
    printf("]\n");
}

int main()
{
    freopen("data.txt", "r", stdin);
    struct ListNode *p[2];
    int N[2];
    //vscode的launch.json中的cwd不是当前工作目录，"D:\\mingw64\\bin"，使得freopen("data.txt","r",stdin)出错。使用gcc test.c;a.exe却不会出错。
    while (scanf("%d %d",&N[0],&N[1]) != EOF) {
        int arr[2][30];
        for (int i = 0; i < 2; ++i){
            int j = 0;
            while (j < N[i])
                scanf("%d", &arr[i][j++]);
            p[i] = creat(arr[i], N[i]);
            print(p[i]);
        }
        print(mergeTwoLists(p[0], p[1]));
    }
    fclose(stdin);
    return 0;
}*/
```

#### [22. 括号生成](https://leetcode-cn.com/problems/generate-parentheses/)

```c
//方法：只有当当前字符串满足(左括号数量>=右括号数量)，才有可能有效，当左右括号都用完了就得到一条有效字符串。
void generate_str(int i, int j, int *k, int n, char *stack, char **result)
{
    if(i<j) return;//当前字符串，左括号数量少于右括号数量，则这个字符串肯定不满足要求；
    if (i < n){
        stack[i + j] = '(';
        generate_str(i + 1, j, k, n, stack, result);
    }
    if (j < n){ //if(i<j)可以合并进来，if(i>j) 表示当左括号多余右括号，才可以添加右括号。
        stack[i + j] = ')';
        generate_str(i, j + 1, k, n, stack, result);
    }
    if (i == j&&i==n){ //所有括号添加完毕,
        char *s = (char *)malloc(sizeof(char) * n * 2 + 1);
        strcpy(s, stack);
        result[*k] = s;
        *k = *k + 1;
    }
}

char **generateParenthesis(int n, int *returnSize)
{
    int left = 0, right = 0;
    char *s = (char *)malloc(sizeof(char) * n * 2 + 1);
    char **result = (char **)malloc(sizeof(char *) * n);
    s[n * 2] = 0;
    generate_str(0, 0, returnSize, n, s, result);
    free(s);
    return result;
}
```

#### [23. 合并K个升序链表](https://leetcode-cn.com/problems/merge-k-sorted-lists/)

```c
//方法：由各个链表的当前指针构成最小堆，然后在推根节点的链表指向下一位(不为空)或用堆最后一个节点的链表代替(为空)，然后调整堆。直到堆为空。
//还可以用桶排序。分而治之，递归，依次合并两个
#define MAXSIZE 10000
#define MAXVALUE 10001
//调整第i个节点为根的子堆，
void heapAdjust(struct ListNode** heap, int size, int i)
{
    heap[0] = heap[i];
    int son = i * 2;
    while (son <= size) {
        if (son < size && heap[son + 1]->val < heap[son]->val) //比较两个子节点的大小
            son++;
        if (heap[0]->val > heap[son]->val) { //比较最小子节点和父节点的大小
            heap[son / 2] = heap[son];
            son *= 2;
        } else //子树满足最小堆的要求
            break;
    }
    heap[son / 2] = heap[0];
}

struct ListNode* mergeKLists(struct ListNode** lists, int listsSize)
{
    //int *p[10] 指针数组，10个int指针构成的数组，int a[3][10]; p[1]=a[1],p++指向a[1][1]
    //int (*p)[10] 数组指针，指向数组长度为10的指针，p=a;p++指向a[1]
    struct ListNode* heap[MAXSIZE + 1] = { NULL }; //初始化指针，
    struct ListNode* head = (struct ListNode*)malloc(sizeof(struct ListNode));
    struct ListNode* p = head;
    int size = 0;
    for (int i = 0; i < listsSize; ++i) {
        if (lists[i])
            heap[++size] = lists[i];
    }
    //从有子节点的点开始建最小堆
    for (int i = size / 2; i > 0; --i)
        heapAdjust(heap, size, i);

    while (size > 1) {
        p->next = heap[1];
        p = heap[1];
        if (!heap[1]->next) { //链表遍历完，由堆里最后一个链表替代。堆大小减一
            heap[1] = heap[size];
            size--;
        } else
            heap[1] = heap[1]->next;
        heapAdjust(heap, size, 1);
    }
    p->next = heap[1];
    p = head->next;
    free(head);
    return p;
}
```

#### [24. 两两交换链表中的节点](https://leetcode-cn.com/problems/swap-nodes-in-pairs/)

```c
//方法：先前指针q、当前指针p、下一个指针p->next,修改三者的指向即可。如1-2-3-4
struct ListNode* swapPairs(struct ListNode* head)
{
    struct ListNode* p = head;
    struct ListNode* q = (struct ListNode*)malloc(sizeof(struct ListNode));
    q->next = head;
    head = q;
    while (p) {
        if (p->next) { //head(q)-1(p)-2-3-4
            q->next = p->next; //head(q)-2-3-4  1(p)-2-3-4
            p->next = p->next->next; //1(p)-3-4  head(q)-2-3-4
            q->next->next = p; //head(q)-2-1(p)-3-4
            q = p;
            p = p->next;
        } else
            break;
    }
    p = head->next;
    free(head);
    return p;
}
```

#### [25. K 个一组翻转链表](https://leetcode-cn.com/problems/reverse-nodes-in-k-group/)

```c
//方法：之前指针、当前指针，边遍历边反转。当满足k步后，连接上一段和该段；不满k步，再反转回去。
//另外可以先得长度为k的链表，再进行反转。
struct ListNode* reverseKGroup(struct ListNode* head, int k)
{
    if (k < 2 || !head || !head->next)
        return head;
    struct ListNode* p = (struct ListNode*)malloc(sizeof(struct ListNode));
    p->next = head;
    struct ListNode* start = p;
    while (head) {
        struct ListNode *pre = NULL, *begin = head;
        int i = 0;
        while (i < k && head){ // 每前进一步都进行反转
            struct ListNode* tmp = head->next;
            head->next = pre;
            pre = head;
            head = tmp;
            ++i;
        }
        if (i == k) { //长度满足，更新前起始节点
            start->next = pre;
            start = begin;
        } else if (!head) { //长度不满足，再次反转最后一段。
            head = pre;
            pre = NULL;
            while (head) {
                struct ListNode* tmp = head->next;
                head->next = pre;
                pre = head;
                head = tmp;
            }
            start->next = pre;
        }
    }
    head = p->next;
    free(p);
    return head;
}
```

#### [30. 串联所有单词的子串](https://leetcode-cn.com/problems/substring-with-concatenation-of-all-words/)

```c++
class Solution {
public:
    vector<int> findSubstring(string s, vector<string>& words) {
        unordered_map<string, vector<int>> wordsSet;
        int num = 0;
        for (auto w : words){ //统计各词的出现次数，并将每个词对应一个整数
            if (wordsSet.find(w) != wordsSet.end())
                wordsSet[w][0]++;
            else
                wordsSet[w] = {1, num++};
        }
        int n = s.size(), m = words[0].size(), k = words.size();
        vector<int> vis(num), ans; //vis每个词出现的次数

        for (int i = 0; i <= n - m * k; ++i){
            auto sub = s.substr(i, m);
            if (wordsSet.find(sub) != wordsSet.end()){
                for (auto w : wordsSet)
                    vis[w.second[1]] = w.second[0];
                int cnt = k, j = i;
                while (wordsSet.find(sub) != wordsSet.end() && vis[wordsSet[sub][1]] > 0){
                    vis[wordsSet[sub][1]]--;
                    j = j + m;
                    sub = s.substr(j, m);
                    cnt--;
                }
                if (cnt == 0)//所有词都出现
                    ans.push_back(i);
            }
        }
        return ans;
    }
};
//还可以从第一个单词的每个位置开始，一次移动每个单词的长度，这样在后续比较时，可以跳过一些不可能匹配的子串。
```

#### [32. 最长有效括号](https://leetcode-cn.com/problems/longest-valid-parentheses/)

```c++
//记录当前还有多少个左括号等待匹配，第i个位置上的值表示当前已经匹配的括号数。长度的更新只发生在出现右括号的时候
class Solution {
public:
    int longestValidParentheses(string s) {
        int i = 0, n = s.size(), st = 0;
        vector<int> preAns(n, 0);//存储已经匹配了括号数
        int maxLen = 0;
        for (int i = 0; i < n; ++i){
            if (s[i] == ')'){
                if (st == 0){
                    preAns[0] = 0;//没有左括号匹配，重新开始
                } else {  //有匹配的括号
                    preAns[st - 1] += preAns[st] + 2; //之前已经匹配的个数+后面匹配的个数+最新匹配的两个
                    preAns[st--] = 0;
                    maxLen = fmax(maxLen, preAns[st]);
                }
            }
            else
                st++;
        }
        return maxLen;
    }
};
//leetcode的方法更简洁；可以指比较左右括号的个数，右括号多，则一定不满足，相等则一定匹配，为了求左括号多的情况，反向遍历
```

#### [37. 解数独](https://leetcode-cn.com/problems/sudoku-solver/)

```c++
class Solution {
    const int n = 9;
    int m;
    vector<vector<bool>> vis;  //vector<vector<bool>> vis(27,vector<bool>(10,false));会出错
    vector<pair<int, int>> arr;
    bool dfs(vector<vector<char>> &board, int ii){
        if (ii == m)
            return true;
        int i = arr[ii].first, j = arr[ii].second;
        for (int k = 1; k < 10; ++k){
            int x = i / 3, y = j / 3;
            int i1 = x * 3 + y + 18, i2 = i, i3 = j + 9;
            if (!vis[i1][k] && !vis[i2][k] && !vis[i3][k]){
                vis[i1][k] = 1, vis[i2][k] = 1, vis[i3][k] = 1;
                board[i][j] = '0' + k;
                if (dfs(board, ii + 1))
                    return true;
                vis[i1][k] = 0, vis[i2][k] = 0, vis[i3][k] = 0;
            }
        }
        return false;
    }

public:
    void solveSudoku(vector<vector<char>>& board) {
        vis.assign(27, vector<bool>(10, false));
        for (int i = 0; i < n; ++i){
            for (int j = 0; j < n; ++j){
                if (board[i][j] != '.'){
                    int x = i / 3, y = j / 3, k = board[i][j] - '0';
                    vis[x * 3 + y + 18][k] = 1;
                    vis[i][k] = 1;
                    vis[j + 9][k] = 1;
                }
                else
                    arr.emplace_back(i, j); //emplace_back()原地构造，不需要触发拷贝构造和转移构造。
            }
        }
        m = arr.size();
        dfs(board, 0);
    }
};
```

#### [41. 缺失的第一个正数](https://leetcode-cn.com/problems/first-missing-positive/)

```c++
//在原数组上修改。用来记录某个数是否出现过。
class Solution {
public:
    int firstMissingPositive(vector<int>& nums) {
        int MinInt = 1, n = nums.size();
        for (int i = 0; i < n; ++i){
            if (nums[i] < 1)
                nums[i] = (n + 1);
        }
        for (int i = 0; i < n; ++i){
            int k = abs(nums[i]) - 1;
            if (k < n)
                nums[k] = -abs(nums[k]);
        }
        for (int i = 0; i < n; ++i){
            if (nums[i] > 0)
                return i + 1;
        }
        return n + 1;
    }
};
```



#### [48. 旋转图像](https://leetcode-cn.com/problems/rotate-image/)

```c++
//围绕中心点逐步旋转
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int n=matrix.size();
        for(int i=0;i<n/2;++i){//由外往里的层数
            for(int j=i;j<n-i-1;++j){//处理每一层
                int t=matrix[i][j];
                matrix[i][j]=matrix[n-j-1][i];
                matrix[n-j-1][i]=matrix[n-i-1][n-j-1];
                matrix[n-i-1][n-j-1]=matrix[j][n-i-1];
                matrix[j][n-i-1]=t;
            }
        }
    }
};
//可以先水平翻转，再对角线翻转
```

#### [73. 矩阵置零](https://leetcode-cn.com/problems/set-matrix-zeroes/)

```c++
class Solution {
public:
	void setZeroes(vector<vector<int>>& matrix) {
		int n = matrix.size(), m = matrix[0].size();
		int curZero = 0, nextZero = 0;
		for (int i = 0; i < m; ++i) { //统计当前行是否有0
			if (matrix[0][i] == 0) {
				curZero = 1;
				break;
			}
		}
		for (int i = 1; i <= n; ++i) {
			int i_1 = i - 1;
			nextZero = 0;
			if (i < n) { 
				for (int j = 0; j < m; ++j) {
					if (matrix[i][j] == 0) { //先统计当前行有0无
						int k = i_1;
						while (k >= 0)matrix[k--][j] = 0;
						nextZero = 1;
					}
					else if (matrix[i_1][j] == 0) { //再看上一行是否为0
						matrix[i][j] = 0;
					}

				}
			}
			if (curZero) { //将上一行清零
				for (int j = 0; j < m; ++j)matrix[i_1][j] = 0;
			}
			curZero = nextZero;//当前行变为上一行
		}

	}
};
```



#### [92. 反转链表 II](https://leetcode-cn.com/problems/reverse-linked-list-ii/)

```c++
class Solution {
public:
    ListNode *reverseBetween(ListNode *head, int left, int right) {
        if (left == right)
            return head;
        int i = 1;
        ListNode h(0, head);
        ListNode *p = head, *p_l = &h, *pre = &h;
        while (i < left) {  //找到left对应的节点p
            pre = p;
            p = p->next;
            i++;
        }
        p_l = pre;//不进行翻转的前一个节点
        ListNode *p_r = p;//进行翻转的第一个节点，
        pre = p, p = p->next, i++;
        while (i <= right) { //需要翻转的节点
            ListNode *q = p->next;
            p->next = pre;
            pre = p, p = q;
            i++;
        }
        p_l->next = pre, p_r->next = p;//将left前面的链表、翻转链表、right后面的链表 连接起来

        return h.next;
    }
};
/*
for (int i = 0; i < right - left; i++) {
    next = cur->next;
    cur->next = next->next;
    next->next = pre->next;
    pre->next = next;
}
*/
```



#### [115. 不同的子序列](https://leetcode-cn.com/problems/distinct-subsequences/)

```c++
//可以进一步优化，只需要两行的dp，存储上一行和当前行；dp[i][j]表示字符串s的[:,i]里匹配t[:j]的子序列个数
class Solution {
public:
    int numDistinct(string s, string t) {
        int n = s.size(), m = t.size();f
        if (n < m)
            return 0;
        vector<vector<long>> dp(2, vector<long>(n + 1, 0));
        for (int i = 0; i <= n; ++i)
            dp[0][i] = 1;
        int row, prerow = 0;
        for (int i = 1; i <= m; i++) {
            row = i & 1;
            dp[row][i - 1] = 0;
            for (int j = i; j <= n; j++) {
                cout << "(" << t[i - 1] << "," << s[j - 1] << "),";
                if (t[i - 1] == s[j - 1]) { //i-1和j-1新匹配个数+之前已经匹配的个数
                    dp[row][j] = dp[row][j - 1] + dp[prerow][j - 1]; 
                } else { //不产生新匹配的子序列，
                    dp[row][j] = dp[row][j - 1];
                }
            }
            prerow = row;
        }
        return dp[row][n];
    }
};
```

#### [119. 杨辉三角 II](https://leetcode-cn.com/problems/pascals-triangle-ii/)

```c
//方法：杨辉三角为二项式（两个数之和的整数次幂）的系数，有规律，组合。
//也可以一层一层的算。
int *getRow(int rowIndex, int *returnSize)
{
    int *ans = (int *)malloc(sizeof(int) * (rowIndex + 1));
    ans[0] = ans[rowIndex] = 1;
    for (int i = 1; i < rowIndex; ++i){
        if (i <= rowIndex / 2)
            ans[i] = (long long)ans[i - 1] * (rowIndex - i + 1) / i; //注意运算可能溢出。
        else
            ans[i] = ans[rowIndex - i];
    }
    *returnSize = rowIndex + 1;
    return ans;
}
```

#### [124. 二叉树中的最大路径和](https://leetcode-cn.com/problems/binary-tree-maximum-path-sum/)

```c++
class Solution {
    int maxSum = -2000;
    int dfs(TreeNode *root, int sum) {
        if (root == nullptr)
            return 0;
        sum += root->val;
        maxSum = max(sum, maxSum); //某条路径执行到当前点的最大值
        sum = max(sum, 0);
        int leftSum = dfs(root->left, sum);
        leftSum += root->val;
        leftSum = max(0, leftSum); 
        sum = max(sum, leftSum); ////左边子树某点出发经过该点
        int rightSum = dfs(root->right, sum);
        rightSum += root->val;
        rightSum = max(0, rightSum);
        return max(rightSum, leftSum); //经过该点返回的最大值
    }

public:
    int maxPathSum(TreeNode *root) {
        dfs(root, 0);
        return maxSum;
    }
};
/*更简洁的版本
int dfs(TreeNode *root) {
    if (root == nullptr)
        return 0;
    int leftSum = dfs(root->left);
    int rightSum = dfs(root->right);
    leftSum = max(leftSum, 0);
    rightSum = max(rightSum, 0);
    int sum = leftSum + rightSum + root->val;
    maxSum = max(sum, maxSum);
    return max(leftSum, rightSum) + root->val;
}*/
```



#### [131. 分割回文串](https://leetcode-cn.com/problems/palindrome-partitioning/)

```c++
//使用递归，不断尝试不同长度的分割（从0当前位置到n最后一个位置），还可以将求回文串标志加到搜索里面。
//记忆化搜索，需要另一个函数来求标志的值，会出现递归调用的情况，当复杂度一样的，
class Solution{
    vector<string> tmp;
    vector<vector<bool>> flag; //位置i到j是否为回文串。
    vector<vector<string>> ans;
    int n;
    void dfs(int i, string &s){
        if (i == n){
            ans.push_back(tmp);
            return;
        }
        for (int j = i; j < n; ++j){
            if (flag[i][j]){
                tmp.push_back(s.substr(i, j - i + 1));
                dfs(j + 1, s);
                tmp.pop_back();
            }
        }
    }

public:
    vector<vector<string>> partition(string s){
        n = s.size();
        flag.assign(n, vector<bool>(n, true));
        //因为我们会用到ij中间(i+1到j-1)的字符串是否匹配。所以必须先求之间是否回文。三角形范围从小到大
        for (int i = n - 1; i >= 0; --i){ //矩阵的右下角
            for (int j = i + 1; j < n; ++j)
                flag[i][j] = (s[i] == s[j]) && flag[i + 1][j - 1];
        }
        //for (int i = 0; i <n ; ++i){ //矩阵的左下角
        //    for (int j = i-1; j >=0; --j)
        //        flag[i][j] = (s[i] == s[j]) && flag[i - 1][j + 1];
        //}
        dfs(0, s);
        return ans;
    }
};
```

#### [132. 分割回文串 II](https://leetcode-cn.com/problems/palindrome-partitioning-ii/)

```c++
//同上，使用相同的方法求所有i到j是否为回文串。然后使用DP[i]表示0-i分割的最小次数，由0-i是否为回文串，DP[i]=min{DP[j]}+1（不是）或0（是）;
//从左往右依次新加一个字符s[i]，求DP[i]，之前位置上DP已经求得，新加的s[i]可能使得DP[i]=min{DP[j]}+1;
class Solution {
public:
    int minCut(string s){
        int n = s.size();
        vector<vector<bool>> f(n, vector<bool>(n, true));
        for (int i = n - 1; i >= 0; --i){
            for (int j = i + 1; j < n; ++j){
                f[i][j] = s[i] == s[j] && f[i + 1][j - 1];
            }
        }
        vector<int> ans(n, INT_MAX);
        for (int i = 0; i < n; ++i){
            if (f[0][i]){
                ans[i] = 0;
                continue;
            }
            for (int j = 0; j < i; ++j){
                if (f[j + 1][i])
                    ans[i] = min(ans[i], ans[j] + 1);
            }
        }
        return ans[n - 1];
    }
};
```

#### [149. 直线上最多的点数](https://leetcode-cn.com/problems/max-points-on-a-line/)

```c++
//对于节点i,我们只需统计i+1到n的节点与i构成的线，取点数最大值的线。不需要考虑i之前的点，因为之前通过i和之前的点的线已经考虑过了。
//新加一个点i，需要遍历之前节点，确定到线，线上点数加一，注意：去重。
class Solution {
    int n;
    int max_lines_contains_i(vector<vector<int>> &points, int i) {//求在一条线上的点数最大的值。
        unordered_map<double, int> line;
        int duplicate = 0, verti = 1;
        int maxp = 0;
        int x1 = points[i][0], y1 = points[i][1];
        for (int j = i + 1; j < n; ++j) {
            int x2 = points[j][0], y2 = points[j][1];
            if (x1 == x2 && y1 == y2)
                duplicate++;
            else if (x1 == x2) {
                verti++;
            } else {
                double scope = 1.0 * (y1 - y2) / (x1 - x2);
                if (line.count(scope))
                    line[scope]++;
                else
                    line[scope] = 2;
                maxp = max(line[scope], maxp);
            }
        }
        return max(maxp, verti) + duplicate;
    }

public:
    int maxPoints(vector<vector<int>> &points) {
        n = points.size();
        if (n < 3)
            return n;
        int maxp = 1;
        for (int i = 0; i < n - 1; ++i) {
            maxp = max(max_lines_contains_i(points, i), maxp);
        }
        return maxp;
    }
};
```

#### [150. 逆波兰表达式求值](https://leetcode-cn.com/problems/evaluate-reverse-polish-notation/)

```c++
//没有考虑单操作数，如3-(-(1+1)) 3 1 1 + - - 当作非法输入
class Solution {
public:
	int evalRPN(vector<string>& tokens) {
		stack<int>num;
		for (auto s : tokens) {
			if (isdigit(s[s.size() - 1])) {//数可能为负数
				int n = stoi(s);
				num.push(n);
			}
			else {
				int n1, n2, x;
				n2 = num.top(), num.pop();
				n1 = num.top(), num.pop(); //后弹出的为前一个操作数
				if (s == "+")x = n1 + n2;
				else if (s == "-")x = n1 - n2;
				else if (s == "*")x = n1 * n2;
				else x = n1 / n2;
				num.push(x);
			}
		}
		return num.top();
	}
};
```



#### [224. 基本计算器](https://leetcode-cn.com/problems/basic-calculator/)

```c++
//官方代码更简洁
class Solution{
public:
    int calculate(string s){
        int n = s.size();
        int localSum = 0;
        stack<int> num;
        stack<char> ope;
        for (int i = 0; i < n; ++i){
            if (isdigit(s[i])){
                int k = 0;
                while (isdigit(s[i])){
                    k = k * 10 + (s[i] - '0'); //加括号防止超出int类型范围
                    i++;
                }
                if (ope.empty() || ope.top() == '(')//前面没有操作符
                    localSum += k;
                else {                     //前面有操作符，需要删掉操作符
                    if (ope.top() == '+') 
                        localSum += k;
                    else if (ope.top() == '-')
                        localSum -= k;
                    ope.pop();
                }
            }
            if (s[i] == ' ')
                continue;
            if (s[i] == '(') { //计算新的子表达式结构，存储之前的和
                num.push(localSum);
                localSum = 0;
                ope.push('(');
            }
            else if (s[i] == ')'){ //子表达式计算结束
                int k = localSum;
                localSum = num.top();
                while (!ope.empty() && ope.top() == '(') //弹出所有出结果了的子表达式
                    ope.pop();
                if (ope.empty() || ope.top() == '+')
                    localSum += k;
                else if (ope.top() == '-')
                    localSum -= k;
                if (!ope.empty()) //子表达式为总表达式
                    ope.pop();
                num.pop();
            }
            else //压入操作符符号
                ope.push(s[i]);
        }
        return localSum;
    }
};

```

#### [227. 基本计算器 II](https://leetcode-cn.com/problems/basic-calculator-ii/)

```c++
//无括号的计算器，使用双栈
class Solution{
    stack<int> num;
    stack<char> opt;
    int compute(){
        int p = num.top();num.pop();
        int q = num.top();num.pop();
        char c = opt.top();opt.pop();
        if (c == '*')
            return q * p;
        else if (c == '/')
            return q / p;
        else if (c == '+')
            return q + p;
        return q - p;
    }

public:
    int calculate(string s){
        int n = s.size(), i = 0, ans = 0;
        unordered_map<char, int> pri{{'*', 1}, {'/', 1}, {'+', 0}, {'-', 0}};
        //pri['*']=1,pri['/']=1,pri['+']=0,pri['-']=0;
        while (i < n){
            if (s[i] == ' ')
                i++;
            else if (!isdigit(s[i])){
                while (!opt.empty() && pri[s[i]] <= pri[opt.top()])
                    num.push(compute());
                opt.push(s[i]);
                i++;
            }else{
                int k = 0;
                while (i < n && isdigit(s[i]))
                    k = k * 10 + (s[i++] - '0');
                num.push(k);
            }
        }
        while (!opt.empty())
            num.push(compute());
        return num.top();
    }
};
//还可以用栈存储*和/的计算结果，后面再求总和
```

#### [232. 用栈实现队列](https://leetcode-cn.com/problems/implement-queue-using-stacks/)

```c++
//一个队列作为压入队栈，一个作为弹出栈，队列当要弹出元素时，如果弹出栈为空，将压入栈的元素压入到弹出栈中。
class MyQueue {
public:
    stack<int> inStack, outStack;
    void in2out(){
        while (!inStack.empty()){
            int x = inStack.top();
            outStack.push(x);
            inStack.pop();
        }
    }
    /** Initialize your data structure here. */
    MyQueue() {}

    /** Push element x to the back of queue. */
    void push(int x){
        inStack.push(x);
    }
    /** Removes the element from in front of queue and returns that element. */
    int pop(){
        if (outStack.empty())
            in2out();
        int x = outStack.top();
        outStack.pop();
        return x;
    }
    /** Get the front element. */
    int peek(){
        if (outStack.empty())
            in2out();
        return outStack.top();
    }
    /** Returns whether the queue is empty. */
    bool empty(){
        return inStack.empty() && outStack.empty();
    }
};
```

#### [300. 最长递增子序列](https://leetcode-cn.com/problems/longest-increasing-subsequence/)

```c++
class Solution {
public:
    int lengthOfLIS(vector<int> &nums) {
        int n = nums.size(), maxLen = 1;
        vector<int> dp(n, 1);
        for (int i = 1; i < n; ++i) {
            for (int j = 0; j < i; ++j) {
                if (nums[i] > nums[j]) {
                    dp[i] = max(dp[i], dp[j] + 1);
                    maxLen = max(maxLen, dp[i]);
                }
            }
        }
        return maxLen;
    }
};
```

#### [331. 验证二叉树的前序序列化](https://leetcode-cn.com/problems/verify-preorder-serialization-of-a-binary-tree/)

```c++
//统计树最少未遍历的节点数cnt，遍历一个新节点，cnt--;遇到数字:cnt+=2;
class Solution {
public:
    bool isValidSerialization(string preorder){
        int n = preorder.size(), i = 0, cnt = 1;
        while (i < n){
            if (preorder[i] == ',')
                i++;
            else{
                if (!cnt)
                    return false;
                cnt--;
                if (preorder[i] != '#')
                    cnt += 2;
                while (i < n && preorder[i] != ',')
                    i++;
            }
        }
        return cnt == 0;
    }
};
```

#### [341. 扁平化嵌套列表迭代器](https://leetcode-cn.com/problems/flatten-nested-list-iterator/)

```c++
//更新方法值得学习
class NestedIterator {
	stack<pair<vector<NestedInteger>::iterator, vector<NestedInteger>::iterator>> st;
	void update() {
		while (!st.empty()) {      //压入之后，会将没有元素的嵌套表弹出来
			if (st.top().first == st.top().second) {
				st.pop();
				continue;
			}
			if (st.top().first->isInteger()) {//检测到当前区间的指针为整数。
				break;
			}

			auto& it = st.top().first++->getList(); //压入新嵌套表时，上一个指针后移一位。引用
			st.emplace(it.begin(), it.end());      //
		}
	}
public:
	NestedIterator(vector<NestedInteger>& nestedList) {
		st.emplace(nestedList.begin(), nestedList.end());
		update();
	}

	int next() {
		int x = st.top().first++->getInteger();
		update();
		return x;
	}

	bool hasNext() {
		return !st.empty();
	}
};
```



#### [354. 俄罗斯套娃信封问题](https://leetcode-cn.com/problems/russian-doll-envelopes/)

```c++
//方法：放的方法为：根据大小，对于长和宽都满足要求的（都大于前一封），依次放；如果只有一条边满足要求，放最小的且满足要求的；
//问题：我们不应该放某条过大的边，因为这样会导致后面本来更多满足要求信封无法放入。所以对一条边排好序后，再对另一条边排序，为了放入更多的信封，我们可能会舍弃掉之前的信封。
class Solution{
public:
    int maxEnvelopes(vector<vector<int>> &envelopes) {
        sort(envelopes.begin(), envelopes.end(), [](const auto &e1, const auto &e2) {
            return e1[0] < e2[0] || (e1[0] == e2[0] && e1[1] > e2[1]);
        });
        int n = envelopes.size();
        /*//错误，没有考虑中间某个信封过大，导致后面本可以放进的信封无法放入。
        auto pre=envelopes[0];
        auto f=[](const auto& e1,const auto& e2){return e1[0]<e2[0] && e1[1]<e2[1];};
        int cnt=1;
        for(int i=1;i<n;++i){
            if(f(pre,envelopes[i])){
                cnt++;
                pre=envelopes[i];
                //cout<<pre[0]<<","<<pre[1]<<"->";
            }
        }
        return cnt;
        */
        //动态规划，用dp[i]存储当前可以放入i的最大信封数，即所有小于信封i的 信封k的位置的 值的最大值+1；
        vector<int> dp(n, 1);
        for (int i = 0; i < n; ++i){
            for (int j = 0; j < i; ++j){
                if (envelopes[i][1] > envelopes[j][1] && dp[i] < dp[j] + 1) //信封j后能放下i,
                    dp[i] = dp[j] + 1;
            }
        }
        return *max_element(dp.begin(), dp.end());
        /*方法二：用f来存储信封应该在的位置，使得从0到该位置的信封满足要求，递增。0到当前的长度 表示 包含当前位置上的信封 所构成的最大信封数。
        vector<int> f = {envelopes[0][1]};
        for (int i = 0; i < n; ++i){
            int num = envelopes[i][1];
            if (num > f.back())
                f.push_back(num);
            else{
                auto it = lower_bound(f.begin(), f.end(), num);
                *it = num;
            }
        }
        return f.size();*/
    }
};
```

#### [420. 强密码检验器](https://leetcode-cn.com/problems/strong-password-checker/)

```c++

struct cmp {
    bool operator()(const int a, const int b) { return a % 3 > b % 3; }
};

class Solution {
public:
    int strongPasswordChecker(string password) {
        int n = password.size();
        char pre;
        vector<int> rep;
        int digit = -1, lower = -1, upper = -1, dup = 0;
        for (int i = 0; i < n; ++i) {
            if (i > 0 && pre == password[i])
                dup++;
            else {
                if (dup > 2)
                    rep.push_back(dup);
                dup = 1;
            }
            if (isdigit(password[i]))
                digit++;
            else if (password[i] >= 'A' && password[i] <= 'Z')
                upper++;
            else if (password[i] >= 'a' && password[i] <= 'z')
                lower++;
            pre = password[i];
        }
        int ans = 0;
        if (dup > 2)
            rep.push_back(dup);
        if (upper > -1 && digit > -1 && lower > -1 && rep.empty() && n > 5 &&
            n < 21)
            return 0;
        int off = 0, repcnt = 0, change = 0;
        digit = digit > -1 ? 0 : 1;
        lower = lower > -1 ? 0 : 1;
        upper = upper > -1 ? 0 : 1;
        change = digit + lower + upper;
        for (int i = 0; i < rep.size(); ++i)
            repcnt += rep[i] / 3;
        if (n < 6) {
            off = 6 - n;
            while (off > 0 || change > 0 || repcnt > 0)
                off--, change--, repcnt--, ans++;
        } else if (n <= 20) {
            ans = max(repcnt, change);
        } else {
            off = n - 20;
            priority_queue<int, vector<int>, cmp> que(rep.begin(), rep.end());
            while (off > 0 && !que.empty()) {
                int x = que.top();
                que.pop();
                if (x / 3 - (x - 1) / 3)
                    repcnt--;
                x--, off--, ans++;
                if (x > 2)
                    que.push(x);
            }
            while (off > 0)
                off--, ans++;
            while (repcnt > 0 || change > 0)
                change--, repcnt--, ans++;
        }
        return ans;
    }
};
```

#### [424. 替换后的最长重复字符](https://leetcode-cn.com/problems/longest-repeating-character-replacement/)

```c++
//方法：滑动窗口，要求的字符串是连续的，替换的字符是子串中出现次数较少的字符，且这些字符的总数不大于k。
//给定一个窗口，找里面字符出现最多的字符作为重复字符。窗口长度-其个数<=k，所以只有最大出现次数变大，窗口才可能变大。
//依次往窗口里添加字符，在满足要求的情况下，窗口不断增大，当不满足时，因为是连续的，去掉最左边。
int characterReplacement(char* s, int k)
{
    int num[26]; //满足要求的区间内各字符的个数
    memset(num, 0, sizeof(num));
    int n = strlen(s);
    int maxn = 0;
    int left = 0, right = 0;
    while (right < n) {
        num[s[right] - 'A']++; //字符数加一
        maxn = max(maxn, num[s[right] - 'A']); //区间内出现的最大字符个数
        if (right - left + 1 - maxn > k) {      //区间内需要替换的字符个数>最大替换次数，不满足要求，去掉最左边的字符。
            num[s[left] - 'A']--;               //则左边字符的个数减一
            left++;
        }
        right++;
    }
    return right - left;
}
```



#### [448. 找到所有数组中消失的数字](https://leetcode-cn.com/problems/find-all-numbers-disappeared-in-an-array/)

```c
//方法：基本方法是申请一个大小为n的数组，用来标记下标为i的数是否出现。因为值全部小于n，所以可以利用原数组来表示，如果下标为i的数出现，则i位置上的数就加n。
//或者可以进行排序，排第i个位置时，往后查找为值为i的地址，并交互，则缺失的数会找不到。
int *findDisappearedNumbers(int *nums, int numsSize, int *returnSize)
{
    for (int i = 0; i < numsSize; ++i)
        nums[(nums[i] - 1) % numsSize] += numsSize;
    int *ans = (int *)malloc(sizeof(int) * numsSize);
    *returnSize = 0;
    for (int i = 0; i < numsSize; ++i){
        if (nums[i] <= numsSize)
            ans[(*returnSize)++] = i + 1;
    }
    return ans;
}
```

#### [480. 滑动窗口中位数](https://leetcode-cn.com/problems/sliding-window-median/)

```c
//方法：构建两个堆，一个最大堆存储前半部分，一个最小堆存储后半部分，每次只需比较两个堆顶的值和新加入的值，并删掉窗口去掉的值，然后不断维护两个堆。
//窗口长度为奇数时，最大堆存储的个数比最小堆多一个，则大堆堆顶的值即为中位数。
//leetcode使用了优先队列和延迟删除，主要堆顶的元素不是需要删除的元素，则其作为中位数就不会出错，相当于两个队列将窗口同时往两边扩大。
#define MAXSIZE 100000
typedef struct node {
    int i, v;
} node;

void maxHeapPush(node* heap, int* s, node k)
{
    int son = ++(*s);
    while (son / 2 > 0 && heap[son / 2].v < k.v) {
        heap[son] = heap[son / 2];
        son /= 2;
    }
    heap[son] = k;
}
void maxHeapPop(node* heap, int* s)
{
    if (*s == 0)
        return;
    //node k=heap[1];
    node v = heap[(*s)--];
    int son = 2;
    while (son <= *s) { //只需要与子节点中最大的比较，大于最大子节点，跳出，其他情况都需要交换。
        if (son + 1 <= *s && heap[son + 1].v > heap[son].v)
            son++;
        if (v.v < heap[son].v)
            heap[son / 2] = heap[son], son *= 2;
        else
            break;
    }
    heap[son / 2] = v;
}

void minHeapPush(node* heap, int* s, node k)
{
    int son = ++(*s);
    while (son / 2 > 0 && heap[son / 2].v > k.v) {
        heap[son] = heap[son / 2];
        son /= 2;
    }
    heap[son] = k;
}
void minHeapPop(node* heap, int* s)
{
    if (*s == 0)
        return;
    //node k=heap[1];
    node v = heap[(*s)--];
    int son = 2;
    while (son <= *s) {
        if (son + 1 <= *s && heap[son + 1].v < heap[son].v)
            son++;
        if (v.v > heap[son].v)
            heap[son / 2] = heap[son], son *= 2;
        else
            break;
    }
    heap[son / 2] = v;
}

void adjust(node* maxHeap, node* minHeap, int* maxCnt, int* minCnt, node k)
{
    node x = maxHeap[1], y = minHeap[1];
    if (*maxCnt <= *minCnt) {
        if (*maxCnt == 0 || k.v <= y.v) //最开始时，大堆个数为0，小堆个数也为0，直接将元素添加到大堆中。当k=2且，大堆里的元素删除了，此时maxCnt==0,也可直接添加元素，因为中位数为两个堆顶元素的平均值。
            maxHeapPush(maxHeap, maxCnt, k);
        else {
            minHeapPop(minHeap, minCnt);
            minHeapPush(minHeap, minCnt, k);
            maxHeapPush(maxHeap, maxCnt, y);
        }
    } else {  
        if (k.v >= x.v)//向小堆里添加元素时，大堆一定不为空，需要比较大堆顶和插入元素的大小
            minHeapPush(minHeap, minCnt, k);
        else {
            maxHeapPop(maxHeap, maxCnt);
            maxHeapPush(maxHeap, maxCnt, k);
            minHeapPush(minHeap, minCnt, x);
        }
    }
}

int maxHeapDeletek(node* heap, int* s, node k)
{
    int i = 1;
    while (i <= *s && k.i != heap[i].i)
        i++;
    if (i > *s)
        return 0;

    node x = heap[(*s)--];
    int son = i, p = son / 2;
    if (p > 0 && x.v > heap[p].v) {
        while (p > 0 && x.v > heap[p].v) {
            heap[son] = heap[p];
            son /= 2;
            p = son / 2;
        }
        heap[son] = x;
    } else {
        son = i * 2;
        while (son <= *s) {
            if (son + 1 <= *s && heap[son + 1].v > heap[son].v)
                son++;
            if (heap[son].v > x.v)
                heap[son / 2] = heap[son], son *= 2;
            else
                break;
        }
        heap[son / 2] = x;
    }
    return 1;
}
int minHeapDeletek(node* heap, int* s, node k)
{
    int i = 1;
    while (i <= *s && k.i != heap[i].i)
        i++;
    if (i > *s)
        return 0;

    node x = heap[(*s)--];
    int son = i, p = son / 2;
    if (p > 0 && x.v < heap[p].v) {
        while (p > 0 && x.v < heap[p].v) {
            heap[son] = heap[p];
            son /= 2;
            p = son / 2;
        }
        heap[son] = x;  //不能用heap[p * 2] = x;因为可能p*2和 p/2之前的值不一样,
    } else {
        son = i * 2;
        while (son <= *s) {
            if (son + 1 <= *s && heap[son + 1].v < heap[son].v)
                son++;
            if (heap[son].v < x.v)
                heap[son / 2] = heap[son], son *= 2;
            else
                break;
        }
        heap[son / 2] = x;
    }
    return 1;
}
// void print(node* heap, int cnt, char* s)
// {
//     printf("%s:[", s);
//     for (int i = 1; i <= cnt; ++i) {
//         printf("(i=%d,v=%d),", heap[i].i, heap[i].v);
//         printf("];");
//     }
// }
// void minCheck(node* heap, int cnt)
// {
//     for (int i = 1; i < cnt; ++i) {
//         if (i * 2 <= cnt && heap[i].v > heap[i * 2].v) {
//             printf("i=%d", i);
//             break;
//         }
//         if (i * 2 + 1 <= cnt && heap[i].v > heap[i * 2 + 1].v) {
//             printf("i=%d", i);
//             break;
//         }
//     }
// }
double* medianSlidingWindow(int* nums, int numsSize, int k, int* returnSize)
{
    *returnSize = numsSize - k + 1;
    double* ans = (double*)malloc(sizeof(double) * (*returnSize));

    node maxHeap[MAXSIZE], minHeap[MAXSIZE];
    int minCnt = 0, maxCnt = 0, i = 0;
    node n, m;
    for (; i < k; ++i) { //由第一个窗口构建堆
        n.v = nums[i], n.i = i;
        adjust(maxHeap, minHeap, &maxCnt, &minCnt, n);
    }

    //print(maxHeap, maxCnt, "max");
    //print(minHeap, minCnt, "min");
    //maxCheck(maxHeap, maxCnt), minCheck(minHeap, minCnt);
    for (int j = 0; i <= numsSize; ++i, ++j) {
        node x = maxHeap[1], y = minHeap[1];
        if (k % 2)
            ans[j] = (double)x.v;
        else
            ans[j] = ((double)x.v + (double)y.v) / 2;//两个相加可能超过int的范围

        if (i == numsSize)  //判断是否继续移动窗口
            break;
        n.v = nums[i], n.i = i;  
        m.v = nums[j], m.i = j;
        if (x.v == y.v) {  //找到被窗口移除的元素，并从堆中删除
            int f = maxHeapDeletek(maxHeap, &maxCnt, m);
            if (f == 0)
                minHeapDeletek(minHeap, &minCnt, m);
        } else if (m.v <= x.v) {
            maxHeapDeletek(maxHeap, &maxCnt, m);
        } else {
            minHeapDeletek(minHeap, &minCnt, m);
        }
        //maxCheck(maxHeap, maxCnt), minCheck(minHeap, minCnt);
        // print(maxHeap,maxCnt,"max");
        // print(minHeap,minCnt,"min");
        adjust(maxHeap, minHeap, &maxCnt, &minCnt, n);
        //maxCheck(maxHeap, maxCnt), minCheck(minHeap, minCnt);
        // print(maxHeap,maxCnt,"max");
        // print(minHeap,minCnt,"min");
    }
    return ans;
}
```

#### [485. 最大连续1的个数](https://leetcode-cn.com/problems/max-consecutive-ones/)

```c
//方法：遍历，如果出现0则计数清零，否则加一
int findMaxConsecutiveOnes(int *nums, int numsSize){
    int maxCnt = 0;
    for (int i = 0; i < numsSize; ++i){
        int cnt = 0;
        while (i < numsSize && nums[i])
            i++, cnt++;
        if (maxCnt < cnt)
            maxCnt = cnt;
    }
    return maxCnt;
}
```

#### [503. 下一个更大元素 II](https://leetcode-cn.com/problems/next-greater-element-ii/)

```c++
//方法：用一个栈来存储未找到下一个更大元素的元素，则栈里的元素应该递减的；如果当前元素大于栈里的一些元素，则找到了这些元素的下一个更大元素，并将这些元素弹出。然后将当前元素加入栈；因为是循环查看的，所以遍历完数组后，应该再遍历一下，找栈里剩余元素的下一个更大元素。
class Solution{
public:
    vector<int> nextGreaterElements(vector<int> &nums){
        stack<int> stk;
        int n = nums.size();
        vector<int> ans(n, -1);
        for (int i = 0; i < 2 * n - 1; ++i){
            while (!stk.empty() && nums[stk.top()] < nums[i % n]){
                ans[stk.top()] = nums[i % n];
                stk.pop();
            }
            stk.push(i % n);
        }
        return ans;
    }
};
```

#### [561. 数组拆分 I](https://leetcode-cn.com/problems/array-partition-i/)

```c
//方法：要使最小值的和最大，则需最小值尽可能大，所以为每个最大值配第二大值构成一对，则和最大。
int cmp(const void *a, const void *b){
    return *(int *)a - *(int *)b;
}
int arrayPairSum(int *nums, int numsSize){
    qsort(nums, numsSize, sizeof(int), cmp);
    int sum = 0;
    for (int i = 0; i < numsSize; i = i + 2)
        sum += nums[i];
    return sum;
}
```

#### [564. 寻找最近的回文数](https://leetcode-cn.com/problems/find-the-closest-palindrome/)

```c++
//将左半部分交换到右边，三种操作：1）直接交换得到回文数，2）左边减一，再交换得到的回文数；3）左边加一，再交换得到的回文数。
//这三种操作得到的回文数是最近的三个。分别对应的差值范围位abs(revleft-right),pow(10,n/2)-abs(revleft-right)
template <class outtype, class intype> outtype convert(intype val) { //使用字符串流进行类型转换
    stringstream stream;
    stream << val;
    outtype out;
    stream >> out;
    return out;
}
class Solution {
public:
    string nearestPalindromic(string n) {
        int k = n.size();
        int m = k / 2;
        if (k == 1) {
            k = convert<int>(n) - 1; //1的答案是0，0的答案-1
            return convert<string>(k);
        }
        long base = pow(10, m);
        string left_str = n.substr(0, (k + 1) / 2);
        string right_str = n.substr(k - m, m);

        long left_num = convert<long>(left_str);
        long right_num = convert<long>(right_str);
        //减一后再翻转
        string left_minus_str = convert<string>(left_num - 1);
        long left_minus_num;
        if (left_minus_str.size() < left_str.size() || left_num == 1) { //位数减少
            left_minus_num = 1 + right_num;
            left_minus_str = string(k - 1, '9');
        } else {
            string str = left_minus_str.substr(0, m);
            reverse(str.begin(), str.end());
            long rev = convert<long>(str);
            left_minus_num = base - rev + right_num;
            left_minus_str += str;
        }
        //加一后再翻转
        string left_plus_str = convert<string>(left_num + 1);
        long left_plus_num;
        if (left_plus_str.size() > left_str.size()) { //位数增多
            left_plus_num = base - right_num;
            left_plus_str = "1";
            left_plus_str += string(k - 1, '0');
            left_plus_str += "1";
        } else {
            string str = left_plus_str.substr(0, m);
            reverse(str.begin(), str.end());
            long rev = convert<long>(str);
            left_plus_num = base - right_num + rev;
            left_plus_str += str;
        }
        //直接翻转
        string rev_left_str = n.substr(0, m);
        reverse(rev_left_str.begin(), rev_left_str.end());
        long left_rev_num = convert<long>(rev_left_str);
        left_rev_num = abs(right_num - left_rev_num);
        rev_left_str = left_str + rev_left_str;

        if (left_rev_num == 0) {
            return left_minus_num > left_plus_num ? left_plus_str : left_minus_str;
        } else if (left_rev_num < left_minus_num) {
            return left_rev_num > left_plus_num ? left_plus_str : rev_left_str;
        }
        return left_minus_num > left_plus_num ? left_plus_str : left_minus_str;
    }
};
```

#### [566. 重塑矩阵](https://leetcode-cn.com/problems/reshape-the-matrix/)

```c
int **matrixReshape(int **nums, int numsSize, int *numsColSize, int r, int c, int *returnSize, int **returnColumnSizes)
{//使用 matrixReshape(*nums[],numSize,numsColSize[],r,c,&returnSize,&*returnColumnSizes);后面两个因为要修改，所以需要再使用一层指针
    if (numsColSize[0] * numsSize != r * c || r == numsSize){
        *returnColumnSizes = numsColSize;
        *returnSize = numsSize;
        return nums;
    }
    int **ans = (int **)malloc(sizeof(int *) * r);
    int i = 0, k = 0;
    *returnColumnSizes = (int *)malloc(sizeof(int) * r); //加*表示修改其值。
    while (i < r * c){
        int j = 0;
        int *col = (int *)malloc(sizeof(int) * c);
        while (j < c){
            col[j++] = nums[i / numsColSize[0]][i % numsColSize[0]];
            i++;
        }
        ans[k] = col;
        (*returnColumnSizes)[k++] = c;  //*returnColumnSizes为一个数组地址，[]的优先级高于*
    }
    *returnSize = r;
    return ans;
}
```

#### [567. 字符串的排列](https://leetcode-cn.com/problems/permutation-in-string/)

```c
//方法：用双指针，统计s2两个指针中间的字符串各字符出现的次数是否等于s1中各字符的出现次数，且长度恰好等于s1的长度。
//另外可以用给定固定长度，判断字符出现次数是否满足要求。
bool checkInclusion(char *s1, char *s2)
{
    int len1 = 0;
    int cnt[26] = {0};
    while (*s1)  //统计s1字符串各字符出现的次数和字符串长度
        cnt[*s1 - 'a']++, s1++, len1++;

    int win = 0;
    char *left = s2, *right = s2;
    while (*right) {
        int i = *right - 'a';
        cnt[i]--, win++, right++;  //右指针向右移动，耗费一个字符c，长度加一
        while (cnt[i] < 0)         //耗费c的字符数多于s1中的c字符的出现次数，左指针右移，直到将超出耗费的字符c补回。
            cnt[*left - 'a']++, left++, win--;
        if (win == len1)
            return true;
    }
    return false;
}
```

#### [629. K个逆序对数组](https://leetcode-cn.com/problems/k-inverse-pairs-array/)

```c++
//dp[i][j]存储的是前i个数字组成的数组，其逆序对为j的个数。则dp[i][j]=sum(dp[i-1][j-window+1:j]);其中window=i;表示窗口长度，因为数字i可以产生的新逆序对的范围为0到i-1;对应依次从右边逐步插入到左边。
class Solution {
    const int mod = 1e9 + 7;
public:
    int kInversePairs(int n, int k) {
        if (k == 0)
            return 1;
        vector<vector<int>> dp(2, vector<int>(k + 1, 0));
        dp[1][0] = 1;
        int row, preRow = 1;
        for (int i = 2; i <= n; ++i) {
            row = i & 1;
            int window = i;
            int window_sum = 0;
            for (int j = 0; j <= k; ++j) {
                window_sum += dp[preRow][j];
                if (j >= window) {
                    window_sum -= dp[preRow][j - window];
                }
                window_sum = window_sum >= 0 ? window_sum % mod : window_sum + mod;
                dp[row][j] = window_sum;
            }
            preRow = row;
        }
        return dp[row][k];
    }
};
```



#### [643. 子数组最大平均数 I](https://leetcode-cn.com/problems/maximum-average-subarray-i/)

```c
//因为长度确定，平均值最大，也即和最大,
double findMaxAverage(int* nums, int numsSize, int k)
{
    int sum = 0, i;
    for (i = 0; i < k; ++i) {
        sum += nums[i];
    }
    int j = 0, maxSum = sum;
    while (i < numsSize) {
        int x = nums[i++] - nums[j++]; //和变化的值
        if (x > 0 && x + sum > maxSum) { //最大和出现的情况
            maxSum = x + sum;
        }
        sum += x; //更新和
    }
    return (double)maxSum / k;
}
```

#### [665. 非递减数列](https://leetcode-cn.com/problems/non-decreasing-array/)

```c
//方法：每轮比较相连的三个数，nums[i-1],nums[i],nums[i+1]；
//1.如果两端满足要求（nums[i-1]<=nums[i+1]），如果中间的数不满足要求，修改中间的数；
//2.如果两端不满足要求，前两个数满足要求，修改最后一个数；
//3.如果后两个数满足要求，修改第一个数（该情况只可能出现在数组最前面。数组前面放一个最小的数，则变为第一种情况）；
//4.其他情况则至少修改两个数。一步一步移动，则该情况不会出现。
#define MIN -100000
bool checkPossibility(int *nums, int numsSize)
{
    int pre = MIN, k = 0;
    for (int i = 0; i < numsSize - 1; ++i){
        if (pre <= nums[i + 1]){
            if (nums[i] < pre || nums[i] > nums[i + 1]) //中间的数不满足要求
                k++, nums[i] = pre;
        }else if (nums[i] >= pre)//前两个数满足要求
            k++, nums[i + 1] = nums[i];
        else   //其他情况不会出现
            return false;
        if (k == 2)
            return false;
        pre = nums[i];
    }
    return true;
}
//leetcode上的方法，当不满足非递减要求时，可以：1）将nums[i]修改为nums[i+1]，或2）将nums[i+1]修改为nums[i]；
//情况1，降低前面的值（i==0），用掉一次修改机会，继续看后边是否满足；
//情况2，提升后面的值（i>0），还需要看nums[i+2]和nums[i]的关系，如果提升后的值大于随后的值，则不满足要求
bool checkPossibility(int* nums, int numsSize) {
    int cnt = 0;
    for (int i = 0; i < numsSize - 1; ++i) {
        int x = nums[i], y = nums[i + 1];
        if (x > y) {
            cnt++;
            if (cnt > 1) {
                return false;
            }
            if (i > 0 && y < nums[i - 1]) {
                nums[i + 1] = x;
            }
        }
    }
    return true;
}
```

#### [697. 数组的度](https://leetcode-cn.com/problems/degree-of-an-array/)

```c
//需要一个哈希表来存储各元素出现的次数，要求该元素出现次数最多且长度最小的子串，则该子串两边恰好为该元素，所以可以再加两个哈希表，用来存储元素的起始下标和终止下标。
#define M 50000
int findShortestSubArray(int *nums, int numsSize){
    int cnt[M], startIndex[M], endIndex[M];
    for (int i = 0; i < M; ++i)
        startIndex[i] = -1;
    memset(cnt, 0, sizeof(int) * M);
    int maxCnt = 0, minLen = M;
    for (int i = 0; i < numsSize; ++i){
        if (startIndex[nums[i]] == -1)
            startIndex[nums[i]] = i;
        endIndex[nums[i]] = i;
        cnt[nums[i]]++;
        int len = endIndex[nums[i]] - startIndex[nums[i]] + 1;
        if (cnt[nums[i]] > maxCnt || (cnt[nums[i]] == maxCnt && minLen > len)){
            minLen = len;
            maxCnt = cnt[nums[i]];
        }
    }
    return minLen;
}
```

#### [703. 数据流中的第 K 大元素](https://leetcode-cn.com/problems/kth-largest-element-in-a-stream/)

```c
//方法：使用一个最大堆和最小堆，大的数放在最小堆中，小的数放在最大堆里。
//大堆没有必要，因为构建好小堆后，如果新加的数大于堆顶，则将堆顶元素和替换为新元素，并调整。否则堆无需变化。
#define MAX 10001
typedef struct{
    int minHeap[MAX], maxHeap[MAX];
    int minSize, maxSize, k;
} KthLargest;
int less(int a, int b) { return a < b; }
int greater(int a, int b) { return a > b; }
void heapAdd(int *heap, int *size, int val, int (*cmp)(int, int)){//从堆末尾增加元素，并调整。
    int son = ++*size;
    while (son / 2 > 0 && cmp(val, heap[son / 2]))
        heap[son] = heap[son / 2], son /= 2;
    heap[son] = val;
}
void heapReplace(int *heap, int size, int *val, int (*cmp)(int, int)){ //出现较大的数，替换最小堆里最小的数
    int k = heap[1];
    int son = 2;
    while (son <= size){
        if (son + 1 <= size && cmp(heap[son + 1], heap[son]))
            son += 1;
        if (cmp(heap[son], *val))
            heap[son / 2] = heap[son];
        else
            break;
        son *= 2;
    }
    heap[son / 2] = *val;
    *val = k;
}
KthLargest *kthLargestCreate(int k, int *nums, int numsSize){
    KthLargest *heap = (KthLargest *)malloc(sizeof(KthLargest));
    heap->minSize = 0, heap->maxSize = 0, heap->k = k;
    int i;
    for (i = 0; i < numsSize && i < k; ++i)//构建小堆
        heapAdd(heap->minHeap, &heap->minSize, nums[i], less);
    for (i; i < numsSize; ++i){//调整两个堆
        if (nums[i] > heap->minHeap[1])
            heapReplace(heap->minHeap, heap->minSize, &nums[i], less);
        heapAdd(heap->maxHeap, &heap->maxSize, nums[i], greater);
    }
    return heap;
}
int kthLargestAdd(KthLargest *obj, int val){
    if (obj->k > obj->minSize) //可能最开始通过的元素个数小于k。
        heapAdd(obj->minHeap, &obj->minSize, val, less);
    else{
        if (obj->minHeap[1] < val)
            heapReplace(obj->minHeap, obj->minSize, &val, less);
        heapAdd(obj->maxHeap, &obj->maxSize, val, greater);
    }
    return obj->minHeap[1];
}
void kthLargestFree(KthLargest *obj){
    free(obj);
}
```

#### [724. 寻找数组的中心索引](https://leetcode-cn.com/problems/find-pivot-index/)

```c
//方法：总的和减去右边的和==左边的和。
int pivotIndex(int *nums, int numsSize)
{
    int sum = 0, leftSum = 0;
    for (int i = 0; i < numsSize; ++i)
        sum += nums[i];
    for (int i = 0; i < numsSize; ++i)
    {
        sum -= nums[i];
        if (leftSum == sum)
            return i;
        leftSum += nums[i];
    }
    return -1;
}
//失败案例，
int pivotIndex(int *nums, int numsSize)
{
    int *rsum = (int *)malloc(sizeof(int) * (numsSize + 1));
    int *lsum = (int *)malloc(sizeof(int) * (numsSize + 1));
    rsum[numsSize] = lsum[0] = 0;
    for (int i = 0; i < numsSize; ++i)  //从左往右求和，i左边的和
        lsum[i + 1] = lsum[i] + nums[i];
    for (int i = numsSize - 1; i >= 0; --i) //从右往左求和，i右边的和
        rsum[i] = rsum[i + 1] + nums[i];
    for (int i = 0; i < numsSize; ++i){
        if (lsum[i] == rsum[i + 1]) {
            free(rsum);
            free(lsum);
            return i;
        }
    }
    free(rsum);
    free(lsum);
    return -1;
}
```

#### [730. 统计不同回文子序列](https://leetcode-cn.com/problems/count-different-palindromic-subsequences/)

```c++
//回文串加子串，dp[i][j]存储i到j的回文子序列最大个数。在已知dp[i][j]中间的值后，我们可以根据s[i]的s[j]的关系，与i-j中间s[i]重复的个数推导出dp[i][j]的值
class Solution {
    const int mod = 1e9 + 7;
public:
    int countPalindromicSubsequences(string S) {
        int n = S.size();
        vector<vector<int>> dp(n, vector<int>(n, 0));
        for (int i = n - 1; i >= 0; --i) {
            dp[i][i] = 1;
            vector<int> cnt(4, 0);
            int id = S[i] - 'a';
            for (int j = i + 1; j < n; ++j) {
                if (S[i] == S[j]) {
                    if (cnt[id] == 0) {
                        dp[i][j] = 2 * dp[i + 1][j - 1] + 2;
                    } else if (cnt[id] == 1) {
                        dp[i][j] = 2 * dp[i + 1][j - 1] + 1;
                    } else {
                        int x = i + 1, y = j - 1;
                        while (S[x] != S[i])
                            x++;
                        while (S[y] != S[i])
                            y--;
                        dp[i][j] = 2 * dp[i + 1][j - 1] - dp[x + 1][y - 1];
                    }
                } else {
                    dp[i][j] = dp[i][j - 1] - dp[i + 1][j - 1] + dp[i + 1][j];
                }
                dp[i][j] = (dp[i][j] >= 0) ? dp[i][j] % mod : dp[i][j] + mod;
                //cout << dp[i][j] << ",";
                cnt[S[j] - 'a']++;
            }
        }
        return dp[0][n - 1];
    }
};
```



#### [765. 情侣牵手](https://leetcode-cn.com/problems/couples-holding-hands/)

```c
//方法：所有情侣牵手成功，则必须要求在偶数位i与下一位奇数位i+1坐的是一对情侣。这样的位子对有rowsize/2对，如果某对位子上坐的不是一对情侣，只需交互其中一个即可。
//还可以使用并查集，连通分量
int minSwapsCouples(int *row, int rowSize){
    int index[rowSize];
    for (int i = 0; i < rowSize; ++i)
        index[row[i]] = i;
    int cnt = 0;
    for (int i = 0; i < rowSize; i = i + 2){//下一对位子
        if (abs(row[i] - row[i + 1]) != 1 || (row[i] + row[i + 1]) % 4 != 1){ //一对位子上坐的不是一对情侣
            if (row[i] % 2){   //为靠左边的人找到对应的情侣，将右边的人替换到左边情侣的位子上去，修改右边人的位子下标
                row[index[row[i] - 1]] = row[i + 1];
                index[row[i + 1]] = index[row[i] - 1];
            }else{   //同上，只是左边人的情侣取决于左边人的奇偶性；可以用异或运算
                row[index[row[i] + 1]] = row[i + 1];
                index[row[i + 1]] = index[row[i] + 1];
            }
            //row[index[row[i]^1]]=row[i+1];  
            //index[row[i+1]]=index[row[i]^1];
            cnt++;
        }
    }
    return cnt;
}
```

#### [766. 托普利茨矩阵](https://leetcode-cn.com/problems/toeplitz-matrix/)

```c
//方法：依次比较相邻两行（前一行0到n-1，后一行1到n）的元素即可。
bool isToeplitzMatrix(int **matrix, int matrixSize, int *matrixColSize){
    for (int i = 1; i < matrixSize; ++i){
        for (int j = 1; j < matrixColSize[i]; ++j){
            if (matrix[i][j] - matrix[i - 1][j - 1])
                return false;
        }
    }
    return true;
}
```

#### [832. 翻转图像](https://leetcode-cn.com/problems/flipping-an-image/)

```c
//也可以直接在原数组上修改。
int **flipAndInvertImage(int **A, int ASize, int *AColSize, int *returnSize, int **returnColumnSizes){
    *returnSize = ASize;
    int **array = (int **)malloc(sizeof(int *) * ASize);     //指针构成的数组
    *returnColumnSizes = (int *)malloc(sizeof(int) * ASize); //指向数组的指针
    for (int i = 0; i < ASize; ++i){
        (*returnColumnSizes)[i] = AColSize[i];                   //*returnColumnSizes获取其地址，
        *(array + i) = (int *)malloc(sizeof(int) * AColSize[i]); //修改指针数组里的值
        for (int j = 0; j < AColSize[i]; ++j)
            array[i][j] = A[i][AColSize[i] - j - 1] ^ 1;
    }
    return array;
}
```

#### [862. 和至少为 K 的最短子数组](https://leetcode-cn.com/problems/shortest-subarray-with-sum-at-least-k/)

```c++
//找规律，先记录前序和，作为左边界，如果某个位置x1的前序和大于后面位置x2的前序和，x1可能成为左边界的话，则x2为更小的左边界。所以应该存储递增左边界。
//左右边界满足要求时，左边界可能不是最大值，无法使长度更小；则尝试右移左边界
class Solution {
public:
    int shortestSubarray(vector<int>& A, int K)
    {
        int n = A.size();
        vector<int> sum(n + 1);
        for (int i = 0; i < n; i++) {
            sum[i + 1] = sum[i] + A[i];
        }
        int minLen = n + 1, right = 0;
        deque<int> que;
        while (right <= n) {
            while (!que.empty() && sum[right] <= sum[que.back()])//相比当前值作为左边界，不可能成为左边界的值。
                que.pop_back();
            while (!que.empty() && sum[right] - sum[que.front()] >= K) {//找更靠右的左边界
                minLen = fmin(minLen, right - que.front());
                que.pop_front();
            }
            que.push_back(right);
            right++;
        }
        return minLen > n ? -1 : minLen;
    }
};
```



#### [867. 转置矩阵](https://leetcode-cn.com/problems/transpose-matrix/)

```c
//和832. 翻转图像一样
int **transpose(int **matrix, int matrixSize, int *matrixColSize, int *returnSize, int **returnColumnSizes){
    *returnSize = matrixColSize[0];
    *returnColumnSizes = (int *)malloc(sizeof(int) * matrixColSize[0]);
    int **array = (int **)malloc(sizeof(int *) * matrixColSize[0]);
    for (int i = 0; i < matrixColSize[0]; ++i){
        (*returnColumnSizes)[i] = matrixSize;
        array[i] = (int *)malloc(sizeof(int) * matrixSize);
        for (int j = 0; j < matrixSize; ++j)
            array[i][j] = matrix[j][i];
    }
    return array;
}
```

#### [888. 公平的糖果棒交换](https://leetcode-cn.com/problems/fair-candy-swap/)

```c
//方法：是否存在两者总和之差==两个元素之差的2倍；其他方法可以以空间换时间，遍历A时，查找B中是否存在abs(Asum-Bsum)/2-A[i]的值
int* fairCandySwap(int* A, int ASize, int* B, int BSize, int* returnSize)
{
    int ASum = 0, BSum = 0;
    for (int i = 0; i < ASize; ++i)
        ASum += A[i];
    for (int i = 0; i < BSize; ++i)
        BSum += B[i];

    int k = ASum - BSum;
    int* ans = (int*)malloc(sizeof(int) * 2);
    for (int i = 0; i < ASize; ++i) {
        for (int j = 0; j < BSize; ++j) {
            if (2 * (A[i] - B[j]) == k) {
                ans[0] = A[i], ans[1] = B[j];
                *returnSize = 2;
                return ans;
            }
        }
    }
    return ans;
}
```

#### [906. 超级回文数](https://leetcode-cn.com/problems/super-palindromes/)

```c++
//有规律，和乘积过程中不会产生进位。
typedef long long ll;
template <class T1, class T2> T1 convert(T2 s) {
    stringstream io;
    io << s;
    T1 out;
    io >> out;
    return out;
}
class Solution {
    ll right_num, left_num;
    string next_string(string &s) {
        int n = s.size();
        if (n == 1 && s != "9") {
            int x = convert<int>(s);
            return convert<string>(x + 1);
        }
        if (s == "9")
            return string("11");
        int m = (n + 1) / 2;
        string left_str = s.substr(0, m);
        int i = m;
        while (i && left_str[i - 1] == '9') {
            left_str[--i] = '0';
        }
        if (i)
            left_str[i - 1] += 1;
        else
            left_str.insert(0, 1, '1');
        string rev_str = left_str.substr(0, n / 2);
        reverse(rev_str.begin(), rev_str.end());
        return left_str + rev_str;
    }
    bool ispali(const string &s) {
        string r_str=s;
        reverse(r_str.begin(), r_str.end());
        return s == r_str;
    }
    bool ispowpali(ll num) {
        ll x = num * num;
        if (x <= right_num && x >= left_num) {
            string s = convert<string>(x);
            return ispali(s);
        }
        return false;
    }

public:
    int superpalindromesInRange(string left, string right) {
        right_num = convert<ll>(right);
        left_num = convert<ll>(left);
        ll sqrt_left = sqrt(left_num);
        left = convert<string>(sqrt_left);

        int n = left.size();
        int m = n / 2;
        if (n > 1) {
            string l_str = left.substr(0, m);
            string r_str = left.substr(n - m, m);
            reverse(l_str.begin(), l_str.end());
            ll l_num = convert<ll>(l_str);
            if (l_num <= convert<ll>(r_str))
                left = next_string(left);
            else
                left = left.substr(0, (n + 1) / 2) + l_str;
        }
        int cnt = 0;
        sqrt_left = convert<ll>(left);
        while (sqrt_left * sqrt_left <= right_num) {
            if (ispowpali(sqrt_left))
                cnt++, cout << sqrt_left << "," << sqrt_left * sqrt_left << ";";
            left = next_string(left);
            sqrt_left = convert<ll>(left);
        }
        return cnt;
    }
};
```



#### [907. 子数组的最小值之和](https://leetcode-cn.com/problems/sum-of-subarray-minimums/)

```c
//对每个子串找最小值，时间复杂度O(n^2),超时。依次获取每个字串和其最小值。
//leetcode方法：找出当前元素作为最小值的左边界（最小值不唯一）和右边界（唯一最小值）。该区间以当前元素为最小值的子串个数为(i-prev[i])*(next[i]-i)。
#define MOD 1000000007
int sumSubarrayMins(int *arr, int arrSize){
    int prev[arrSize], next[arrSize];
    int minQue[arrSize], right = 0;//存储当前位置之前的最小值和前一位置的元素（下标）
    for (int i = 0; i < arrSize; ++i){ //小于当前元素的左边界
        while (right > 0 && arr[i] <= arr[minQue[right - 1]]) 
            right--;
        if (right == 0)
            prev[i] = -1;
        else
            prev[i] = minQue[right - 1];
        minQue[right++] = i;
    }
    right = 0;
    for (int i = arrSize - 1; i >= 0; --i){//小于等于当前元素的左边界
        while (right > 0 && arr[i] < arr[minQue[right - 1]])
            right--;
        if (right == 0)
            next[i] = arrSize;
        else
            next[i] = minQue[right - 1];
        minQue[right++] = i;
    }
    int sum = 0;
    for (int i = 0; i < arrSize; ++i){
        sum += (long)arr[i] * (i - prev[i]) * (next[i] - i) % MOD;
        sum %= MOD;
    }
    return sum;
}
//维护递增栈，
//新加一个元素j，左边界i依次往左运动，则产生了新的子串，对于不影响新子串中最小值的，其和不变（=之前统计的和-最小值改变了的部分的和），如果新加值为新串的最小值，需要统计其作为最小值的新子串的个数。
```

#### [940. 不同的子序列 II](https://leetcode-cn.com/problems/distinct-subsequences-ii/)

```c++
//aaaa; "" 1; "" a 2; "" a (a) aa 3-1; "" a aa (a) (aa) aaa 5-2; "" a aa aaa (a) (aa) (aaa) aaaa  8-3; 
//              a 1;    a aa (a) 3-1;    a aa (aa) aaa (a) 5-2;    a aa aaa (aa) (aaa) aaaa (a) 7-3; 
//lee; "" 1; "" l 2; "" l e le 4; "" l e le (e) (le) ee lee 7-2;
//              l 1;    l le e 3;    l (le) (e) le lee ee e 7-2;

//每次新加一个字符，总个数变为2*n,重复的个数为上一次添加该元素前一位置的个数；
class Solution {
    const int mod = 1e9 + 7;
public:
    int distinctSubseqII(string S) {
        int n = S.size();
        vector<int> dp(n+1), last(26, -1);
        dp[0] = 1;
        for (int i = 0; i < n; ++i) {
            int id = S[i] - 'a';
            dp[i+1] = dp[i] * 2 ;
            if (last[id] >= 0)
                dp[i+1] = dp[i+1] - dp[last[id]];
            dp[i+1] = dp[i+1] >= 0 ? dp[i+1] % mod : dp[i+1] + mod;
            last[id] = i;
            //cout << dp[i+1] << ";";
        }
        dp[n]--;
        if(dp[n]<0)dp[n]+=mod;
        return dp[n];
    }
};
```



#### [978. 最长湍流子数组](https://leetcode-cn.com/problems/longest-turbulent-subarray/)

```c
//方法：判断arr[i]和arr[i-1]的大小连续反转的次数，计数终止情况：1.当出现等于时，需要向后移动直到出现不等于；2.反转未出现时。
//其他方法用双指针和动态规划。
int maxTurbulenceSize(int *arr, int arrSize)
{
    if (arrSize < 2)
        return arrSize;
    int cnt = 1, i = 1, maxCnt = 1;
    while (i < arrSize){
        while (i < arrSize && arr[i] == arr[i - 1])  //找到不等于
            ++i;
        if (i == arrSize)
            break;
        bool pre = arr[i] > arr[i - 1]; //前一个大小比较
        cnt = 2, i++;
        while (i < arrSize){
            if (arr[i] == arr[i - 1])  //出现等于，终止
                break;
            bool cur = arr[i] > arr[i - 1];  //后一个大小比较
            if ((pre || cur) && !(pre && cur)){//异或
                i++, pre = cur, cnt++;
            }
            else
                break;
        }
        if (cnt > maxCnt)
            maxCnt = cnt;
    }
    return maxCnt;
}
```

#### [992. K 个不同整数的子数组](https://leetcode-cn.com/problems/subarrays-with-k-different-integers/)

```c
//方法：统计窗口里各数字出现的次数cnt[A[i]]，不同数字的个数num，如果num==k（条件，出现一个新的数）,则找到一个合适窗口，然后从左往右缩小窗口，看看还有多少窗口满足num==k（终止条件为有一个数的出现次数变为0），只考虑包含新加入数字在内的子窗口。
int currentWindow(int *A, int *cnt, int left, int right) //当前窗口满足K==num,从左往右缩小窗口，有多少个窗口满足。
{
    int ans = 0;
    int i = left;
    while (i < right){
        if (--cnt[A[i++]])
            ans++;
        else
            break;
    }
    for (int j = left; j < i; ++j) //复原出现频率。
        cnt[A[j]]++;
    return ans;
}
int subarraysWithKDistinct(int *A, int ASize, int K)
{
    int cnt[ASize + 1];
    memset(cnt, 0, sizeof(int) * (ASize + 1));
    int right = 0, left = 0, num = 0, ans = 0;
    while (right < ASize){
        if (cnt[A[right]] == 0)
            num++;
        cnt[A[right]]++;
        if (num == K){  //满足要求的新窗口，
            ans++;
            ans += currentWindow(A, cnt, left, right);//包含最右端数的子窗口满足要求的个数。
        } else if (num > K) {  //新窗口不满足要求，
            while (left < right && --cnt[A[left++]]); //删掉一个数，使其出现次数为0
            ans++, num--;
            ans += currentWindow(A, cnt, left, right); //新满足的窗口
        }
        right++;
    }
    return ans;
}
//双指针：
//关系：给定一个窗口，我们可以先求当前窗口最多包含k个不同数的子窗口个数（=包含1到k个不同数的子窗口数之和），减去最多包含k-1个不同数的子窗口的个数，即得包含k个不同数的子窗口数。
//统计新加一个数，会导致多少个新子窗口出现？，答案是L+1,L为之前窗口的大小，从右往左依次选不同长度0-L的子窗口加上新加入的数构成新的子窗口。
//新加一个数，如果不同数的个数小于k，统计新的子窗口个数；
//如果不同个数大于K,则应该缩小之前窗口，使其不同数个数变为k-1，即将左指针右移，直到有一个数的统计次数变为0；
```

#### [995. K 连续位的最小翻转次数](https://leetcode-cn.com/problems/minimum-number-of-k-consecutive-bit-flips/)

```c
//方法：1.一个字串翻转两次，相当于没有翻转；2.各子串的翻转顺序对结果没有影响。遇到0就翻转接下来的K个数，则时间复杂度O(NK),超时。
int minKBitFlips(int *A, int ASize, int K){
    int cnt = 0;
    for (int i = 0; i < ASize; ++i){
        if (A[i] == 0){
            if (i + K <= ASize){
                for (int j = 0; j < K; ++j)
                    A[i + j] ^= 1;
                cnt++;
            }else
                return -1;
        }
    }
    return cnt;
}
//统计每个元素翻转的次数，
class Solution {
public:
    int minKBitFlips(vector<int> &A, int K){
        int revCnt = 0, ans = 0;
        int n = A.size();
        vector<int> diff(n + 1, 0);
        for (int i = 0; i < n; ++i){
            revCnt += diff[i];  //得到当前的位置翻转的次数
            if ((revCnt & 1) == A[i]){ //优先级
                if (i + K > n)
                    return -1;
                diff[i + K]--; //连续翻转k个，只影响第k和k+1处的翻转差。
                revCnt++;
                ans++;
            }
        }
        return ans;
    }
};
```

#### [1004. 最大连续1的个数 III](https://leetcode-cn.com/problems/max-consecutive-ones-iii/)

```c
//方法：统计窗口内0出现的次数，如次数大于k，则左右边界一起移动，否则，只移动右边界。
//leetcode使用求和后的差得到窗口间0的个数。
int longestOnes(int *A, int ASize, int K){
    int cnt[2] = {0, 0};
    int right = 0, left = 0, maxLen = 0;
    while (right < ASize){
        cnt[A[right++]]++;
        if (cnt[0] > K)
            cnt[A[left++]]--;
    }
    return right - left;
}
```

#### [1044. 最长重复子串](https://leetcode-cn.com/problems/longest-duplicate-substring/)

```c++
//字符串哈希，快速查找
const long long mod = ((long long)1 << 55) + 1; //小了会冲突
const int base = 26;
class Solution {
    //快速将长度为N的字符串转为整型。
    int searchN(vector<int> &nums, string &s, int N, int n) {
        long long key = 0, pow = 1;
        // unordered_map<int,unordered_set<string>> hash;
        unordered_set<long> hash;
        for (int i = 0; i < N; ++i) {
            key = (key * base + nums[i]) % mod;
            pow = (pow * base) % mod;
        }
        // hash[key].insert(s.substr(0,N));
        hash.insert(key);
        for (int i = 1; i <= n - N; ++i) {
            key = (key * base - (nums[i - 1] * pow) % mod + mod) % mod;
            key = (key + nums[i + N - 1]) % mod;
            // if (hash.count(key)&&hash[key].count(s.substr(i,N)))
            if (hash.count(key))
                return i;
            // hash[key].insert(s.substr(i,N));
            hash.insert(key);
        }
        return -1;
    }
public:
    string longestDupSubstring(string s) {
        cout << mod << endl;
        int n = s.size();
        int left = 1, right = n - 1;
        vector<int> arr(n);
        for (int i = 0; i < n; ++i)
            arr[i] = s[i] - 'a';
        string ans;
        //使用二分查找
        while (left <= right) {
            int mid = (left + right) / 2;
            int start = searchN(arr, s, mid, n);
            if (start == -1)
                right = mid - 1;
            else {
                cout << start;
                ans = s.substr(start, mid);
                left = mid + 1;
            }
        }
        return ans;
    }
};
```

#### [1047. 删除字符串中的所有相邻重复项](https://leetcode-cn.com/problems/remove-all-adjacent-duplicates-in-string/)

```c++
//string提供了类似栈的操作。栈，将stack用string替代
class Solution{
    string dfs(stack<char> &st){
        if (st.empty())
            return "";
        char c = st.top();
        st.pop();
        return dfs(st) + c;
    }

public:
    string removeDuplicates(string S){
        stack<char> st;
        for (int i = 0; i < S.size(); ++i){
            if (st.size() && st.top() == S[i])
                st.pop();
            else
                st.push(S[i]);
        }
        return dfs(st);
    }
};
```

#### [1052. 爱生气的书店老板](https://leetcode-cn.com/problems/grumpy-bookstore-owner/)

```c
//方法，记录没有使用技巧时的客户满意数，和使用技巧获得的最大增值数。
int maxSatisfied(int *customers, int customersSize, int *grumpy, int grumpySize, int X){
    int increase = 0, sum = 0, maxIncrease = 0;
    for (int i = 0; i < customersSize; ++i){
        if (grumpy[i])   //右边界使用技巧
            increase += customers[i];
        else
            sum += customers[i]; //不使用技巧的满意数
        if (i >= X && grumpy[i - X] == 1)  //左边界移除技巧
            increase -= customers[i - X];
        maxIncrease = fmax(increase, maxIncrease);
        //printf("i=%d,sum=%d,inc=%d,maxInc=%d\n", i, sum, increase, maxIncrease);
    }
    return sum + maxIncrease;
}
```

#### [1074. 元素和为目标值的子矩阵数量](https://leetcode-cn.com/problems/number-of-submatrices-that-sum-to-target/)

```c++
//行和列都多申请一行，sum[i][j]表示i-1,j-1的前缀和，后面处理区间时，可以不用讨论边界
class Solution {
public:
    int numSubmatrixSumTarget(vector<vector<int>> &matrix, int target) {
        int n = matrix.size(), m = matrix[0].size();
        vector<vector<int>> sum(n + 1, vector<int>(m + 1, 0));
        for (int i = 0; i < n; ++i) {  //求前缀和，
            int lineSum = 0;
            for (int j = 0; j < m; ++j) {
                lineSum += matrix[i][j];
                sum[i + 1][j + 1] = lineSum + sum[i][j + 1];
            }
        }
        int ans = 0;
        for (int i = 0; i < n; ++i) {
            for (int j = i + 1; j <= n; ++j) {
                //存储i到j行 0-k列的和，后面某个值减去哈希表里的（也可以不减，相当于表初始一个0，1），即得后面子数组的和，
                unordered_map<int, int> cnt{{0, 1}}; 
                for (int k = 1; k <= m; ++k) {
                    int x = sum[j][k] - sum[i][k];
                    int y = x - target;
                    if (cnt.count(y) != 0) {
                        ans += cnt[y];
                    }
                    cnt[x]++;
                }
            }
        }
        return ans;
    }
};
```



#### [1143. 最长公共子序列](https://leetcode-cn.com/problems/longest-common-subsequence/)

```c++
//使用动态规划来记录s1的i位置和s2的j位置，的结果，如果当前相等，则长度+1，否则，遍历完某个子串，取其最大值
class Solution {
public:
    int longestCommonSubsequence(string text1, string text2) {
        int n = text1.size(), m = text2.size();
        vector<vector<int>> dp(n + 1, vector<int>(m + 1, 0));
        for (int i = 0; i < n; ++i) {
            for (int j = 0; j < m; ++j) {
                if (text1[i] == text2[j]) {
                    dp[i + 1][j + 1] = fmax(dp[i + 1][j + 1], dp[i][j] + 1);
                } else {
                    dp[i + 1][j + 1] = fmax(dp[i + 1][j + 1],
                                            fmax(dp[i][j + 1], dp[i + 1][j]));
                }
            }
        }
        return dp[n][m];
    }
};
```

#### [1172. 餐盘栈](https://leetcode-cn.com/problems/dinner-plate-stacks/)

```c++
class DinnerPlates {
    int cap;
    int not_full_left, have_right;
    vector<vector<int>> plates;
    vector<int>cnt;
    void right_have_num() {//查找最靠右有元素的stack下标
        while (have_right >= 0 && cnt[have_right] == 0) {
            have_right--;
        }
    }

public:
    DinnerPlates(int capacity)
        : cap(capacity), not_full_left(0), have_right(-1) {
        plates.emplace_back(vector<int>(capacity,0));
        cnt.push_back(0);
    }

    void push(int val) {
        plates[not_full_left][cnt[not_full_left]++]=val;
        if (have_right < not_full_left)
            have_right = not_full_left;
        while (not_full_left < plates.size() && cnt[not_full_left] == cap) //最左边元素未满的stack下标
            not_full_left++;
        if (not_full_left == plates.size()){
            plates.emplace_back(vector<int>(cap,0));
            cnt.push_back(0);
        }
    }

    int pop() {
        if (have_right < 0)
            return -1;
        int x = plates[have_right][--cnt[have_right]];
        right_have_num();
        return x;
    }

    int popAtStack(int index) {
        if (index >= plates.size() || cnt[index]==0)
            return -1;
        int x = plates[index][--cnt[index]];
        if (not_full_left > index)//左边产生新的未满的stack
            not_full_left = index;
        if (cnt[index] == 0 && have_right == index) //右边产生新的空的stack
            right_have_num();
        return x;
    }
};
```



#### [1178. 猜字谜](https://leetcode-cn.com/problems/number-of-valid-words-for-each-puzzle/)

```c
//超时，对于每一个字谜，都遍历所有字。统计好所有字所包含的字符。然后每个字谜，只需进行查找。
#define M 7
#define S 26
int* findNumOfValidWords(char ** words, int wordsSize, char ** puzzles, int puzzlesSize, int* returnSize){
    int *ans=(int*)malloc(sizeof(int)*puzzlesSize);
    *returnSize=puzzlesSize;
    int cnt[wordsSize][S+1];
    memset(cnt,0,sizeof(cnt));
    for(int i=0;i<wordsSize;++i){
        char *p=words[i];
        int m=0;
        while(*p){
            if(cnt[i][*p-'a']==0)cnt[i][*p-'a']=1,m++;
            p++;
        }
        cnt[i][S]=m;
    }
    for(int i=0;i<puzzlesSize;++i){
        int n=0,pCnt[S]={0};
        for(int j=0;j<M;++j)pCnt[puzzles[i][j]-'a']=j+1;//统计字谜的字符
        for(int j=0;j<wordsSize;++j){
            if(cnt[j][S]>7)continue;
            int k,firstChar=0;
            for(k=0;k<S;++k){ //字是否可以作为谜底
                if(cnt[j][k]){
                    if(pCnt[k]==0)break;
                    else if(pCnt[k]==1)firstChar=1;
                }
            }
            if(k==S&&firstChar)n++;
        }
        ans[i]=n;
    }
    return ans;
}
//将字符串转化为数值，用来存储字符串包含的字符 结构
class Solution {
public:
    vector<int> findNumOfValidWords(vector<string>& words, vector<string>& puzzles) {
        unordered_map<int, int> cnt;
        for (auto w : words){
            int mask = 0;
            for (auto c : w)
                mask |= (1 << (c - 'a'));
            if (__builtin_popcount(mask) <= 7)
                cnt[mask]++;
        }
        vector<int> ans;
        for (auto p : puzzles){
            int k = 0;
            /*//求子集第一中方法
            for (int i = 0; i < (1 << 6); ++i){
                int mask = 0;
                for (int j = 0; j < 6; ++j){
                    if (i & (1 << j))
                        mask |= (1 << (p[j + 1] - 'a'));
                }
                mask |= (1 << (p[0] - 'a'));
                if (cnt.count(mask))
                    k += cnt[mask];
            }*/
            int mask = 0;
            for (int i = 1; i < 7; ++i)
                mask |= (1 << (p[i] - 'a'));
            int subset = mask;
            do{
                int s = subset | (1 << (p[0] - 'a'));
                if (cnt.count(s))
                    k += cnt[s];
                subset = (subset - 1) & mask;
            } while (subset != mask); //会递减到0，然后两者相等。
            ans.push_back(k); 
        }
        return ans;
    }
};
//或者将字符结构按字典数排序，作为哈希表的key
```

#### [1208. 尽可能使字符串相等](https://leetcode-cn.com/problems/get-equal-substrings-within-budget/)

```c
//方法：利用双指针，当差值小于剩余的maxCost后，右指针右移；大于，左指针右移，窗口只会越来越大，添加和删除元素后的窗口如果不满足要求，左右指针都会右移。
//类似424.替换后的最长重复字符
int equalSubstring(char* s, char* t, int maxCost)
{
    int left = 0, right = 0;
    while (*(s + right)) {
        maxCost -= abs(*(s + right) - *(t + right)); //减去新加入字符的消耗
        if (maxCost < 0) {
            maxCost += abs(*(s + left) - *(t + left));//去掉最左边的消耗，左指针右移
            left++;
        }
        right++;
    }
    return right - left;
}
```

#### [1423. 可获得的最大点数](https://leetcode-cn.com/problems/maximum-points-you-can-obtain-from-cards/)

```c
//先求靠前的k个值和，然后去掉最左边的元素，依次加入尾部的数，直到前面靠前的k个全部去掉。
//两边k个元素的和=总和-中间窗口的和
int maxScore(int *cardPoints, int cardPointsSize, int k)
{
    int sum = 0, i;
    for (i = 0; i < cardPointsSize && i < k; ++i)
        sum += cardPoints[i];
    if (k == cardPointsSize)
        return sum;
    int left = i - 1, right = cardPointsSize - 1, maxSum = sum;
    while (i > 0){
        sum -= cardPoints[--i];
        sum += cardPoints[right--];
        if (sum > maxSum)
            maxSum = sum;
    }
    return maxSum;
}
```

#### [1458. 两个子序列的最大点积](https://leetcode-cn.com/problems/max-dot-product-of-two-subsequences/)

```c++
//动态规划，dp[i][j]表示两数组前i,j个元素的最大点积。
class Solution {
    const int inf = -1e6;

public:
    int maxDotProduct(vector<int> &nums1, vector<int> &nums2) {
        int n = nums1.size(), m = nums2.size();
        vector<vector<int>> dp(2, vector<int>(m + 1, 0));
        if (m > n)
            return maxDotProduct(nums2, nums1);
        // int dp[2][m+1];
        for (int i = 0; i <= m; ++i)
            dp[0][i] = inf;
        dp[1][0] = inf;
        int row, preRow = 0;
        for (int i = 1; i <= n; ++i) {
            row = i & 1;
            for (int j = 1; j <= m; ++j) {
                int Mut = nums1[i - 1] * nums2[j - 1];
                dp[row][j] = max(Mut, Mut + dp[preRow][j - 1]);
                int x = max(dp[row][j - 1], dp[preRow][j]);
                dp[row][j] = max(dp[row][j], x);
            }
            preRow = row;
        }
        return dp[row][m];
    }
};
```

#### [1438. 绝对差不超过限制的最长连续子数组](https://leetcode-cn.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)

```c
//使用堆来存储最大值和最小值，超时
typedef struct{
    int val, index;
} node;

int less(int a, int b){return a < b;}
int greater(int a,int b){return a>b;}
void heapPush(node *heap, int size, node k, int (*cmp)(int, int)){
    int son = size;
    while (son / 2 > 0){
        if (cmp(k.val, heap[son / 2].val))
            heap[son] = heap[son / 2];
        else
            break;
        son /= 2;
    }
    heap[son] = k;
}
void heapDelete(node *heap, int *size, int index, int (*cmp)(int, int)){
    int i = 1;
    while (i <= *size && heap[i].index != index)
        ++i;
    if (i == *size){
        (*size)--;
        return;
    }
    node k = heap[(*size)--];
    if (i / 2 > 0 && cmp(k.val, heap[i / 2].val)){
        heapPush(heap, *size, k, cmp);
    }else{
        int son = i * 2;
        while (son <= *size){
            if (son + 1 <= *size && cmp(heap[son + 1].val, heap[son].val))
                son++;
            if (cmp(heap[son].val, k.val))
                heap[son / 2] = heap[son];
            else
                break;
            son *= 2;
        }
        heap[son / 2] = k;
    }
}

void print(node *heap,int size){
    for(int i=1;i<=size;++i)printf("%d(%d)>",heap[i].val,heap[i].index);
    printf("\n");
}

int longestSubarray(int *nums, int numsSize, int limit)
{
    if (numsSize < 2)
        return 1;
    int left = 0, right = 0, maxLen = 0, maxSize = 0, minSize = 0;
    node maxHeap[numsSize+1], minHeap[numsSize+1];
    while (right < numsSize){
        node k = {nums[right], right};
        maxSize++, minSize++;
        heapPush(minHeap, minSize, k, less);
        heapPush(maxHeap, maxSize, k, greater);
        //print(maxHeap, maxSize), print(minHeap, minSize);
        while (maxHeap[1].val - minHeap[1].val > limit){
            heapDelete(minHeap, &minSize, left, less);
            heapDelete(maxHeap, &maxSize, left, greater);
            //print(maxHeap, maxSize), print(minHeap, minSize);
            left++;
        }
        right++;
        int len = right - left;
        if (len > maxLen)
            maxLen = len;
    }
    return maxLen;
}
//leetcode的方法：两个队列，分别存储到当前位置的窗口中可能成为最大值和最小值的元素。两个队列的头表示当前窗口内的最大值和最小值，当窗口内的最大值与最小值差不满足要求时，窗口左边界往右移动，直到删掉最大值或最小值。使得新窗口满足要求。
int longestSubarray(int *nums, int numsSize, int limit){
    int maxQue[numsSize], minQue[numsSize];
    int maxRight = 0, maxLeft = 0;
    int minRight = 0, minLeft = 0;
    int right = 0, left = 0;
    int maxLen = 0;
    while (right < numsSize){
        //新加入一个元素后，删除那些到当前位置的窗口中不可能成为最大值（最小值）的元素
        while (minLeft < minRight && minQue[minRight - 1] > nums[right])
            minRight--;
        while (maxLeft < maxRight && maxQue[maxRight - 1] < nums[right])
            maxRight--;
        //新加入的可能成为最大值（最小值）的元素
        maxQue[maxRight++] = nums[right];
        minQue[minRight++] = nums[right];
        //到当前位置的窗口内，最大值与最小值的差大于limit，不满足要求，移动左边界，直到删除最大值或最小值，使窗口满足要求。
        while (minLeft < minRight && maxLeft < maxRight && maxQue[maxLeft] - minQue[minLeft] > limit){
            if (nums[left] == minQue[minLeft])
                minLeft++;
            if (nums[left] == maxQue[maxLeft])
                maxLeft++;
            left++;
        }
        right++;
        maxLen = fmax(maxLen, right - left);
    }
    return maxLen;
}
```

#### [1610. 可见点的最大数目](https://leetcode-cn.com/problems/maximum-number-of-visible-points/)

```c++
//求角度atan2更方便，求区间和的最大值，可以将区间的角度整体加360后附在后面，就不用分开处理了。
class Solution {
public:
    int visiblePoints(vector<vector<int>> &points, int angle, vector<int> &location) {
        int x = location[0], y = location[1];
        int loc = 0, vertical = 0;
        map<double, int> deg;
        for (auto p : points) { //求各点对应的角度，
            int u = p[0], v = p[1];
            if (x == u && y == v) {
                loc++;
            } else if (x == u) {
                y < v ? deg[90]++ : deg[270]++;
            } else if (y == v) {
                x < u ? deg[0]++ : deg[180]++;
            } else {
                double t = fabs((double)(y - v) / (x - u));
                double d = atan(t) * 180.0 / M_PI;
                if (u > x) {
                    if (v < y)
                        d = 360.0 - d;
                } else {
                    if (v > y)
                        d = 180.0 - d;
                    else
                        d = d + 180.0;
                }
                deg[d]++;
            }
        }
        map<double, int>::iterator start = deg.begin(), rstart;
        double end = start->first + angle, rst;
        int cnt = 0, maxp = 0;
        while (start != deg.end() && start->first <= end) {
            cnt += start->second;
            start++;
        }
        if (start == deg.end())
            return cnt + loc;
        rstart = deg.begin(), maxp = cnt;
        while (start != deg.end()) { //窗口整体右移
            cnt += start->second;
            rst = start->first - angle;
            while (rstart->first < rst) {
                cnt -= rstart->second;
                rstart++;
            }
            maxp = max(maxp, cnt);
            start++;
        }
        rstart++;
        while (rstart != deg.end()) {//窗口分为前半部分，后半部分
            end = rstart->first + angle;
            start = deg.begin();
            rst = end - 360;
            cnt -= rstart->second;
            while (start->first <= rst) {
                cnt += start->second;
                start++;
            }
            maxp = max(maxp, cnt);
            rstart++;
        }
        return maxp+loc;
    }
};
```



#### [1622. 奇妙序列](https://leetcode-cn.com/problems/fancy-sequence/)

```c++
//整个数组的乘法和加法操作，超时
//使用线段数组或树状数组

const int mod = 1e9 + 7;
class SegmentTree
{
	vector<int> lazya, lazyb; //记录数据的操作，a*x+b,遍历到该点时才更新
public:
	SegmentTree(int n) : lazya(n * 4, 1), lazyb(n * 4, 0) {}

	void updateTree(int treeId, int left, int right, int i, int j, int a, int b) {
		if (right<i || left>j) { //当前区间在操作区间外
			return;
		}
		if (left >= i && right <= j) { //操作区间内的一个子空间
			lazya[treeId] = ((long)lazya[treeId] * a) % mod;
			lazyb[treeId] = ((long)lazyb[treeId] * a % mod + b) % mod;
			return;
		}
		int lchild = 2 * treeId + 1, rchild = 2 * treeId + 2;
		int mid = (left + right) / 2;
		if (lazya[treeId] != 1 || lazyb[treeId] != 0) { //累积左右孩子上的a,b
			lazya[lchild] = ((long)lazya[lchild] * lazya[treeId]) % mod;
			lazyb[lchild] = ((long)lazyb[lchild] * lazya[treeId] % mod + lazyb[treeId]) % mod;
			lazya[rchild] = ((long)lazya[rchild] * lazya[treeId]) % mod;
			lazyb[rchild] = ((long)lazyb[rchild] * lazya[treeId] % mod + lazyb[treeId]) % mod;
		}
		lazya[treeId] = 1; lazyb[treeId] = 0;//消除父亲节点上的a,b

		updateTree(lchild, left, mid, i, j, a, b);
		updateTree(rchild, mid + 1, right, i, j, a, b);
	}
	int queryTree(int treeId, int left, int right, int i) {
		if (left == right)return lazyb[treeId]; //查询到i节点
		int lchild = 2 * treeId + 1, rchild = 2 * treeId + 2;
		int mid = (left + right) / 2;
		if (lazya[treeId] != 1 || lazyb[treeId] != 0) { 
			lazya[lchild] = ((long)lazya[lchild] * lazya[treeId]) % mod;
			lazyb[lchild] = ((long)lazyb[lchild] * lazya[treeId] % mod + lazyb[treeId]) % mod;
			lazya[rchild] = ((long)lazya[rchild] * lazya[treeId]) % mod;
			lazyb[rchild] = ((long)lazyb[rchild] * lazya[treeId] % mod + lazyb[treeId]) % mod;
		}
		lazya[treeId] = 1; lazyb[treeId] = 0;
		if (i <= mid)return queryTree(lchild, left, mid, i); //查询节点在当前空间的左半边
		return queryTree(rchild, mid + 1, right, i); //右半边
	}
};
const int M = 1e5;
class Fancy {
	vector<int>arr;
	SegmentTree tree;
	int size;
public:
	Fancy() :size(0), tree(M + 1) {}

	void append(int val) {
		tree.updateTree(0, 0, M, size, size, 1, val);
		size++;
	}

	void addAll(int inc) {
		tree.updateTree(0, 0, M, 0, size - 1, 1, inc);
	}

	void multAll(int m) {
		tree.updateTree(0, 0, M, 0, size - 1, m, 0);
	}

	int getIndex(int idx) {
		if (idx >= size || idx < 0)return -1;
		return tree.queryTree(0, 0, M, idx);
	}
};


```



#### [1631. 最小体力消耗路径](https://leetcode-cn.com/problems/path-with-minimum-effort/)

+ 思路
  1. 二分法；给定一个值当作最小值，看看是否可以连通左上角和右下角（深度搜索或广度搜索）。或者BFS+DP；BFS遍历图，并储存起始节点到当前节点的最小高度，
  
  2. 并查集；根据边的高度对边递增排序，然后依次合并边连接两个集合，并判断左上角和右下角是否在一个集合里。为每个节点编号，则表示一条边只需两个值。
  
  3. dijkstra：查找队列里的最小值，则起始点到该点的最小距离可以确定下来，
  
     ```c
     #define MAXSIZE 10001
     #define MAXHEIGHT 1000000
     typedef struct node {
         int k, v;
     } node;
     int dir[4][2] = { { 1, 0 }, { 0, 1 }, { -1, 0 }, { 0, -1 } };
     
     void minHeapPop(node* queue, int s, int i)//末尾节点代替根节点
     {
         queue[0] = queue[i];
         int son = i * 2;
         while (son <= s) {
             if (son + 1 <= s && queue[son + 1].v < queue[son].v)
                 son++;
             if (queue[0].v > queue[son].v) { //插入节点还是比最小子节点大，则最小子节点上移
                 queue[son / 2] = queue[son];
                 son *= 2;
             } else     //比子节点都小。
                 break;
         }
         queue[son / 2] = queue[0]; 
     }
     void minHeapPush(node* queue, int s) //在末尾插入节点
     {
         int son = s;
         queue[0] = queue[s];
         while (son / 2 > 0 && queue[0].v < queue[son / 2].v) {//父亲节点大于子节点
             queue[son] = queue[son / 2];//父亲节点下移
             son /= 2;
         }
         queue[son] = queue[0];
     }
     int minimumEffortPath(int** heights, int heightsSize, int* heightsColSize)
     {
         int row = heightsSize, col = heightsColSize[0];
         node queue[MAXSIZE];
         int N = row * col, cnt = 0;
         int visited[N], dis[N];
         memset(visited, 0, sizeof(visited));
         for (int i = 0; i < N; ++i)
             dis[i] = MAXHEIGHT;
     
         dis[0] = 0;
         queue[++cnt].k = 0, queue[cnt].v = 0;
         while (cnt >= 1) {
             int x = queue[1].k;
             queue[1] = queue[cnt--];
             minHeapPop(queue, cnt, 1);
     
             if (visited[x]) //已找到最小的边。
                 continue;
             if (x == N - 1)
                 break;
     
             visited[x] = 1;
             int c = x % col, r = x / col;
             for (int i = 0; i < 4; ++i) {
                 int dc = c + dir[i][1], dr = r + dir[i][0];
                 if (dr >= 0 && dr < row && dc >= 0 && dc < col ) {
                     int dx = dr * col + dc;
                     int h = abs(heights[dr][dc] - heights[r][c]);
                     int m = dis[x] > h ? dis[x] : h;
                     if (dis[dx] > m) {
                         dis[dx] = m;
                         queue[++cnt].k = dx, queue[cnt].v = dis[dx];
                         minHeapPush(queue, cnt);
                     }
                 }
             }
             // printf("push:");
             // for(int a=1;a<=cnt;++a)printf("%d(%d)->",queue[a].k,queue[a].v);
             // printf("\n");
         }
         return dis[N - 1];
     }
     
     ```

```c
//超时，时间为3^(m*n)
//方法：随便先连通一条路径，然后修改路径中最大高度的前一位置的方向，看看能否找到更小的路径
#define MAXHEIGHT 10e6
#define MAXCOLSIZE 101
#define min(a, b) (a > b ? b : a)
#define max(a, b) (a > b ? a : b)

void print(int **heights, int row, int col)
{
    system("cls");
    for (int i = 0; i <= row; ++i){
        for (int j = 0; j <= col; ++j){
            if (heights[i][j])
                printf("%1d", heights[i][j] % 10);
            else
                printf(" ");
        }
        printf("\n");
    }
    Sleep(500);
}


// priorMax 从起始点沿着路径到当前节点的高度；
int gonext(int r, int c, int row, int col, int **heights, int priorMax, int *globle)
{
    print(heights, row, col);
    if (r == row && c == col){
        *globle = priorMax;
        return 0;
    }

    int t = heights[r][c];
    heights[r][c] = 0;
    int nextMin = MAXHEIGHT;
    for (int k = 0; k < 4; ++k){
        if (*globle == priorMax){ //返回到最大高度的前一位置
            print(heights,row,col);
            heights[r][c] = t;
            return nextMin;
        }
        int flag = 0;
        // 往下、往右、往上、往左
        if (k == 0 && ++r <= row || k == 1 && ++c <= col ||
            k == 2 && --r >= 0 && c < col && c > 0 ||
            k == 3 && --c >= 0 && r < row && r > 0)
            flag = 1;
        if (flag && heights[r][c]){         //下一节点可达
            int i = abs(t - heights[r][c]); //当前节点到下一节点的高度
            if (i < *globle){               //可能存在更小高度的路径。
                int m = max(priorMax, i);
                int j = gonext(r, c, row, col, heights, m, globle); //下一节点到终点的最小高度
                m = max(i, j);
                nextMin = min(m, nextMin);
            }
        }
        if (k == 0 && --r || k == 1 && --c || k == 2 && ++r || k == 3 && ++c);
    }

    heights[r][c] = t;
    return nextMin;
}
int minimumEffortPath(int **heights, int heightsSize, int *heightsColSize)
{
    int minColSize = MAXCOLSIZE;
    for (int i = 0; i < heightsSize; ++i){
        if (minColSize > heightsColSize[i])
            minColSize = heightsColSize[i];
    }
    if (heightsSize == 1 && minColSize == 1)
        return 0;
    int globle = MAXHEIGHT;
    gonext(0, 0, heightsSize - 1, minColSize - 1, heights, 0, &globle);
    return globle;
}
//转化为循环
char x[5][3] = { "*", "||", "->", "||", "<-" };
int dirs[4][2] = { { 1, 0 }, { 0, 1 }, { -1, 0 }, { 0, -1 } }; //下，右，上，左
void print(int* arr, int row, int col)
{
    system("cls");
    for (int i = 0; i < col; ++i)
        printf("%2d", i);
    printf("\n");
    for (int i = 0; i < row; ++i) {
        printf("%2d ", i);
        for (int j = 0; j < col; ++j) {
            int k = i * col + j;
            if (arr[k])
                printf("%s", x[arr[k]]);
            else
                printf("  ");
        }
        printf("\n");
    }
    // Sleep(100);
}
void HideCursor()
{
    CONSOLE_CURSOR_INFO cursor_info = {1, 0};
    SetConsoleCursorInfo(GetStdHandle(STD_OUTPUT_HANDLE), &cursor_info);
}
int minimumEffortPath(int **heights, int heightsSize, int *heightsColSize)
{
    int row = heightsSize;
    int col = heightsColSize[0];
    if (row == 1 && col == 1)
        return 0;
    int globle = MAXHEIGHT;
    int q[row * col][2];
    int cnt = 0;
    q[cnt][0] = 0, q[cnt][1] = 0;
    int seen[row * col], priorMax[row * col];
    memset(seen, 0, sizeof(seen));
    memset(priorMax, 0, sizeof(priorMax));
    seen[0] = 1;

    int x, y;
    while (cnt >= 0){
        int k = 0;
        while (k < 4){  //依次访问四个方向
            x = q[cnt][0], y = q[cnt][1];
            int nx = x + dirs[k][0];
            int ny = y + dirs[k][1];
            if ((k == 0 && nx < row ||
                 k == 1 && ny < col ||
                 k == 2 && nx >= 0 && ny < col - 1 && ny > 0 ||
                 k == 3 && ny >= 0 && nx < row - 1 && nx > 0) &&
                !seen[nx * col + ny]){
                int t = abs(heights[nx][ny] - heights[x][y]);
                if (t < globle){
                    cnt++;
                    priorMax[cnt] = priorMax[cnt - 1] > t ? priorMax[cnt - 1] : t;
                    q[cnt][0] = nx, q[cnt][1] = ny;
                    printf("(%d,%d)[%d-%d]->", nx, ny, t, globle);
                    seen[nx * col + ny] = k + 1;
                    break;
                }
            }
            k++;
            if (x == row - 1 && y == col - 1) //到达终点
                globle = priorMax[cnt];
            
            while (cnt >= 0 && (k == 4 || globle == priorMax[cnt])){ //方向访问完，或最大值出现在前面，回退一步
                //print(seen, row, col);
                seen[q[cnt][0] * col + q[cnt][1]] = 0;
                cnt--;

                if (cnt < 0)
                    break;

                x = q[cnt][0], y = q[cnt][1];
                if (q[cnt + 1][0] > x){ //以前往下，现在往右
                    k = 1;
                }else if (q[cnt + 1][1] > y){ //以前往右，现在往上
                    k = 2;
                }else if (q[cnt + 1][0] < x){ //以前往上，现在往左
                    k = 3;
                }
            }
        }
    }
    return globle;
}
```

#### [1743. 从相邻元素对还原数组](https://leetcode-cn.com/problems/restore-the-array-from-adjacent-pairs/)

```c
//方法：哈希，存储节点可以连接的节点，中间节点为2个，两端节点为1个，从其中一个端点出发，遍历一遍即得数组。
#define M 100000
int* restoreArray(int** adjacentPairs, int adjacentPairsSize, int* adjacentPairsColSize, int* returnSize)
{
    *returnSize = adjacentPairsSize + 1;
    int to[2 * M + 1][2];  //在本地笔记本上出错，放在函数外面可以通过。
    int cnt[2 * M + 1];
    memset(cnt, 0, sizeof(cnt));
    for (int i = 0; i < adjacentPairsSize; ++i) {
        int x = adjacentPairs[i][0] + M, y = adjacentPairs[i][1] + M;
        to[x][cnt[x]++] = y;
        to[y][cnt[y]++] = x;
    }
    int* arr = (int*)malloc(sizeof(int) * (adjacentPairsSize + 1));
    int k = 0, i;
    for (i = 0; i < M * 2 + 1; ++i) {
        if (cnt[i] == 1) {
            break;
        }
    }
    memset(cnt,0,sizeof(cnt));  //用来表示节点是否访问过
    while (k <= adjacentPairsSize) {
        arr[k++] = i - M;
        cnt[i]=1;
        int j=to[i][0];
        if(cnt[j])i=to[i][1];
        else i=j;
    }
    return arr;
}

```

#### [1742. 盒子中小球的最大数量](https://leetcode-cn.com/problems/maximum-number-of-balls-in-a-box/)

```c
//方法：不需要每个数字都求一下各位数之和，其和与前一位数字k-1、k/10有关。可以减少一些操作。
int sum(int k)
{
    int s = 0;
    while (k) {
        s += (k % 10);
        k /= 10;
    }
    return s;
}
int countBalls(int lowLimit, int highLimit)
{
    int cnt[46], i = lowLimit, s;
    memset(cnt, 0, sizeof(cnt));
    while (lowLimit <= highLimit) {
        s = sum(lowLimit);
        cnt[s]++;
        int k = (lowLimit / 10 + 1) * 10;  //找到下一次发生进位的地方，即不满足数字加一，和加一规则的位置。
        if (k > highLimit)
            k = highLimit;
        while (++lowLimit < k) {
            cnt[++s]++;
        }
    }
    int m = 0;
    for (int i = 1; i < 46; ++i) {
        if (m < cnt[i])
            m = cnt[i];
    }
    return m;
}
```

#### [1779. 找到最近的有相同 X 或 Y 坐标的点](https://leetcode-cn.com/problems/find-nearest-point-that-has-the-same-x-or-y-coordinate/)

```c++
//简单的遍历，找最小值。
class Solution {
public:
    int nearestValidPoint(int x, int y, vector<vector<int>>& points) {
        int minIndex = -1, minDis = 10000;
        for (int i = 0; i < points.size(); ++i) {
            if (x == points[i][0] || y == points[i][1]){
                int dis = abs(x - points[i][0]) + abs(y - points[i][1]);
                if (dis < minDis)
                    minDis = dis, minIndex = i;
            }
        }
        return minIndex;
    }
};
```

#### [1780. 判断一个数字是否可以表示成三的幂的和](https://leetcode-cn.com/problems/check-if-number-is-a-sum-of-powers-of-three/)

```c++
//判断一个数是否可以表示为3的幂之和，依次整除3，如果不能整除3，则可能有0次幂，减一，再整除，如果不行则为false.
class Solution {
public:
    bool checkPowersOfThree(int n) {
        while (n){
            if (n % 3==2)
                return false;
            n /= 3;
        }
        return true;
    }
};
```

#### [1782. 统计点对的数目](https://leetcode-cn.com/problems/count-pairs-of-nodes/)

```c++
//两节点的边数和，大于给定值，求这样的点对数。将遍历节点转为遍历边。
class Solution {
public:
    vector<int> countPairs(int n, vector<vector<int>> &edges, vector<int> &queries) {
        unordered_map<int, int> overlap;
        vector<int> deg(n + 1, 0);
        vector<pair<int, int>> distinctedges;
        auto encode = [n](int v, int u) -> int { //将节点对编码为整数
            return max(v, u) * n + min(v, u);
        };
        for (auto e : edges) {
            int v = e[0], u = e[1];
            int id = encode(v, u);
            deg[v]++, deg[u]++;
            if (overlap.find(id) == overlap.end()) {
                overlap[id] = 1;
                distinctedges.emplace_back(u, v);
            } else
                overlap[id]++;
        }
        vector<int> sortDeg(deg.begin() + 1, deg.end());
        sort(sortDeg.begin(), sortDeg.end());
        vector<int> ans;
        for (auto x : queries) {
            int l = 0, r = n - 1, cnt = 0;
            while (l < n) {  //查询两点的边之和大于query的节点对数，排序好的，从左往右遍历，r右边表示能和满足要求O(n)
                while (r > l && sortDeg[l] + sortDeg[r] > x)
                    r--;
                cnt += n - max(r, l) - 1;
                l++;
            }
            for (auto e : distinctedges) {
                int v = e.first, u = e.second;
                int id = encode(v, u);
                if (deg[v] + deg[u] > x && deg[v] + deg[u] - overlap[id] <= x)
                    cnt--;
            }
            ans.push_back(cnt);
        }
        return ans;
    }
};
```

#### [1784. 检查二进制字符串字段](https://leetcode-cn.com/problems/check-if-binary-string-has-at-most-one-segment-of-ones/)

```c++
//检查字符串是否出现多个的由‘1’构成的子串。
class Solution {
public:
    bool checkOnesSegment(string s) {
        int i = 1, n = s.size();
        while (i < n && s[i] == '1')
            i++;
        if (i == n)
            return true;
        while (i < n && s[i] == '0')
            i++;
        if (i == n)
            return true;
        return false;
    }
};
```

#### [1785. 构成特定和需要添加的最少元素](https://leetcode-cn.com/problems/minimum-elements-to-add-to-form-a-given-sum/)

```c++
//求还需多少各不大于limit的数，使得数组的和达到target。
class Solution{
public:
    int minElements(vector<int> &nums, int limit, int goal){
        long sum = 0; //注意可能会超出int的范围
        for (int i = 0; i < nums.size(); ++i)
            sum += nums[i];
        sum = abs(goal - sum);
        return sum / limit + (sum % limit ? 1 : 0);
    }
};
```

#### [1792. 最大平均通过率](https://leetcode-cn.com/problems/maximum-average-pass-ratio/)

```c++
//给定一组分子分母，操作分子分母同时加一，给定n次操作，求最大的平均值
class cmp {
public:
    bool operator()(const pair<int, int> &p1, const pair<int, int> &p2) {
        double x = (double)(p1.first + 1) / (p1.second + 1) -
                   (double)(p1.first) / (p1.second);
        double y = (double)(p2.first + 1) / (p2.second + 1) -
                   (double)(p2.first) / (p2.second);
        return x < y;
    }
};
//pair<int,int>有预定义的大小于重载运算符，先比较第一个，再比较第二个；默认的less不会调用我们编写全局重载运算符
/*bool operator<(const pair<int, int> &p1, const pair<int, int> &p2) {
    double x = (double)(p1.first + 1) / (p1.second + 1) -
               (double)(p1.first) / (p1.second);
    double y = (double)(p2.first + 1) / (p2.second + 1) -
               (double)(p2.first) / (p2.second);
    return x < y;
}*/
class Solution {
public:
    double maxAverageRatio(vector<vector<int>> &classes, int extraStudents) {
        priority_queue<pair<int, int>, vector<pair<int, int>>, cmp> heap;
        int cnt = 0, n = classes.size();
        for (auto c : classes) {
            if (c[0] == c[1]) {
                cnt++;
                continue;
            }
            heap.emplace(c[0], c[1]);
        }
        while (extraStudents) {
            if (!heap.empty()) { //可能为空
                auto x = heap.top();
                heap.pop();
                heap.emplace(x.first + 1, x.second + 1);
            }
            extraStudents--;
        }
        double sum = cnt;
        while (!heap.empty()) {
            auto x = heap.top();
            // cout<<x.first<<","<<x.second<<";";
            heap.pop();
            sum += (double)x.first / x.second;
        }
        return sum / n;
    }
};
```

#### [LCP 14. 切分数组](https://leetcode-cn.com/problems/qie-fen-shu-zu/)

```c++
//第一中方法超时
class Solution1 {
	int gcd(int a, int b) {
		if (a > b)return gcd(b, a);
		while (b % a) {
			int c = b % a;
			b = a, a = c;
		}
		return a;
	}
	int gcd2(int a, int b) {
		if (a > b)return gcd2(b, a);
		while (a != b) {
			int x = b - a;
			if (x > a)b = x;
			else b = a, a = x;
		}
		return a;
	}
public:
	int splitArray(vector<int>& nums) {
		int n = nums.size();
		vector<int> dp(n, 1);
		for (int i = 1; i < n; ++i) {
			dp[i] = dp[i - 1] + 1; //最多i单独为一个子数组
			if (gcd(nums[i], nums[0]) > 1) {
				dp[i] = 1;
				continue;
			}
			for (int j = 1; j < i; j++) { //遍历前半部分，是否可以与nums[i]组成新的子数组
				if (gcd(nums[i], nums[j]) > 1) {
					dp[i] = min(dp[i], dp[j]);
				}
			}
		}
		return dp[n - 1];
	}
};
const int M = 1e6 + 1;
const int N = 1e5 + 1;
int min_prime[M], prime[N];
int g[M];
class Solution {
public:
	int splitArray(vector<int>& nums) {
		int n = nums.size();
		int m = *max_element(nums.begin(), nums.end());
		for (int i = 2; i <= m; i++) {				//求2-m间的质数和每个数的最小质数因子
			if (!min_prime[i]) {					//质数的最小质数因子，不会在自己出现前出现
				prime[++prime[0]] = i;
				min_prime[i] = i;
			}
			for (int j = 1; j <= prime[0]; j++) {	//遍历已经找到了的质数，求以他们为最小质数因子的数
				if (i > m / prime[j]) break;		//i*prime[j]大于数组里的最大值，
				min_prime[i * prime[j]] = prime[j]; //向上求某个的数的最小值数
				if (i % prime[j] == 0) break;		//4*3；6*2；确保prime[j]是某个数可分的最小质数因子，减少重复计算
			}
		}
        
		for (int j = 1; j <= prime[0]; j++)		//所有结果设为最大值
			g[prime[j]] = n;
		for (int x = nums[0]; x > 1; x /= min_prime[x])	//初始化第一个节点，表示节点之前所需的最小分割次数
			g[min_prime[x]] = 0;
		int ans = 1;
		for (int i = 0; i < n; i++) {
			ans = i + 1;									//新加元素可能导致的最大值
			for (int x = nums[i]; x > 1; x /= min_prime[x])	//找到之前存在共同因子的数，他之前所需的最小分割次数+1
				ans = min(g[min_prime[x]] + 1, ans);
			if (i == n - 1) break;
			for (int x = nums[i + 1]; x > 1; x /= min_prime[x])	//新加一个数，更新g，新加的数与之前的数存在共同因子，
				g[min_prime[x]] = min(g[min_prime[x]], ans);
		}
		return ans;
	}
};
```

#### [面试题 17.26. 稀疏相似度](https://leetcode-cn.com/problems/sparse-similarity-lcci/)

```c++
//两个数组的交集
class Solution {
public:
	vector<string> computeSimilarities(vector<vector<int>>& docs) {
		unordered_map<int, vector<int>>cnt;
		int n = docs.size();
		vector<string>ans;
		for (int i = 0; i < n; ++i) {
			unordered_map<int, int>inter;
			int m = docs[i].size();
			for (auto c : docs[i]) {
				if (i && cnt.find(c) != cnt.end()) {
					for (auto x : cnt[c]) {
						inter[x]++;
					}
				}
				cnt[c].push_back(i);
			}
			char temp[100];
			for (auto x : inter) {
				ostringstream ostr;
				ostr << x.first << "," << i << ": ";
				ostr << setiosflags(ios::fixed) << setprecision(4);
				ostr << (double)x.second / (docs[x.first].size() + m - x.second) + 1e-9; //1e-9需要，
				ans.push_back(ostr.str());
				// int id=x.first;
				// double y=(double)x.second/(docs[id].size()+m-x.second);
				// sprintf(temp, "%d,%d: %0.4lf", id, i, y + 1e-9);
				// ans.push_back(temp);
			}
		}
		return ans;
	}
};
```

#### [面试题 17.24. 最大子矩阵](https://leetcode-cn.com/problems/max-submatrix-lcci/)

```c++
//求连续子数组的最大和，累积到当前位置的和sum，如果sum<0，当前片段产生了只会使后面的和更小，停止累积，清零。sum>0；继续累积。
class Solution {
public:
	vector<int> getMaxMatrix(vector<vector<int>>& matrix) {
		int n = matrix.size(), m = matrix[0].size();
		vector<int>colSum(m), ans(4);
		int maxSum = INT_MIN;
		for (int i = 0; i < n; ++i) {
			colSum.assign(m, 0); //重新统计每列的和
			for (int j = i; j < n; ++j) {
				int lineSum = 0, id = 0; //colSum累积的最大和
				for (int k = 0; k < m; ++k) {
					colSum[k] += matrix[j][k];
					lineSum += colSum[k];
					if (lineSum > maxSum) {//出现更大的累积和
						maxSum = lineSum;
						ans = { i,id,j,k };
					}
					if (lineSum < 0) { //累积的和小于0，不再继续累积
						lineSum = 0;
						id = k + 1;
					}
				}
			}
		}
		return ans;
	}
};
```

