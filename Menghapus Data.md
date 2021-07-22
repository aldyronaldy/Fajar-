Hapus Belakang
void hapusBelakang(){
 TNode *hapus,*bantu;
 int d;
 if (isEmpty()==0){
  if(head->next != NULL){
  bantu = head;
  while(bantu->next->next!=NULL){   
    bantu = bantu->next;
  }
  hapus = bantu->next;
  d = hapus->data;
        bantu->next = NULL;
  delete hapus;
  } else {
  d = head->data;
  head = NULL;
  }
  cout<<d<<" terhapus\n";
 } else cout<<"Masih kosong\n";
}
