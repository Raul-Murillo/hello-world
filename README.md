# hello-world

## Raúl Isaí Murillo Alemán  100
## Carrera - ITC

## Christopher Gabriel Pedraza Pohlenz
## Carrara - ITC

**bold text**

*italicized text*

> blockquote
>
1. First item
2. Second item
3. Third item

- First item
- Second item
- Third item

`code`

---

[title](https://www.example.com)

![alt text](image.jpg)

| Syntax | Description |
| ----------- | ----------- |
| Header | Title |
| Paragraph | Text |

```c++
#include <iostream>
#include<stdlib.h>
#include<time.h>
#include<math.h>
using namespace std;

void numeroMágico(){
//Análisis
  //Datos de entrada: "nnum" que es el número que se solicita ingresar
  //Datos de salida: "num" que es el número generado y intentos que registra los intentos del usuario.
  //Procesos: una vez se genere  un número aleatorio entre 1 y 100, se le solicita al usaurio ingresar un número entre el mismo rango, a lo que el programa verifica que ambos número sean distintos y, si es el caso: imprime si el número mágico es más o menos y suma un intento en la varuiable "intentos "para volver a solicitar otro número, una vez que se ingrese el mismo número: imprime el número mágico y la cantidad de intentos del usuario
//Algoritmo general
  //Declaración de variables
int num,nnum,intentos{0};
  //Leer datos de entrada
srand(time(NULL));
num = 1 + rand()%(101-1);
cout << "Ingrese un número entre 1 y 100" << endl;
do{
cin >> nnum;
  //Calcular
  if (nnum < num)
cout << "MÁS" << endl;
  else if(nnum > num)
cout << "MENOS" << endl;
intentos = intentos + 1;
}
while(nnum != num);
  //Desplegar
cout << "Acertaste con el valor mágico " << num << " después de " << intentos << " intentos" << endl;
}

void conversionesCelsiusFarenheit(){
//Análisis
  //Datos de entrada: "C" para los grados Celsius, "conversiones" como la cantidad de conversiones que se realizarán e "incremento" para saber que tanto van aumentando los grados Velsius.
  //Datos de salida: la matriz con los valores de "C" y "F"
  //Procesos: se ingresan los grados Celsius, la cantidad de converiones que se realizarán y los incrementos entre cada grado, después se va llevando una matrzi llamada "Grados" con los valores de "F" y "C" mientras va realizando las converiones de "F" a "F" y los aumentos de "C" para devolver la matriz al final.
//Algoritmo general
  //Declaración de variables
int C,conversiones,incremento;
float F, Grados[conversiones][2];
string encabezado[1][2]={{" FARENHEIT "," CELSIUS "}};
  //Leer datos de entrada
cout << "Ingrese el valor inicial en grados Celsius:" << endl;
cin >> C;
cout << "Inngrese el número de conversiones que se harán:" << endl;
cin >> conversiones;
cout<<"Ingrese el incremento entre los valores Celsius:"<<endl;
cin >> incremento;
  //Calcular
for (int i = 0; i<conversiones ; i++){
  F = (9.0/5.0) * C + 32;
  for(int j = 0; j<2 ;j++){
    if (j == 0)
      Grados[i][j] = F;
    else if (j == 1)
      Grados[i][j] = C;
  }
  C = C + incremento;
}
  //Desplegar
cout << "Conversión de grados Celsius a Farenheit" << endl;
for (int i = 0; i<1 ; i++){
  for(int j = 0; j<2 ;j++){
    cout << encabezado[i][j];
  }
  cout << "\n";
}
for (int i = 0; i<conversiones ; i++){
  for(int j = 0; j<2 ;j++){
    cout << "    " << Grados[i][j] << "    ";
  }
  cout << "\n";
}
}

void serieAritmetica(){
//Análisis
  //Datos de entrada: no hay datos que se le soliciten al usuario, pero se tiene "a" con un valor de 1, "d" con un valor de 3 y "n" con un valor de 25.
  //Datos de salida: el número de la ubicación en la que va de la serie como "i", el número en esa posición "serie" y al final la suma de todos los términos "V".
  //Proceso: Inicia mostrando el valor inicial de la serie en el término "0", el cual es 1 y mientras "i" se mantenga menor que "n": irá sumando el término en la variable "V", aumentando el valor de "i" en 1 y actualizando el valor de "serie" para ir mostrando cada término y al finalizar mostrar la sumatoria de todos los términos.
//Algoritmo general
  //Declaración de variables
int a=1,d=3,n=25,serie=1,i=0,V=0;
  //Calcular y Desplegar
do{
cout << "Término " << i << ": " << serie << endl;
V = V + serie;
i = i + 1;
serie = a + i * d;
}
while(i < n);
cout << "Valor total de la serie:" << V << endl;
}

void mediasGeometricasArmonica(){
//Análisis
  //Datos de entrada: "xi" como el número que se va ingresando
  //Datos de salida: "mg" como la media geométrica y "ma" como la media armónica
  //Procesos: se solicita ingresar un número, si el número es diferente de 0 se almacena la multiplicación del número en "m" y la suma del valor entre 1 en "d" a la vez que el contador "n" aumenta en una unidad, pero si el valor ingresado es 0 el código procede a calcular "mg" usando el número en "m" elevado a 1/"n" y calculando "ma" dividiendo "n" entre la suma de "d".
//Algoritmo general
  //Declaración de variables
double xi=0,mg=0,ma=0,m=1,d=0,n=0;
  //Leer datos de entrada y Calcular
do{
  cout << "Ingrese un número diferente de 0: " << endl;
  cin >> xi;
  if (xi != 0){
    m = m * xi;
    d = d + (1/xi);
    n = n + 1;
  }
}
while(xi != 0);
mg = pow(m,1/n);
ma = n/d;
  //Desplegar
cout << "La media geométrica es: " << mg << endl;
cout << "La media armónica es: " << ma << endl;
}

int menu(){
  int opcion;
  cout<<"Menú de opciones"<<
  "\n1. Número Mágico"<<
  "\n2. Conversiones Celsius-Farenheit"<<
  "\n3. Serie aritmética"<<
  "\n4. Medias geométrica armonica"<<
  "\n0. Salir"<<
  "\nTeclea la opción: ";
  cin>>opcion;
  return opcion;
}

int main() {
  int opcion;
  do{
    opcion = menu();
    switch (opcion){
      case 0:
        cout<<"Gracias por usar el programa\n";
        break;
      case 1:
        numeroMágico();
        break;
      case 2:
        conversionesCelsiusFarenheit();
        break;
      case 3:
        serieAritmetica();
        break;
      case 4:
        mediasGeometricasArmonica();
        break;
      default:
        cout<<"Opción incorrecta\n";
        break;
    }
  }
  while (opcion != 0);

  return 0;
}
```
Here's a sentence with a footnote. [^1]

[^1]: This is the footnote.

### My Great Heading {#custom-id}

term
: definition

~~The world is flat.~~

- [x] Write the press release
- [ ] Update the website
- [ ] Contact the media
