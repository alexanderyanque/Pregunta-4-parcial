#include <iostream>
using namespace std;
void creamemoria(int **a,int cols,int fils,int x=0){
    if(x==fils){
        return;
    }
    a[x]=new int[cols];
creamemoria(a,cols,fils,x+1);
return;}
void destruyememoria(int **a,int cols,int fils,int x=0){
    if(x==fils){
        return;
    }
    delete[] a[x];
    destruyememoria(a,cols,fils,x+1);
return;}
void pidevalores(int **a,int x,int y,int fils,int cols){
    if(x==fils){
        return;
    }
    int aux;
    cout<<"Matriz["<<x<<"]["<<y<<"] = ";cin>>aux;
    a[x][y]=aux;
    if (y==cols-1){
    x=x+1;
    y=0;
    }
    else{
        y=y+1;
    }
    pidevalores(a,x,y,fils,cols);
    return;}
void davalores(int **a,int x,int y,int fils,int cols){
    if(x==fils){
        return;
    }
    cout<<"Matriz["<<x<<"]["<<y<<"] = "<<a[x][y]<<endl;
    if (y==cols-1){
    x=x+1;
    y=0;
    }
    else{
        y=y+1;
    }
    davalores(a,x,y,fils,cols);
    return;}

void func_uno   (int **a,int **b,int **c,int x,int y,int fil,int col,int fils=0){
if(x==fil){
    return;
}
int aux=b[x][y];
if (a[x][y]<aux){
    aux=a[x][y];
}
c[x][y]=aux;
if (y==col-1){
    x=x+1;
    y=0;
}
else{
    y=y+1;
}
func_uno(a,b,c,x,y,fil,col);
return;}
void func_dos   (int **a,int **b,int **c,int x,int y,int fil,int col,int fils=0){
if(x==fil){
    return;
}
int aux=b[x][y];
if (a[x][y]>aux){
    aux=a[x][y];
}
c[x][y]=aux;
if (y==col-1){
    x=x+1;
    y=0;
}
else{
    y=y+1;
}
func_uno(a,b,c,x,y,fil,col);
return;}
void func_tres  (int **a,int **b,int **c,int x,int y,int fil,int col,int fils=0){
if(x==fil){
    return;
}
float aux=0;
aux=a[x][y]+b[x][y];
c[x][y]=aux/2;
if (y==col-1){
    x=x+1;
    y=0;
}
else{
    y=y+1;
}
func_uno(a,b,c,x,y,fil,col);
return;}
void func_cuatro(int **a,int **b,int **c,int x,int y,int fil,int col,int fils=0){
if(x==fil){
    return;
}
float aux=0;
aux=a[x][y]+b[x][y];
c[x][y]=aux;
if (y==col-1){
    x=x+1;
    y=0;
}
else{
    y=y+1;
}
func_uno(a,b,c,x,y,fil,col);
return;}
void func_cinco (int **a,int **b,int **c,int x,int y,int fil,int col,int fils=0){
if(x==fil){
    return;
}
float aux=0;
aux=a[x][y]-b[x][y];
c[x][y]=aux;
if (y==col-1){
    x=x+1;
    y=0;
}
else{
    y=y+1;
}
func_uno(a,b,c,x,y,fil,col);
return;}
int multi(int **a,int **b,int x,int y,int v,int fil=0){
    int auxa;
    if(fil==v-1){
        return 0;
    }

    auxa=(a[x][fil])*(b[fil][y]);

return auxa+multi(a,b,x,y,v,fil+1);}

void func_seis  (int **a,int **b,int **c,int x,int y,int fil,int col,int fils){
if(x==fil){
    return;
}
    c[x][y] = (multi(a,b,x,y,fils));
if (y==col-1){
    x=x+1;
    y=0;
}
else{
    y=y+1;
}
return;}


int main()
{
    int fila,filb,filc,cola,colb,colc;
    cout<<"Numero de filas matriz a: ";cin>>fila;
    cout<<"Numero de columnas matriz a: ";cin>>cola;
    cout<<"Numero de filas matriz b: ";cin>>filb;
    cout<<"Numero de columnas matriz b: ";cin>>colb;
    if(fila==filb and cola==colb){
        filc=fila;
        colc=cola;
    }
    else if(filb=cola){
        filc=fila;
        colc=colb;
    }
    int **a,**b,**c;
    a = new int* [fila];
    b = new int* [filb];
    c = new int* [filc];
    creamemoria(a,cola,fila);
    creamemoria(b,colb,filb);
    creamemoria(c,colc,filc);
    cout<<endl<<"<<--Matriz A-->>"<<endl<<endl;
    pidevalores(a,0,0,fila,cola);
    cout<<endl<<"<<--Matriz B-->>"<<endl<<endl;
    pidevalores(b,0,0,filb,colb);
    int adsad=0;
    void (*puntero)(int**,int**,int**,int,int,int,int,int);
    cout<<" ¿ Que hago ? "<<endl;
    cout<<"1.-numero menor"<<endl;
    cout<<"2.-numero mayor"<<endl;
    cout<<"3.-promedio"<<endl;
    cout<<"4.-suma"<<endl;
    cout<<"5.-resta"<<endl;
    cout<<"6.-multiplicacion"<<endl;
    cin>>adsad;
    switch(adsad){
    case(1):{
        puntero=func_uno;
    break;}
    case(2):{
        puntero=func_dos;
    break;}
    case(3):{
        puntero=func_tres;
    break;}
    case(4):{
        puntero=func_cuatro;
    break;}
    case(5):{
        puntero=func_cinco;
    break;}
    case(6):{
        puntero=func_seis;
    break;}
    }
    puntero(a,b,c,0,0,fila,colb,cola);

    cout<<endl<<"<<--Resultado-->>"<<endl<<endl;
    davalores(c,0,0,filc,colc);
    destruyememoria(a,cola,fila);
    destruyememoria(b,colb,filb);
    destruyememoria(c,colc,filc);
    delete[] a;
    delete[] b;
    delete[] c;

    return 0;
}
