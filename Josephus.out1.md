 # # include <stdio.h><br>
 # # include <stdlib.h><br>
<br>
typedef struct List{<br>
	int data;<br>
	struct List* next;<br>
}Node;<br>
/*<br>
Node *Head(){<br>
	Node *head=(Node*)malloc(sizeof(Node));<br>
	head->data=1;<br>
	head->next=NULL;<br>
	return head;<br>
}<br>
*/<br>
Node *create_node(int data){<br>
	Node*node=(Node*)malloc(sizeof(Node));<br>
	node->data=data;<br>
	node->next=NULL;<br>
	return node;<br>
}<br>
int main(){<br>
	Node *head=(Node*)malloc(sizeof(Node));<br>
	head->data=1;<br>
	head->next=NULL;<br>
	Node*p=head;<br>
	int data1,data2,data3;<br>
	char ch;<br>
	int running=1;<br>
	while(running){<br>
		scanf(" %c",&ch);//跳过空白字节 <br>
		switch(ch){<br>
			case'H':<br>
				{<br>
				Node*t=NULL;<br>
				scanf("%d%d%d",&data1,&data2,&data3);<br>
				t=head;<br>
				head=create_node(data1);<br>
				head->next=create_node(data2);<br>
				head->next->next=create_node(data3);<br>
				head->next->next->next=t;<br>
				}<br>
				break;<br>
			case'T':<br>
				{<br>
				p=head;<br>
				while(p->next!=NULL){<br>
					p=p->next;<br>
				}<br>
				scanf("%d%d%d",&data1,&data2,&data3);<br>
				p->next=create_node(data1);<br>
				p=p->next;<br>
				p->next=create_node(data2);<br>
				p=p->next;<br>
				p->next=create_node(data3);<br>
				p=p->next;		<br>
				}<br>
				break;<br>
			case'C':<br>
				{<br>
				p=head;<br>
				while(p->next!=NULL){<br>
					p=p->next;<br>
				}<br>
				p->next=head;<br>
				}<br>
				break;<br>
			case'D'://头为1 <br>
				{ <br>
				int LOCATION;<br>
				int i;<br>
				Node*pre=NULL;<br>
				scanf("%d",&LOCATION);<br>
				if(head==NULL){<br>
					printf("list is empty"); <br>
				} else if(head->next==NULL){<br>
					p=head;<br>
					printf("%d\n",p->data);<br>
					free(p);<br>
				}else if(head!=NULL&&head->next!=NULL){<br>
					p=head;<br>
					if(LOCATION!=1){<br>
					for(i=1;i<LOCATION;i++){//当LOCATION输入1，2时会崩溃 <br>
						if(p->next==NULL){<br>
							pre=p; <br>
							break;//注意此时pre为NULL<br>
							//当退出时会有访问pre的行为 <br>
						}else if(LOCATION!=1){<br>
							pre=p;<br>
							p=p->next;<br>
						}<br>
						}<br>
						pre->next=p->next;<br>
						printf("%d\n",p->data);<br>
						free(p);<br>
					}else if(LOCATION==1){<br>
						head=head->next;<br>
						printf("%d\n",p->data);<br>
						free(p);<br>
					}<br>
					}<br>
				} <br>
				break;<br>
			case'B':<br>
				{<br>
				int m,u;<br>
				Node*temp,*r;<br>
				p=head;<br>
				while(p->data!=3){<br>
					temp=p;<br>
					p=p->next;<br>
				}<br>
				p=temp;<br>
				while(p!=NULL){<br>
					m=1;<br>
					for(u=0;u<m;u++){<br>
							r=p;	<br>
							p=p->next;<br>
						}<br>
					r->next=p->next;	<br>
					printf("%d",p->data);<br>
					free(p);<br>
					p=r->next;<br>
					m++;	<br>
				}<br>
				break;<br>
			default:<br>
				{<br>
				printf("Invaild grade\n");<br>
				running=0;<br>
				}<br>
				break;<br>
			}	<br>
		}<br>
	p=head;<br>
	while(p!=NULL){<br>
		p=p->next;<br>
		printf("%d",p->next);<br>
	}<br>
	return 0;<br>
}<br>
}