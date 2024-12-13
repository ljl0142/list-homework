2.most fruit
每个果农拥有若干块大小相同的地，每块地都种了水果。请从中找出种植最多的那种水果。

输入说明：
（1）输入多个果农的种植情况，以0作为最终的结束。
（2）每个果农若干行，第一行为耕地数目n，后续n行分别为每块地种植的水果。
（3）水果名称不超过20个字母

输出说明：
输出最多的水果是什么(数量相等情况下，按出现顺序输出)

样例输入：
5
peach
apple
banana
apple
apple
3
pear
orange
pear
1
pear
0

样例输出：
apple
pear


3.list combination
给定 2 个单向链表L1，L2，其中链表的长度分别是n1，n2。每个链表中的数据已经按照从小到大排列好，现在要求将两个链表进行合并，并保证合并后的链表中的数据仍然保持从小到大排列。
输入说明：
第一行：n1 n2 （1≤n1≤1000，1≤n2≤1000）
第二行：n1个非负整数，用空格隔开
第三行：n2个非负整数，用空格隔开

输出说明：
合并后的链表数据，用空格隔开。

例如输入：
3 5
3 7 11
2 8 9 12 16 

输出：
2 3 7 8 9 11 12 16


4.delete the duplication
完成代码中的函数，实现下面的功能：
读入若干正整数，以“-1”作为读入结束标记，去除其中重复的数后，在一行中输出剩余的数，数之间用空格分隔。
例如：
输入：
5 2 3 1 3 4 2 -1
输出：
5 2 3 1 4

说明：
（1）用单链表实现数据的存储。
单链表的节点类型是：
struct Node{
  int content;
  Node * next;
};
（2）只需要实现file1.cpp中的4个函数，其功能可以用于下面的main函数调用。

#include "file1.h"
int main()
{    Node * head;
     head = input();  // 读入整数，用单链表存储
     deduplicate(head); // 去除重复整数
     output(head);  // 输出链表中的整数
     remove(head);  // 撤销链表
     return 0;
}
file1.h文件的内容如下：

#ifndef FILE1_H
#define FILE1_H
#include <iostream>
using namespace std;
#endif
struct Node{
  int content;
  Node * next;
};
Node * input();
void deduplicate(Node * head);
void output(Node * head);
void remove(Node * head);


5.antisort
给定一个单链表的头节点head，实现调整单链表局部节点，使得每K个节点之间逆序，如果最后节点不够K个一组，则不调整。
例如：
输入：
 1->2->3->4->5->6->7->8->-1
 3

 输入说明：
 （1）第一行输入单链表，节点存储的是正整数,-1表示输入结束；
 （2）第二行输入K的值。

输出：
 3->2->1->6->5->4->7->8

输出说明：
（1） 7、8不调整，因为不够一组。
（2）输出形式和输入形式一样，两个整数之间用“->”分隔。

file1.h的内容如下：

#ifndef FILE1_H
#define FILE1_H
#include <iostream>
using namespace std;
#endif
struct Node{
  int content;
  Node* next;
};
Node* input();
Node* reverseK(Node* head,int k);
void output(Node* head);
void remove(Node* head);
你需要实现file1.cpp中的4个函数，以用于下面的main函数调用。

#include "file1.h"
using namespace std;
int main()
{
    Node * head = input();
    int k;
    cin>>k;
    Node* newhead = reverseK(head,k); 
    output(newhead);
    remove(head);
    remove(newhead);
    return 0;
}
