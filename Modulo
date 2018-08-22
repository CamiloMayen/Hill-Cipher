# -*- coding: cp1252 -*-
#Módulo de definiciones HILL CIPHER
#Universidad del Valle de Guatemala
#Grupo FÍSICOS DISCRETOS
##31/05/2018

from numpy import *
from numpy.linalg import inv
import random

letras = ["a","b","c","d","e","f","g","h","i","j", "k","l","m","n","o","p","q","r","s","t","u","v","w","x","y","z","!","?"," "]
cad  =   [ 1,  2,  3,  4,  5,  6,  7,  8,  9,  10,  11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 0]

def letras_numeros(a):
    lista = []
    let = a.lower()
    for i in let:
        for j in letras:
            if i == j:
                variable = letras.index(j)
                num = cad[variable]
                lista.append(num)
    return lista
        
def numeros_letras(a):
    lista=[]
    for i in a:
        for j in cad:
            if i == j:
                variable = cad.index(j)
                lista.append(letras[variable])
    return lista

def divisiones(m,mensaje):
    lista = []
    lista1 = []
    msg= mensaje
    while  (len(msg)%m) != 0:
        msg.append(cad[28])
    cont = 0
    for i in msg:
        lista1.append(i)
        if len(lista1) == m:
            lista.append(lista1)
            lista1 = []
    c=matrix(lista)
    d=c.transpose()
    return d

def juntar(x):
    temp1=x.transpose()
    temp=temp1.getA()
    lista = []    
    for i in  temp:
        for j in i:
            a=mod_29(int(round(j)))
            lista.append(a)
    return lista

def pasar_a_cadena(x):
    b = "".join(x)
    c=b.upper()
    return c
        
def verificar_numero(a):
    mensaje=""
    try:
        int(a)
        mensaje = mensaje + "i"
    except ValueError:
        mensaje = "malo"
    return mensaje

def mod_29(x):
    a = 0
    try:
        a=a+x%29
    except ValueError:
        a=a+666.666
    return a

def crear_matriz(m):
    matriz=[]
    for i in range(m):
        lista = []
        for j in range(m):        
            lista.append(int(random.uniform(0,29)))
        matriz.append(lista)
    c = matrix(matriz)
    return c

def mcd(n,m):
    m_aux = n%m
    if( m_aux == 0 ):
        return m
    elif( m_aux == 1 ):
        return 1
    else:
        return mcd(m,m_aux)

def inv_mult(a,n):
    if(mcd(a,n)!=1):
        print(str(a) + " NO TIENE INVERSO MULTIPLICATIVO EN " + str(n))
    else:
        for i in range(1,n) :
            if( ( a*i-1 )%n == 0 ):
                return i

def Inversa(matriz):
    lista=[]
    temp = linalg.inv(matriz)
    b=int(round(linalg.det(matriz)))
    uno = (b*temp)
    inverso = inv_mult(b,29)
    dos = inverso*uno
    tres = dos.getA()
    for i in tres:
        temp2 = []
        for j in i:
            ing = mod_29(j)
            temp2.append(ing)
        lista.append(temp2)
    regresar = matrix(lista)
    return regresar
