# Ejercicios de Introducción a Python

## Tipos de Datos Básicos y Estructuras de Control

### Ejercicio 1: Calculadora de Propinas

Escribe un programa que solicite al usuario el monto de una cuenta (float) y el porcentaje de propina que desea dar (int). El programa debe calcular y mostrar la propina y el total a pagar.

**Ejemplo de salida:**

```
Ingresa el monto de la cuenta: 150.75
Ingresa el porcentaje de propina: 15
Propina: $22.61
Total a pagar: $173.36
```
Mc = float(input("Ingresar el monto de la cuenta: "))
Pp = int(input("Ingresar el porcentaje de propina"))
Prop = Mc*(PP/100)
Tot = Mc + Prop

print("Propina: $",Prop)
print("Total a pagar: $",Tot)
---

### Ejercicio 2: Contador de Vocales

Crea un programa que pida una palabra al usuario (str) y use un ciclo `for` para contar cuántas vocales (a, e, i, o, u) contiene la palabra. Considera tanto mayúsculas como minúsculas.

**Ejemplo de salida:**

```
Ingresa una palabra: Python
La palabra "Python" tiene 1 vocal(es)
```
Pal=input("Ingresar una palabra: ")
cont = 0

for l in Pal:
    if l == "a" or l == "A" or l == "e" or l == "E" or l == "i" or l == "I" or l == "o" or l == "O" or l == "u" or l == "U":
        cont = cont + 1
print("La palabra ",Pal," tiene ",cont," vocal(les)")
---

### Ejercicio 3: Tabla de Multiplicar

Solicita al usuario un número entero (int) y usa un ciclo `for` para mostrar su tabla de multiplicar del 1 al 10.

**Ejemplo de salida:**

```
Ingresa un número: 7
7 x 1 = 7
7 x 2 = 14
...
7 x 10 = 70
```
num = int(input("Ingresar un numero: "))
x = 0

for x in range (10):
    print(num," x ",(x+1)," = ",(x+1)*num)
---

### Ejercicio 4: Validador de Contraseña Simple

Escribe un programa que pida una contraseña al usuario y use un ciclo `while` para seguir pidiendo la contraseña hasta que tenga al menos 8 caracteres. Al final, muestra la longitud de la contraseña aceptada.

**Ejemplo de salida:**

```
Ingresa tu contraseña: 123
Muy corta. Ingresa tu contraseña: 12345678
Contraseña aceptada. Longitud: 8 caracteres
```
l = 0
while l < 8:
    contra = input("Ingresa tu contraseña: ")
    l = len(contra)
    if l < 8:
        print("Muy corta. ")
print("Contraseña aceptada. Longitud: ",l," caracteres")
---

### Ejercicio 5: Suma de Números Pares

Pide al usuario un número entero (int) y usa un ciclo `for` para calcular la suma de todos los números pares desde 2 hasta ese número (inclusive).

**Ejemplo de salida:**

```
Ingresa un número: 10
La suma de números pares desde 2 hasta 10 es: 30
(2 + 4 + 6 + 8 + 10 = 30)
```
num = int(input("Ingresar un numero:"))
sum = 0
for x in range(0,num+1,2):
    sum+= x
print("La suma de los numeros pares desde 2 hasta",num,"es:",sum)

---

### Ejercicio 6: Generador de Patrones de Texto

Solicita al usuario un carácter (str) y un número de filas (int). Usa ciclos `for` anidados para crear un patrón triangular donde cada fila tiene un carácter más que la anterior.

**Ejemplo de salida:**

```
Ingresa un carácter: *
Ingresa número de filas: 4
*
**
***
****
```
car = input("Ingresar un caracter: ")
fil = int(input("Ingresar numero de filas: "))
cont = 1
for x in range(fil):
    for i in range(cont):
        print(car, end="")
    print("")
    cont+=1
---

### Ejercicio 7: Calculadora de Promedio con Validación

Usa un ciclo `while` para pedir al usuario que ingrese números decimales (float) uno por uno. El programa debe terminar cuando el usuario ingrese -1. Al final, calcula y muestra el promedio de todos los números ingresados (sin contar el -1).

**Ejemplo de salida:**

```
Ingresa un número (-1 para terminar): 8.5
Ingresa un número (-1 para terminar): 9.2
Ingresa un número (-1 para terminar): 7.8
Ingresa un número (-1 para terminar): -1
Promedio: 8.50
```
num = 0
sum = 0
cont = 0
while num != -1:
    num = float(input("Ingresar un numero (-1 para salir): "))
    if num != -1:
        sum += num
        cont += 1
print("Promedio: ",round((sum/cont),2))

---

### Ejercicio 8: Inversor de Palabras

Pide al usuario una frase (str) y usa un ciclo `for` para mostrar cada palabra de la frase al revés. Las palabras se separan por espacios.

**Ejemplo de salida:**

```
Ingresa una frase: Hola mundo Python
aloH
odnum
nohtyP
```
Pal = input("Ingresa una frase: ")
rev = ""
for l in Pal:
    if l == " ":
        for i in rev[::-1]:
            print(i, end="")
        print("")
        rev = ""
    else:
       rev = rev + l
for i in rev[::-1]:
            print(i, end="")
---

### Ejercicio 9: Juego de Adivinanza Simple

Crea un juego donde el programa "piensa" en un número del 1 al 20 (puedes usar el número 15 fijo). Usa un ciclo `while` para que el usuario siga adivinando hasta que acierte. Cuenta y muestra el número de intentos.

**Ejemplo de salida:**

```
Adivina el número (1-20): 10
Muy bajo. Adivina el número (1-20): 18
Muy alto. Adivina el número (1-20): 15
¡Correcto! Lo adivinaste en 3 intentos.
```
import random as ran
num = ran.randint(1,20)
guess = 0
while guess != num:
    guess = int(input("Adivina el numero entre 1 y 20: "))
    if guess < num:
        print("Muy bajo")
    elif guess > num:
        print("Muy alto")
    else:
        print("Felicidades! Adivinaste el numero:",num)

---

### Ejercicio 10: Análisis de Texto

Pide al usuario que ingrese un texto (str) y realiza el siguiente análisis usando ciclos:

- Cuenta el número total de caracteres
- Cuenta cuántos espacios hay
- Cuenta cuántos dígitos numéricos hay
- Muestra la primera y última letra del texto

**Ejemplo de salida:**

```
Ingresa un texto: Hola mundo 123
Análisis del texto:
- Caracteres totales: 13
- Espacios: 2
- Dígitos numéricos: 3
- Primera letra: H
- Última letra: 3
```
text = input("Ingresar un texto: ")
contl = 0
contn = 0
conts = 0
contt = 0

for l in text:
    if l.isalpha()== True:
        contl += 1
        contt += 1
    elif l == " ":
        conts += 1
    else:
        contn += 1
        contt += 1
print("Caracteres totales: ",contt)
print("Espacios: ",conts)
print("Digitos numericos: ",contn)
print("Primera letra: ",text[0])
print("Ultima letra: ",text[-1])