sing namespace std;

typedef struct TNode { 
int data;   
TNode *next;
};
TNode *head;  

void init(){ 
head=NULL; 
}

int periksaKosong(){ 
if(head==NULL)  
return 1;
else
return 0; 
}

void masukDepan(int n){
TNode *lagi; 
lagi=new TNode; 
lagi->data=n;  
lagi->next=NULL;  
if(periksaKosong()==1){
head=lagi;
head->next=NULL;
}
else {
lagi->next=head;
head=lagi;
}
cout<<"Data Terisi";
}

void masukBelakang(int n){    
TNode *lagi,*help; 
lagi=new TNode;
lagi->data=n;
lagi->next=NULL;
if(periksaKosong()==1){
head=lagi;
head->next=NULL;
}
else {
help=head;
while(help->next!=NULL){
help=help->next;
}
help->next=lagi;

}
cout<<"Data Terisi";
}

void tampil(){   
TNode *help; 
help=head; 
if(periksaKosong()==0){  
while(help!=NULL){
cout<<help->data<<endl;  
help=help->next; 
}
}
else
cout<<"Masih Kosong"<<endl;
}

void bersihiDepan(){ 
TNode *hapus;
int d;
if(periksaKosong()==0){ 
if(head!=NULL){ 
hapus=head;
d=hapus->data;
head=hapus->next;
delete hapus;  
cout<<d<<"Terhapus"<<endl;
}
else
cout<<"Masih Kosong"<<endl;
}

main(){  // Fungsi Utama dari program
int pil;
do{
system("CLS");
int n;
cout<<"1.Masukkan Data di Depan"<<endl;
cout<<"2.Masukkan Data di Belakang"<<endl;
cout<<"3.Tunjukkan Datanya"<<endl;
cout<<"4.Hapus Datanya"<<endl;
cout<<"5.Keluar dari Program"<<endl;
cout<<"Masukan Pilihan Anda :";pil=getche();
switch(pil){
case'1': system("CLS");
cout<<"Masukan data :";cin>>n;
periksaKosong();
masukDepan(n);
break;
case'2': system("CLS");
cout<<"Masukan data :";cin>>n;
periksaKosong();
masukBelakang(n);
break;
case'3': system("CLS");
periksaKosong();
tampil();
break;
case'4': system("CLS");
periksaKosong();
bersihiDepan();
break;
}
getch();
}while(pil!='5');
return 0;
}

