#include<stdio.h>
 #include<stdlib.h>
 #include<malloc.h>
 struct node
 {
     int data;
     struct node *next;
 }
 *head=NULL,*p,*t,*newnode;
 void create()
 {
     int n,i,ele;
     printf("enter n");
     scanf("%d",&n);
     for(i=0;i<n;i++)
     {
         printf("enter the elements");
         scanf("%d",&ele);
         newnode=(struct node*)malloc(sizeof(struct node));
         newnode->data=ele;
         newnode->next=NULL;
     if(head==NULL)
     {
         head=newnode;
         p=newnode;
     }
     else
     {
         for(p=head;p->next!=NULL;p=p->next);
         p->next=newnode;
         p=newnode;
     }
 }
 }
 void display()
     {
         if(head==NULL)
         printf("linked list is empty");
         else
         for(p=head;p!=NULL;p=p->next)
         printf("%d",p->data);
     }
      void insert_at_begin()
     {
         int ele;
         printf("enter the element");
         scanf("%d",&ele);
         newnode=(struct node*)malloc(sizeof(struct node));
         newnode->data=ele;
         newnode->next=NULL;
         p=head;
         head=newnode;
         newnode->next=p;
         p=newnode;
      }
      void insert_at_end()
     {
         int ele;
         printf("enter the element");
         scanf("%d",&ele);
         newnode=(struct node*)malloc(sizeof(struct node));
         newnode->data=ele;
         newnode->next=NULL;
         for(p=head;p->next!=NULL;p=p->next);
         p->next=newnode;
         p=newnode;
     }
     void insert_at_anyposition()
      {
          int ele,i,pos;
          printf("enter the element");
          scanf("%d",&ele);
          newnode=(struct node*)malloc(sizeof(struct node));
          newnode->data=ele;
          newnode->next=NULL;
          printf("enter the position");
          scanf("%d",&pos);
          for(p=head,i=1;i<pos;p=p->next,i++)
          t=p;
          t->next=newnode;
          newnode->next=p;
          p=newnode;
       }
       void delete_at_end()
      {
          for(p=head;p->next!=NULL;p=p->next)
          t=p;
          t->next=NULL;
          free(p);
          p=t;
          printf("the end element is deleted");
      }
      void delete_at_begin()
     {
         p=head;
         head=p->next;
         free(p);
         p=head;
         printf("the first element is deleted");
     }
     void delete_at_anyposition()
      {
          int i,pos;
          printf("enter the position");
          scanf("%d",&pos);
          for(p=head,i=1;i<pos;i++,p=p->next)
          t=p;
          t->next=p->next;
          free(p);
          p=t;
          printf("the element is deleted");
      }
      void linear_search()
      {
          int i,key,pos,flag=0;
          printf("enter the key");
          scanf("%d",&key);
          for(i=1,p=head;p->next!=NULL;i++,p=p->next)
          {
              if(p->data==key)
              {
                  pos=i;
                  flag=1;
                  break;
              }
          }
          if(flag==1)
          printf("the key element found at position is%d",pos);
          else
          printf("the key element is not found");
      }
     int main()
     {
         int cho;
         do
         {
             printf("\n*main menu*\n");
             printf("1.create\n 2.display\n 3.insert_at _begin\n 4.insert_at_end 5.insert_at_anyposition 6.delete_at_end 7.delete_at_begin 8.delete_at_anyposition 9.linear_search");
             printf("enter the operation");
             scanf("%d",&cho);
             switch(cho)
             {
                 case 1:create();break;
                 case 2:display();break;
                 case 3:insert_at_begin();break;
                 case 4:insert_at_end();break;
                 case 5:insert_at_anyposition();break;
                 case 6:delete_at_end();break;
                 case 7:delete_at_begin();break;
                 case 8:delete_at_anyposition();break;
                 case 9:linear_search();break;
                 default:
                 printf("enter 1 to 5");
             }
         }
         while(cho>=1 && cho<=9);
         return 0;
     }
