# data-structure-#include <stdio.h>
#define MAX 5

int queue[MAX];
int front = -1, rear = -1;

// Enqueue
void enqueue(int x)
{
    if (rear == MAX - 1)
    {
        printf("The Q is FULL!!\n");
    }
    else
    {
        if (front == -1)
            front = 0;

        rear++;
        queue[rear] = x;
        printf("%d has been queued!\n", x);
    }
}

int dequeue()
{
    if (front == -1 || front > rear)
    {
        printf("The Q is Empty!!\n");
        front = rear = -1;
        return -1;
    }
    else
    {
        int x = queue[front];
        front++;

        printf("%d has been dequeued!\n", x);

        if (front > rear)
        {
            front = rear = -1;
        }

        return x;
    }
}

int main()
{
    enqueue(10);
    enqueue(20);
    enqueue(30);
    enqueue(40);
    enqueue(50);
    enqueue(60);   // Queue is full

    dequeue();
    dequeue();
    dequeue();
    dequeue();
    dequeue();
    dequeue();     // Queue is empty

    return 0;
}
