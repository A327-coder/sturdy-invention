#include<iostream>
#include<cstdio>
using namespace std;

typedef struct node {
	int data;
	struct node* next;
}node,*linklist;

linklist init(linklist &l) {
	l = (node*)malloc(sizeof(node));
	l->data = -1;
	l->next = NULL;
	return l;
}

void insert(linklist& l, int data) {
	node* p = (node*)malloc(sizeof(node));
	p->data = data;
	p->next = NULL;

	p->next = l->next;
	l->next = p;
}

void print_list(linklist& l) {
	node* p = l;
	p =p ->next;
	while (p != NULL) {
		cout << p->data << "";
		p = p->next;
	}

}

int main() {
	linklist list;
	list = init(list);



	for (int i = 1; i <= 5; i++) {
		insert(list, i);
	}
	print_list(list);
	return 0;
}
