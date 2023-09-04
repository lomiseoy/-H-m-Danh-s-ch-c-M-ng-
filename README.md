#include <conio.h>
#include <stdio.h>
#define Maxlength 30
//Khai bao danh sach dat
typedef int ElementType;
typedef int Position;
typedef struct {
        ElementType Elements[Maxlength];
        Position Last;
}
        List;
//Tao danh sach rong
void MakeNull_List (List *L){
     L->Last=0;
}
//Kiem tra danh sach rong
int Empty_List(List L){
    return (L.Last==0);
}
//Kiem tra danh sach day
int Full_List(List L){
    return (L.Last==Maxlength);
}
//Tra ve phan tu dau tien
Position FirstList(List L){
         return 1;
}
//Tra ve vi tri sau phan tu cuoi
Position EndList(List L){
         return L.Last+1;
}
//Tra ve phan tu ke tiep vi tri phan tu P trong danh sach L
Position Next(Position P, List L){
         return P+1;
}
//Tra ve phan tu truoc vi tri phan tu P trong danh sach L
Position Previous(Position P, List L){
         return P-1;
}
//Ham tra ve noi dung phan tu tai vi tri P trong danh sach L
ElementType Retrieve(Position P, List L){
            return L.Elements[P-1];
}
//Them phan tu co noi dung X vao tai vi tri P trong danh sach L
void Insert_List(ElementType X, Position P, List *L){
     int i=0;
     if (L->Last==Maxlength)
        printf(“\nDanh sach day!”);
     else if ((P<1) || (P>L->Last+1))
          printf(“\nVi tri khong hop le!”);
          else {
               for (i=L->Last; i>=P; i–)
               L->Elements[i] = L->Elements[i-1];
               L->Last++;
               L->Elements[P-1]=X;
          }
}
