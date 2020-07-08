选择题
C D

简答题
1、请简述 patchVnode 函数的执行过程。


首先触发钩子函数：prepatch和updata

其次判断：
1:新、老节点都有text属性，并不相等 ==》老节点有children属性，调用 removeVnodes 移除children 。设置新节点对应的textContent

2:新、老节点都有children属性，并不相等 ==》调用updateChildren,对比子节点并更新差异

3:只有新节点有children属性 ==》如老节点有text，则清空textContent,然后调用addVnodes添加新节点的子节点

4:只有老节点有children属性 ==》移除老节点

5:只有老节点有text属性 ==》清空对应的textContent

最后触发postpatch钩子函数
