### 1487.Making-File-Names-Unique

基本的策略是：对于当前的name，我们首先查看name是否以前出现过（用一个Set），如果出现过的话再查看name(1)是否出现过，再看name(2)是否出现过...以此类推，直到name(k)没有出现过，那么就作为正式的名字。实现这个功能的数据结构非常简单，就是以name为key建立一个Hash表，value就是0,1,2,... ```Map[name] == i```就说明name(i)曾经出现过。当然，特例是```Map[name] == 0```的话说明name曾经出现过（没有后缀）。每加入一个新的文件名之后，记得要更新Set和```Map[name]```。