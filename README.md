                                               par el archivo.cpp
//============================================================================
// Name        : proyecto_pilas_colas.cpp
// Author      : santigo itzep.
// Version     :
// Copyright   : Your copyright notice
// Description : Hello World in C++, Ansi-style
//============================================================================

#include <iostream>
#include "colas.h"
#include "pilas.h"
using namespace std;

int main() {
	Apilar('j');
	Apilar('k');
	Apilar('a');
	Apilar('s');
	Apilar('ñ');

	show();
	cout<<endl;

	Adesapilar();
	cout<<endl;
	Desapilar();
	cout<<endl;

	Tam ();
	cout<<endl;

Push('x');
cout<<endl;

MostrarT();
cout<<endl;

Top();
cout<<endl;

Pop();
cout<<endl;

MostrarTd();
cout<<endl;

                       para el archivo.h pilas
                       #include <iostream>
#include <stdio.h>
#include <stdlib.h>

using namespace std;

struct pila {
	char D;
	pila * siguiente;
};

pila * iniciar; pila * auxi; pila * final;


void Apilar(char D2){
	if (iniciar==NULL){
		iniciar= new(pila);
		iniciar->D=D2;
		final=iniciar;
	}else{
		auxi=new(pila);
		auxi->siguiente=iniciar;
		auxi->D=D2;
		iniciar=auxi;
	}
	final->siguiente=NULL;
}



void show(){
	auxi= iniciar;
	if(iniciar==NULL){
		cout <<"NO SE HAN APILADO NODOS" << endl;
	}else{
		while (auxi != NULL ){
			cout <<auxi->D<< endl;
			auxi = auxi->siguiente;

	}
}
}

void Adesapilar(){
	auxi= iniciar;
	if(iniciar==NULL){
		cout <<"NO SE HAN APILADO NODOS" << endl;
	}else{
		if(auxi != NULL ){
			cout <<auxi->D<< endl;
		}
	}
}


void Desapilar(){
	struct pila *pant=NULL;
	if (iniciar==NULL){
		cout<<"NO SE HAN APILADO NODOS" << endl;
	}
	else {
		auxi=iniciar;
		iniciar=iniciar->siguiente;
		pant=auxi;
		pant->siguiente=auxi->siguiente;

	}
}

void Tam(){
	int contador=0;
	auxi= iniciar;
	if(iniciar==NULL){
		cout <<"NO SE HAN APILADO NODOS" << endl;
	}else{
		while (auxi != NULL ){
            contador++;
			auxi = auxi->siguiente;
	}
	cout<<"EL NUMERO DE NODOS APILADO SON  "<<contador<<endl;
}
}
                                   para el archivo.h  colas
                                   #include <iostream>
#include <stdio.h>
#include <stdlib.h>
using namespace std;



struct cola {
	char D;
	cola * siguiente;
};

cola * inicio; cola * auxiliar; cola * fin;

void Push(char D2){
	if (inicio==NULL){
		inicio= new(cola);
		inicio->D=D2;
		fin=inicio;
	}else{
		auxiliar=new(cola);
		fin->siguiente=auxiliar;
		auxiliar->D=D2;
		fin=auxiliar;
	}
	fin->siguiente=NULL;
}

void MostrarT(){
	auxiliar= inicio;
	if(inicio==NULL){
		cout <<"NO SE HA INGRESADO NODOS" << endl;
	}else{
		while (auxiliar != NULL ){
			cout <<auxiliar->D<< endl;
			auxiliar = auxiliar->siguiente;

	}
}
}

void Top(){
	auxiliar= inicio;
	if(inicio==NULL){
		cout <<"NO SE HA INGRESADO NODOS" << endl;
	}else{
		if(auxiliar != NULL ){
			cout <<auxiliar->D<< endl;
		}
	}
}

void Pop(){
	struct cola *pant=NULL;
	if (inicio==NULL){
		cout<<"NO SE HA INGRESADO NODOS" << endl;
	}
	else {
		auxiliar=inicio;
		inicio=inicio->siguiente;
		pant=auxiliar;
		pant->siguiente=auxiliar->siguiente;

	}
}

void MostrarTd(){
	int contador=0;
	auxiliar= inicio;
	if(inicio==NULL){
		cout <<"NO SE HA INGRESADO NODOS" << endl;
	}else{
		while (auxiliar != NULL ){
            contador++;

			auxiliar = auxiliar->siguiente;
	}
	cout<<"NODOS INGRESADOS HA LA COLA "<<contador<<endl;
}
}

                                             


	return 0;
}

                                                       // FIN

