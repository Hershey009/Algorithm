| 动态规划&nbsp; | 二叉树 | 回溯算法&nbsp;|二分查找| &nbsp;贪心算法&nbsp;&nbsp;|&nbsp;待定&nbsp;&nbsp;|待定| &nbsp;&nbsp;待定&nbsp;&nbsp; |待定| &nbsp;&nbsp;待定&nbsp;&nbsp; |
| :---: | :----: | :---: | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| [:pencil2:](#pencil2-动态规划) | [:computer:](#computer-二叉树) | [:cloud:](#cloud-回溯算法) | [:art:](#art-二分查找) | [:floppy_disk:](#floppy_disk-贪心算法) |[:coffee:](#coffee-待定)| [:bulb:](#bulb-待定) |[:wrench:](#wrench-待定)| [:watermelon:](#watermelon-待定) |[:memo:](#memo-待定)|


## :pencil2: 动态规划
- [	#322 零钱兑换](https://leetcode-cn.com/problems/coin-change/) dp[i-coin]
- [	#198 打家劫舍](https://leetcode-cn.com/problems/house-robber/) dp[i]=max(dp[i-1],dp[i-2]+nums[i]),int tmp,dp_i,dp_pre_i压缩空间
- [	#213 打家劫舍 II](https://leetcode-cn.com/problems/house-robber-ii/) 调用两次，一次偷前不偷尾，另一次相反
- [337. 打家劫舍 III](https://leetcode-cn.com/problems/house-robber-iii/) pair中first不偷second偷，看root偷yes和不偷no哪个大
- [	#121 买卖股票的最佳时机](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock/) dp[i][k][1]=(dp[i-1][k][1],dp[i-1][k-1][0]-prices[i])k=1去k，右边只剩-prices[i],dp_i_0,dp_i_1压缩空间
- [	#122 买卖股票的最佳时机 II](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-ii/) k可直接去除
- [	#309 最佳买卖股票时机含冷冻期](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-with-cooldown/)//买入时dp[i-2][0]-prices[i],如果不是前2天卖而是前好几天，本应是dp[i-1][0]-prices[i]但二者结果相同因为i-1天没有交易
- [	#714 买卖股票的最佳时机含手续费](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-with-transaction-fee/) -fee
- [	#123 买卖股票的最佳时机 III](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-iii/)//同下
- [	#188 买卖股票的最佳时机 IV](https://leetcode-cn.com/problems/best-time-to-buy-and-sell-stock-iv/) 2k>n时去除k，否则，dp[i][k][0]=max(dp[i-1][k][0],dp[i-1][k][1]+prices[i])dp[i][k][1]=max(dp[i-1][k][1],dp[i-1][k-1][0]-prices[i])
- [#518 零钱兑换 II](https://leetcode-cn.com/problems/coin-change-2/) 完全背包dp[i][j]=max(dp[i-1][j],dp[i][j-coins[i-1])
- [	#416 分割等和子集](https://leetcode-cn.com/problems/partition-equal-subset-sum/) 01背包dp[i][j]=dp[i-1][j]||dp[i-1][j-nums[i-1]]
- [	#1143 最长公共子序列](https://leetcode-cn.com/problems/longest-common-subsequence/) 相同dp[i][j]=1+dp[i-1][j-1],不同dp[i][j]=max(dp[i-1][j],dp[i][j-1])
- [	#516 最长回文子序列](https://leetcode-cn.com/problems/longest-palindromic-subsequence/) 左右相同dp[i][j]=2+dp[i+1][j-1],不同dp[i][j]=max(dp[i+1][j],dp[i][j-1])
- [	#53 最大子序和](https://leetcode-cn.com/problems/maximum-subarray/) 子序必须以nums[i]结尾dp[i]=max(dp[i-1]+nums[i],nums[i]),dp_i压缩空间，res不断更新最大值
- [	#72 编辑距离](https://leetcode-cn.com/problems/edit-distance/) 相同，dp[i][j]=dp[i-1][j-1],不同，删a，删b，都删dp[i][j]=max(dp[i-1][j],max(dp[i][j-1],dp[i-1][j-1])+1
- [	#剑指 Offer 10- I 斐波那契数列](https://leetcode-cn.com/problems/fei-bo-na-qi-shu-lie-lcof/) 注意取模,dp_i,dp_pre_i,tmp压缩空间
- [	#746 使用最小花费爬楼梯](https://leetcode-cn.com/problems/min-cost-climbing-stairs/) 从上阶梯或上上阶梯来dp[i]=max(dp[i-1]+cost[i-1],dp[i-2]+cost[i-2]),int tmp,dp_pre_i,dp_i压缩空间
- [	#718 最长重复子数组](https://leetcode-cn.com/problems/maximum-length-of-repeated-subarray/) 子数组包含A[i],B[i]，A[i]B[i]等，dp[i][j]=dp[i-1][j-1]+1,不等，dp[i][j]=0;
- [	#300 最长上升子序列](https://leetcode-cn.com/problems/longest-increasing-subsequence/) dp[i]=max(dp[j]+1,dp[i])要么从j过来要么不要
- [	#279 完全平方数](https://leetcode-cn.com/problems/perfect-squares/) dp[i]=min(dp[i-j* j]+1,dp[i])要么用j要么不用
- [	#1277 统计全为 1 的正方形子矩阵](https://leetcode-cn.com/problems/count-square-submatrices-with-all-ones/) dp[i][j]=min(dp[i-1][j],min(dp[i][j-1],dp[i-1][j-1]),dp[i][j]是以i,j为右下顶点，全是1的最大正方形边长，也是个数，不断count+=dp[i][j]
- [	#152 乘积最大子数组](https://leetcode-cn.com/problems/maximum-product-subarray/) 由于负负可能很大，维护max_dp[i] min_dp[i],二个每次都要在max_dp[i-1]* nums[i],min_dp[i-1]* nums[i], nums[i]中取一个最大和最小保存
- [	#120 三角形最小路径和](https://leetcode-cn.com/problems/triangle/) 下三角，dp[i][j]=min(dp[i-1][j-1],dp[i-1][j])+nums[i][j],res选出最后一行最小值,可降维但可读性低
- [	#70 爬楼梯](https://leetcode-cn.com/problems/climbing-stairs/) dp[i]=dp[i-1]+dp[i-2]，可tmp，dp_i,dp_pre_i压缩
- [	#64 最小路径和](https://leetcode-cn.com/problems/minimum-path-sum/) dp[i][j]=min(dp[i-1][j],dp[i][j-1])+nums[i][j]
- [	#62 不同路径](https://leetcode-cn.com/problems/unique-paths/) dp[i][j]=dp[i-1][j]+dp[i][j-1]
- [	#63 不同路径 II	](https://leetcode-cn.com/problems/unique-paths-ii/) if(!nums[i][j])dp[i][j]=dp[i-1][j]+dp[i][j-1] 如果有障碍物就是0
- [	#5 最长回文子串](https://leetcode-cn.com/problems/longest-palindromic-substring/) 求begin和end用substr复制子字符串，如果左右不等就是false，相等，长度<=3为true，相等且长度大于3,dp[i][j]=dp[i+1][j-1],只要true就不断更新begin=i，end=j
- [	#343 整数拆分](https://leetcode-cn.com/problems/integer-break/) 要么拆一个j，(i-j) * j,要么不变，dp[i]要么继续拆j * dp[i-j]
- [	#221 最大正方形](https://leetcode-cn.com/problems/maximal-square/) max_dp不断找出dp[i][j]最大值就是最大边长
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :computer: 二叉树
八成模板题，实际上是有的操作需要后序==从何来？有的操作需要前序==怎么下去？偶尔需要中序遍历
- [222. 完全二叉树的节点个数](https://leetcode-cn.com/problems/count-complete-tree-nodes/) int left=help(root->left),实现(不管root是哪个root，它的left就一定能表示这个root左子树有多少个节点)，需要做到(root从何来？后序遍历return left+right+1；怎么下去？if(空节点)return 0)return left+right+1;求出左右子树节点数加自身
- [112 路径总和](https://leetcode-cn.com/problems/path-sum/) bool left=help(root->left) 实现(不管root是哪个root，它的left就一定能表示这个root从左边下去的最终目标和是否符合),需要做到(root从何来？return left||right表示root能否符合；怎么下去？每次下去sum-=root->val;if(叶节点)return root->val==sum；if(空节点)return false肯定凑不出sum哪怕sun是0)，return left||right求出root作为根节点的左右子树能否有一个符合
- [#113 路径总和 II](https://leetcode-cn.com/problems/path-sum-ii/)help(root->left),实现(不管root是哪个root，它的left就一定能表示这个root从左边下去能够吧每一条路放进res)需要做到(从何来？由于来之前一步path多放了一个，path.pop()达到来之后.怎么下去？path.push_back(root->val)if(根结点)res.push_back(path),if(空节点)return;)return res;
- [	#437 路径总和 III](https://leetcode-cn.com/problems/path-sum-iii/)第一步{help(root->left) 实现(不管root是哪个root，从左子树下去就能不断算出符合的路径数)需要做到(sum-=root->val if(sum==0)count++ if(空节点)return ;)}第二步{pathSum(root->left)实现(不管root是哪个root，从左子树下去就能保存所有节点作为起点是否有路径符合)需要做到(从何来？无，怎么下去？经过每个节点都help(root)保存该节点作为起点的符合路径数。)return count;}
- [110 平衡二叉树](https://leetcode-cn.com/problems/balanced-binary-tree/) 第一步{int left=help(root->left) 实现(不管root是哪个root，它的left就一定能表示这个root左子树高度),需要做到(从何来？return 1+max(left,right),向何去?if(空节点)return 0),return 1+max(left,right)求出树高度}  第二步{bool left=isBalanced(root->left),实现(不管root是哪个root，它的left就一定能表示这个root左子树的左右子树也满足题意),需要做到(从何来?return left&&right,怎么下去？if(左子树高度与右子树高度差1以内)继续下去，if(空节点)return true;)return left&&right求出根结点是否满足，return false在高度差不行无法下去时 }
- [#104 二叉树的最大深度](https://leetcode-cn.com/problems/maximum-depth-of-binary-tree/) - [110 平衡二叉树](https://leetcode-cn.com/problems/balanced-binary-tree/)已经实现
- [	#100 相同的树](https://leetcode-cn.com/problems/same-tree/) bool left=help(p->left,q->left) 实现(不管p q是哪个p q，他们的left就一定能表示这两个p q左子树是否相同),需要做到(从何来?return left&&right左右子树同时成立。怎么下去？if(p->val!=q->val)return false;if(p或q一个有一个没有)return false,if(都没有)return true),return left&&right求出pq作为根结点能否符合题意
- [	#101 对称二叉树](https://leetcode-cn.com/problems/symmetric-tree/) bool out=help(p->left,q->right),实现(不管p q是哪个p q，他们的out就一定能表示这两个pq靠外的子树是否相同),需要做到(从何来？return left&&right；怎么下去？if(p->val!=q->val)reutrnflase ;if(q p一个不存在一个在)return false;if(p q都不在return true),return out&&in求出pq作为根结点能否符合题意
- [	#257 二叉树的所有路径](https://leetcode-cn.com/problems/binary-tree-paths/) help(root->left),实现(不管root是哪个root，从左边下去时都能添加所有root->val和->到string path,添加所有path到res),需要做到(从何来？不用.怎么下去？path+=to_string(root->val),path+="->";if(叶节点)res.push_back(path)if(空节点)return ;)return res;
- [404. 左叶子之和](https://leetcode-cn.com/problems/sum-of-left-leaves/) help(root->left),实现(不管root是哪个root，从左边下去都能添加左叶子到int res),需要做到(从何来？不用。怎么下去？一直下去，if(左节点是叶节点)res.push_back(root->left->val)if(空节点)return ;)return res;
- [	#236 二叉树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-tree/)TreeNode* left=help(root->left),实现(不管root是哪个root，它的left就一定能在这个root左子树有p或q时返回p或q，否则返回空),需要做到(if(!left)return right;if(!right)return left;if(都有)return root)怎么下去？下去，if(root==q或p)return root,if(空节点)return nullptr;)return root或空节点
- [	#235 二叉搜索树的最近公共祖先](https://leetcode-cn.com/problems/lowest-common-ancestor-of-a-binary-search-tree/) 同上
- [	#226 翻转二叉树](https://leetcode-cn.com/problems/invert-binary-tree/) invertTree(root->left),实现(不管root是哪个root，从左边下去经过每个节点都能翻转)，需要做到(从何来？没有。怎么下去？下去，每次swap(左右),if(空节点)return;)return root
- [	#199 二叉树的右视图](https://leetcode-cn.com/problems/binary-tree-right-side-view/) 层序遍历，特点是在i=level_size-1时把pop的节点放进res
- [	#124 二叉树中的最大路径和](https://leetcode-cn.com/problems/binary-tree-maximum-path-sum/) int left=max(0,help(root->left)),实现(不管root是哪个root，这个root的left就一定能表示左子树一条路径所能贡献的最大值)，需要做到(从何来？return root->val+max(left,right)，怎么下去？下去，if(空节点)return 0;)res不断更新root->val+left+right,return res
- [	#129 求根到叶子节点数字之和](https://leetcode-cn.com/problems/sum-root-to-leaf-numbers/) int left=help(root->left)，实现(不管root是哪个root，它的left就一定能表示这个root从左子树下去节点和),需要做到(从何来？return left+right;怎么下去？下去，不断更新sum=sum*10+root->val；if(叶节点)return sum;if(空节点)return 0；
- [	#116 填充每个节点的下一个右侧节点指针](https://leetcode-cn.com/problems/populating-next-right-pointers-in-each-node/) 同上
- [701. 二叉搜索树中的插入操作](https://leetcode-cn.com/problems/insert-into-a-binary-search-tree/) root->left=insertIntoBST(root->left);要实现(不管root是哪个root，root->left在空着符合条件时能够插入)需要做到(从何来？不用。怎么下去？if(val<root->val)下去，if(空节点)return new node(val);)最后返回root
- [687. 最长同值路径](https://leetcode-cn.com/problems/longest-univalue-path/) int left=help(root->left) 要做到(不管root是哪个root，它的left就一定能表示这个root从左子树下去相同节点个数)需要做到(从何来？if(root->val==上一个节点val)return max(left,right)+1;否则return 0；怎么下去？下去，if(空节点)return 0;)return res-1,res表示节点数不断更新left+right+1
- [617. 合并二叉树](https://leetcode-cn.com/problems/merge-two-binary-trees/) root->left=help(p->left,q->left) 实现(无论root是新树的哪个节点，root->left一定能指向p q左节点的合并节点)需要做到(从何来？无，怎么下去？if(都有节点)return new node*(p->val+q->val)，if(q p一个有节点)return 它；if(都没有)return nullptr)return root
- [543. 二叉树的直径](https://leetcode-cn.com/problems/diameter-of-binary-tree/) int left=help(root->left) 实现(不管root是哪个root，它的left一定能表示这个root左子树最长路)需要做到(从何来 return left+right+1,怎么下去，下去，if(空节点)return 0)return res,res不断更新left+right+1最大值
- [297. 二叉树的序列化与反序列化](https://leetcode-cn.com/problems/serialize-and-deserialize-binary-tree/)第一步{help(root->left)要实现(不管root是哪个root，从它的左子树下去都能将所有节点变为string)需要做到(从何来，无，怎么下去，直接下去，直到if(无节点)返回)return res，res要不断+=to_string(root->val)+=" "+="# "}第二步{node->left=help(ss),要实现(不管root是哪个root,root->left都能指向ss的一个节点}需要做到(从何来？无。怎么下去？ss>>tmp;return new Node(stoi(tmp));if(tmp=="#")return nullptr;)return root;
- [449. 序列化和反序列化二叉搜索树](https://leetcode-cn.com/problems/serialize-and-deserialize-bst/)同上
- [剑指 Offer 27. 二叉树的镜像](https://leetcode-cn.com/problems/er-cha-shu-de-jing-xiang-lcof/)help(root->left)要实现(不管root是哪个root，从它的左子树下去都能得到镜像)需要做到(swap(root->left,root->right),if(空)return ;)return root;
- [剑指 Offer 26. 树的子结构](https://leetcode-cn.com/problems/shu-de-zi-jie-gou-lcof/) 第一步{bool left=help(A->left,B->left)要实现(不管AB是哪个AB，他们的left都能判断AB左子树是否包含)需要做到(从何来？return left&&right;怎么下去?if(AB值不同)return false;if(A有B没有)return true；if(A没有B有)return false;if(A没B没)return true;}第二步{res=isSameTree(A->left,B)要实现(如果A这个节点不行，换一个节点比较)需要做到(从何来？无。怎么下去？res=isSameTree(A,B),if(res不行)下去}return res;
- [572. 另一个树的子树](https://leetcode-cn.com/problems/subtree-of-another-tree/)同上上，唯一区别是第一步if(A有B没有)return false;
- [1367. 二叉树中的列表](https://leetcode-cn.com/problems/linked-list-in-binary-tree/)同上，唯一区别是从何来？return left||right;
- [	#1382 将二叉搜索树变平衡](https://leetcode-cn.com/problems/balance-a-binary-search-tree/) 第一步{中序遍历将结果保存在vector<int>sort_ok里面}第二步{root->left=help(begin,mid-1)实现(不管root是哪个root，root->left都能指向一个新的中点)需要做到(从何来？return root给个中点节点，怎么下去？每一个节点都要mid=(begin+end)/2,root=new Node(sort_ok[mid])}
- [	#108 将有序数组转换为二叉搜索树](https://leetcode-cn.com/problems/convert-sorted-array-to-binary-search-tree/) 上题第二步已实现
- [	#99 恢复二叉搜索树](https://leetcode-cn.com/problems/recover-binary-search-tree/) 第一步中序遍历得到sort_nums 第二步找到sort_nums中错误的{one,two},第三步{help(root->left) 实现(不管root是哪个root，从这个root左子树下去都能找到一个错误的数并更改)需要做到(从何来？无；怎么下去？if(root->val==其中一个错误的数)更改，if(!root)return;每次--count两次后return强制终止)}
- [	#94 二叉树的中序遍历](https://leetcode-cn.com/problems/binary-tree-inorder-traversal/) 三种做法，递归法最实用，迭代法效率=递归，代码复杂，莫里斯遍历节省空间。Morris{root轨迹就像一把梳子1找到先节点pre_node;2pre_node指向对应root；3root不断向左同时重复就像梳子的手柄12；4此时root在最左，res.push_back(root);(pre_node多次重复1来到该去位置只是为了在跟在root后面恢复恢复nullptr)pre_node=nullptr;root=root-right;不断重复梳子的梳头}
- [	#98 验证二叉搜索树](https://leetcode-cn.com/problems/validate-binary-search-tree/) 中序遍历
- [	#114 二叉树展开为链表](https://leetcode-cn.com/problems/flatten-binary-tree-to-linked-list/) help(root->left) 实现(不管root是哪个root，从左边下去就一定能将所有节点变成右直链)需要做到(从何来？root->right=root->left;root->left=nullptr;提前备份root->right;找最右节点->right=备份,怎么下去？if(!root)return ;
- [	#95 不同的二叉搜索树 II](https://leetcode-cn.com/problems/unique-binary-search-trees-ii/) 复杂递归 TreeNode* left=help(begin,i-1),实现(不管root是哪个root，它的每个left都能保存所有可能的树)需要做到(从何来？tmp_tree=new tree(),all_tree.push_back(tmp_tree)memo[][]保存alltree。return memo[][].怎么下去？每一次return memo[][] if(begin>end)return {nullptr})return memo[][];可以发现从何来和最终答案return操作相同，这说明递归过程和最终要返回的值操作一样但参数不同，如return memo[begin][end]中begin和end在递归中和最终不同，所以才说不会理会递归细节从何来，而要关注如何返回最终值。
- [	#654 最大二叉树](https://leetcode-cn.com/problems/maximum-binary-tree/) root->left=help(begin,max_index) 实现(无论root是哪个root，root->left就一定要是当前最大数左边数形成)需要做到(从何来？由后可知返回new 节点。怎么下去？for寻找max_index，new节点if(begin>end)return nullptr;)return root;
- [	#145 二叉树的后序遍历](https://leetcode-cn.com/problems/binary-tree-postorder-traversal/) 迭代法前序遍历基础上先push左在push右，得到中右左最后reverse得到左右中
- [	#144 二叉树的前序遍历](https://leetcode-cn.com/problems/binary-tree-preorder-traversal/)迭代法stack，每pop就push右再push左
- [	#450 删除二叉搜索树中的节点](https://leetcode-cn.com/problems/delete-node-in-a-bst/) root->left=help(root->left) 实现(无论root是哪个root，root->left都要正好原本是要删除的现在指向删除后的)需要做到(从何来？无，怎么下去？if(root->val<val就走那一条路)if(root->val==val)if(正好只有一个子节点)return 子节点，if(两个子节点)找到root后向节点交换，root->right=(root->right)还需要下去找到交换的删除
- [	#700 二叉搜索树中的搜索](https://leetcode-cn.com/problems/search-in-a-binary-search-tree/) help(root->left) 实现(无论root是哪个root，从他的左子树下去就可能找到对的点并返回)需要做到(从何来？无。怎么下去？if(val<root->val)下哪一条路，if(val==root->val)return root;if(!)return nullptr;
- [#538 把二叉搜索树转换为累加树](https://leetcode-cn.com/problems/convert-bst-to-greater-tree/) 中序遍历，不断更新sum+=root->val，不断root->val=sum,第i个大的节点值等于前i-1个节点值和
- [	#230 二叉搜索树中第K小的元素](https://leetcode-cn.com/problems/kth-smallest-element-in-a-bst/) 中序遍历，不断i++，知道==k就res=root->val并返回
  
一成层序遍历
- [513. 找树左下角的值](https://leetcode-cn.com/problems/find-bottom-left-tree-value/) 层序遍历，i=0时res保存，到最后一层res就是答案
- [429. N叉树的层序遍历](https://leetcode-cn.com/problems/n-ary-tree-level-order-traversal/) 层序遍历，特点是for(auto child:children)q.push(child)
- [	#117 填充每个节点的下一个右侧节点指针 II	](https://leetcode-cn.com/problems/populating-next-right-pointers-in-each-node-ii/) 层序遍历，特点是每pop一个node就pre->next=node;pre再来到node位置
- [	#107 二叉树的层次遍历 II](https://leetcode-cn.com/problems/binary-tree-level-order-traversal-ii/) 层序遍历，最后reverse
- [	#103 二叉树的锯齿形层次遍历](https://leetcode-cn.com/problems/binary-tree-zigzag-level-order-traversal/) 用deque,bool odd表示奇数行，if(odd)不变；if(!odd),pop_back(),push_front而且先push 右再push左
- [	#102 二叉树的层序遍历](https://leetcode-cn.com/problems/binary-tree-level-order-traversal/) 层序遍历
- [	#111 二叉树的最小深度](https://leetcode-cn.com/problems/minimum-depth-of-binary-tree/) 层序遍历，if(叶节点)return depth;

  一成特殊题
- [501. 二叉搜索树中的众数](https://leetcode-cn.com/problems/find-mode-in-binary-search-tree/) 特殊题，unordered_map<int,int>map在中序遍历中用map[root->val]++统计频率,vector<pair<int,int>>vec_sort(map.begin(),map.end())给频率排序，vector<int>res给频率最大几个vec_sort取出return
- [#106 从中序与后序遍历序列构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-inorder-and-postorder-traversal/)精华3代码 root->left=help(ord_begin,ord_root,post_begin,post_begin+left_len)root->right=help(ord_root+1,ord_end,post_begin+left_len+1,post_end-1) left_len=hash_index[post[post_end-1]-ord_begin;
- [	#105 从前序与中序遍历序列构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-preorder-and-inorder-traversal/)精华3代码 root->left=help(pre_begin+1,pre_begin+1+left_len,ord_begin,ord_root)root->right=help(pre_begin+1+left_len,pre_end,ord_root+1,ord_end);left_len=hash_index[pre[pre_begin]]-ord_begin;
- [	#889 根据前序和后序遍历构造二叉树](https://leetcode-cn.com/problems/construct-binary-tree-from-preorder-and-postorder-traversal/) root->left=help(pre_begin+1,pre_begin+1+left_len,post_begin,post_begin+left_len) ;root->right=help(pre_begin+1+left_len,pre_end,post_begin+left_len,post_end-1) int len=hash_index[pre[pre_begin+1]]+1-post_begin;精华三行代码
- [	#96 不同的二叉搜索树](https://leetcode-cn.com/problems/unique-binary-search-trees/) dp[i]+=dp[j]*dp[i-j-1]，有i个节点的树的个数+=有j个节点的左子树个数*有i-j-1个节点的右子树个数
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :cloud: 回溯算法
  排列组合子集题：怎么下去，怎么剪枝
  剪枝3大方法：used[i],不能重复使用同一元素；begin，不能只是换位子。如果begin取得是i+1还可以有used[i]的效果，换句话说begin的前提下如果想重复使用同一个元素就取i，不想就取i+1不用used.nums[i]==nums[i-1]&&!used[i-1]，有重复元素，不能返回重复排列，不能用begin代替used
- [46. 全排列](https://leetcode-cn.com/problems/permutations/) 怎么下去？(下去，if(path.size()==nums.size())res.push_back(path)return;)怎么剪枝？(给123不能还111，if(!used[i]))
- [47. 全排列 II](https://leetcode-cn.com/problems/permutations-ii/) 怎么下去？(if(path.size()==nums.size())res.push_back(path)return;)怎么剪枝？(给112不能还222，if(!used[i]),不能还两个211，if(i>0&&nums[i]==nums[i-1]&&!used[i],)
- [78. 子集](https://leetcode-cn.com/problems/subsets/) 怎么下去？(res.push_back(path))怎么剪枝？(不能给12还12和21，begin,不能给12还11，begin i+1版)
- [90. 子集 II](https://leetcode-cn.com/problems/subsets-ii/)怎么下去？(res.push_back(path))怎么剪枝？(不能给122还112和211begin，不能给112还112和111begin i+1版，不能给122还122和122 nums[i]==nums&&!used[i-1]
- [77. 组合](https://leetcode-cn.com/problems/combinations/) 怎么下去？(if(path.size()==k)res.push_back(path)return)怎么剪枝？(不能12和21begin不能11begin i+1版本)
- [39. 组合总和](https://leetcode-cn.com/problems/combination-sum/)怎么下去？(if(targer==0)res.push_back(path))怎么剪枝？(不能12和21begin可以11begin i版本)
- [40. 组合总和 II](https://leetcode-cn.com/problems/combination-sum-ii/)怎么下去？(if(targer==0)res.push_back(path))怎么剪枝？(不能12和21begin不能111begin i+1,不能112还211和211nums[i]==nums[i-1]&&!used[i-1])
- 以下回溯游戏太难，思路灵活，我也不会
- [79. 单词搜索](https://leetcode-cn.com/problems/word-search/)第一步{forfor从每一个格子出发调用help,help为真就return true否则继续调用}第二步{help(wordIndex,x-1,y)向上，怎么下去？if(board[][]!=word[index])return falseif(index==word.size()到尾了return true,递归前tmp保存board[][]递归后不成立要board[][]=tmp回溯}
- [22. 括号生成](https://leetcode-cn.com/problems/generate-parentheses/) 第一回溯{path.push_back("(")help(left-1,right)path.pop_back()}第二回溯{path.push_back(")")help(left,right-1)path.pop_back()}怎么下去？if(left>right)return;if(left==0||right==0)res.push_back(path)return ;if(left<0||right<0)return;
- [51. N 皇后](https://leetcode-cn.com/problems/n-queens/) 对i行，forj，if(!isValid(board[i][j])return,有效就board[i][j]="Q",help(i+1),board[i][j]="."回溯,怎么下去？(if(i==board.size())res.push_back(board[][])return ;判断是否有效分三步正上方有Q无效，左上方有Q无效，右上方有Q无效。
- [37. 解数独](https://leetcode-cn.com/problems/sudoku-solver/) for fori行j列，if(有数字)return help(i,j+1),否则for(1to9)if(无效)continue;否则board[][]=;if(递归下一列成立)return true;否则board[][]=.回溯。什么时候有效？for上面没有for左边没有forfor九宫格没有就是有效.怎么下去？if(col==9换行，if(row==9找到return true
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :art: 二分查找
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
## :floppy_disk: 贪心算法
- [	#452 用最少数量的箭引爆气球](https://leetcode-cn.com/problems/minimum-number-of-arrows-to-burst-balloons/)
- [#983 最低票价](https://leetcode-cn.com/problems/minimum-cost-for-tickets/)
- [	#55 跳跃游戏](https://leetcode-cn.com/problems/jump-game/)
- [	#435 无重叠区间](https://leetcode-cn.com/problems/non-overlapping-intervals/)
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()
- []()

## :coffee: 待定 
## :bulb: 待定
## :wrench: 待定
## :watermelon: 待定
## :memo: 待定
