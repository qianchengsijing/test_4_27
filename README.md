# test_4_27
#include <stdio.h>
//队列的顺序存储
//第一种方案（判断队列空/满）
#define MaxSize 10//定义队列最大元素个数
typedef struct
{
	ElemType data[MaxSize];//用静态数组存放队列元素
	int front,rear;
}SqQueue;
//初始化(队尾指针指向最后一个元素下一个可插入位置）
void InitQueue(SqQueue &Q)
{
	Q.front = Q.rear = 0;
}
//判空
bool QueueEmpty(SqQueue Q)
{
	if(Q.front == Q.rear)
		return true;
	else
		return false;
}
//入队
bool EnQueue(SqQueue &Q,ElemType x)
{
	if((Q.rear+1)%MaxSize == Q.front)//判满
		return false;
	Q.data[Q.rear] = x;
	Q.rear = (Q.rear+1)%MaxSize;
	return true;
}
//出队
bool DeQueue(SqQueue &Q,ElemType &x)
{
	if(Q.rear == Q.front)//判空
		return false;
	x = Q.data[Q.front];
	Q.front = (Q.front+1)%MaxSize;
	return true;
}
//查找访问队头元素
bool GetHead(SqQueue Q,ElemType &x)
{
	if(Q.rear == Q.front)//判空
		return false;
	x = Q.data[Q.front];
	return true;
}
//第二种方案
#define MaxSize 10
{
	ElemType data[MaxSize];
	int front,rear;
	int size;//定义一个数据成员记录队列长度
}SqQueue;
//初始化
void InitQueue(SqQueue &Q)
{
	Q.front = Q.rear = 0;
	int size = 0;
}
//第三种方案
#define MaxSize 10
{
	ElemType data[MaxSize];
	int front,rear;
	int tag;//定义一个数据成员标记;tag = 0/1标记队空/满
}SqQueue;
void InitQueue(SqQueue &Q)
{
	Q.front = Q.rear = 0;
	int tag = 0;
}
//初始化(队尾指针指向最后一个元素）
void InitQueue(SqQueue &Q)
{
	Q.front = 0; 
    Q.rear = -1;
}
//判空
bool QueueEmpty(SqQueue Q)
{
	if((Q.rear+1)%MaxSize == Q.front)
		return true;
	else
		return false;
}
//入队
bool EnQueue(SqQueue &Q,ElemType x)
{
	if((Q.rear+2)%MaxSize == Q.front)//判满
		return false;
	Q.rear = (Q.rear+1)%MaxSize;
	Q.data[Q.rear] = x;
	return true;
}
//出队
bool DeQueue(SqQueue &Q,ElemType &x)
{
	if((Q.rear+1)%MaxSize == Q.front)//判空
		return false;
	x = Q.data[Q.front];
	Q.front = (Q.front+1)%MaxSize;
	return true;
}
void testQueue()
{
	SqQueue Q;
	InitQueue(Q);
	EnQueue(&Q,x);
	DeQueue(&Q,&x);
	GetHead(Q,&x);
	QueueEmpty(Q);
}
