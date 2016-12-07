# EMBEBIDOS
SUMA,PROM,MULT
#include "datos.h"

int i=0;     
int j=0;
int suma;
double total;
double multi=1;
double prom;

void setup() {
pinMode(2,INPUT); // puerto 2 como entrada
pinMode(3,INPUT);  // puerto 3 como entrada
pinMode(4,INPUT);  // puerto 4 como entrada
Serial.begin(9600); // inicilizo la cx serial
}

void loop() {
 //Suma
if(digitalRead(2)==HIGH) // verifico si el puerto 2 esta en HIGH
{
for(;i<20;i++) // recorre filas
{
  for(;j<3;j++) //recorre columnas
{
  suma=suma+matriz[i][j]; // almaceno la suma de cada fila
}
Serial.print("La suma es igual a "); // imprimir mjs 
Serial.println(suma); // imprimo el valor de la variable suma
delay(1000); // espero un segundo 
j=0; // encero la variable j
suma=0; // encero la variable suma
}
}
if(digitalRead(2)==LOW) //verifico si el puerto 2 esta en LOW
{
 i=0; 
 j=0; 
}


// Multiplicacion
if(digitalRead(3)==HIGH) //  verifico si el puerto 3 esta en HIGH
{
for(;i<3;i++) // recorro columnas
{
  for(;j<10;j++) // recorro filas
{
  multi=multi*matriz[j][i]; // almaceno en la variable
}
Serial.println("La multiplicacion es igual a "); // imprimo el mjs entre comillas 
Serial.println(multi);// imprimo el valor de la variable suma
delay(1000); // tiempo de espera
j=0; //encero la variable j
multi=1; //asigno valor de uno a la variable multi
}
}
if(digitalRead(3)==LOW) //verifico si el puerto 3 esta en LOW
{
 i=0;
 j=0; 
}

// Promedio
if(digitalRead(4)==HIGH) // verifico si el puerto 4 esta en HIGH
{
for(;i<3;i++) // recorre columnas
{
  for(;j<20;j++) // recorre filas
{
  total=total+matriz[j][i];// almaceno en la variable
}
j=0; //encero j
}
prom=(total/3); // obtengo el promedio 
Serial.println("El promedio es");// imprimo el mensaje
Serial.println(prom);// imprimo el valor de suma
delay(1000); // tiempo de espera
total=0; // encera total
}
if(digitalRead(2)==LOW) // verifico si el puerto 4 esta en LOW
{
 i=0;
 j=0; 
}

}
