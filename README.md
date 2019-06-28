#include<stdio.h>
#include<stdlib.h>
 struct node
{

    int data;
    struct node *next;

};
struct node* create(int);
void display(struct node*);
void sorter_list_function(struct node*);
void duplicate_data(struct node*);
void main()
{
    int n;
    struct node  *head=NULL;
    int data_s;
    printf("enter the value of n \n");
    scanf("%d",&n);
    head=create(n);
    printf("\n our unsorted linked list \n");
    display(head);
    sorter_list_function(head);
    printf("\n our sorted of linked list\n");
    display(head);
    duplicate_data(head);
    printf("\n after removing our duplicate data our linked list look like as follows\n");
    display(head);
    getch();
}
void sorter_list_function(struct node *head)
{
       struct node *p=head,*i,*j;
       int temp;
       for(i=p;i->next!=NULL;i=i->next)
       {
                                       for(j=i->next;j!=NULL;j=j->next)
                                       {
                                                                       if(i->data > j->data)
                                                                       {
                                                                                           temp=i->data;
                                                                                           i->data=j->data;
                                                                                           j->data=temp;
                                                                                           }
                                                                                           }
                                                                                           }
                                                                                           }
                                        
       

struct node* create(int m)
{
    struct node  *temp,  *p, *head=NULL;
    int i;
    for(i=0;i<m;i++)
    {

        temp=(struct node*)malloc(sizeof(struct node));
        printf("enter the data to your nodes\n");
        scanf("%d",&temp->data);
        temp->next=NULL;
        if(head==NULL)
        {
            head=temp;
        }
        else
        {
            p=head;
            while(p->next!=NULL)
            {
                  p=p->next;
                  }       
            p->next=temp;
            
        }
        
    }
    
return head;
}
void duplicate_data(struct node *head)
{
    struct node *p=head,*q;
    while(p!=NULL && p->next!=NULL)
    {
                  if(p->data==p->next->data)
                  {
                                            q=p->next->next;
                                            if(q==NULL)
                                            {
                                                       p->next=NULL;
                                                       break;
                                                       }
                                                       p->next=q;
                                                       }
                                                       if(p->data!=p->next->data)
                                                       p=p->next;
                                                       }
                                                       }
                                                 
    

void display(struct node  *head)
{
    struct node  *p=head;
    
    while(p!=NULL)  // while(p->next!=NULL) because of these the last data would not print
    {
        printf("%4d-->",p->data);
        p=p->next;
    }
}
