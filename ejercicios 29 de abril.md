**Ejercicio #1**

tabla=\[

&#x20;   \[1, 2, 3],

&#x20;   \[4, 5, 6],

&#x20;   \[7, 8, 9],

&#x20;   ]

&#x20;   

print (tabla)



print(tabla\[0]\[0])

print(tabla\[1]\[2]-tabla\[1]\[1])



for i in tabla:

&#x20;   for j in i:

&#x20;       if j>=6:

&#x20;          break

&#x20;       else:

&#x20;         print(j)



**Ejercicio #2**

matriz=\[]

sizerow=int(input("Ingrese el tamaño de la fila:"))

sizecolum=int(input("Ingrese el tamaño de la columna:"))



for f in range(sizerow):

&#x20;   fila=\[]

&#x20;   for c in range (sizecolum):

&#x20;       dato=int(input("Ingrese datos:"))

&#x20;       fila.append(dato)

&#x20;       matriz.append(fila)

print(matriz)



**Ejercicio #3**



filas = int(input("Ingresa el numero de filas: "))

columnas = int(input("Ingresa el numero de columnas: "))



print("\\nIngresa los datos de la Matriz 1:")

matriz1 = \[]

for i in range(filas):

&#x20;   fila = \[]

&#x20;   for j in range(columnas):

&#x20;       n = int(input(f"Posicion \[{i}]\[{j}]: "))

&#x20;       fila.append(n)

&#x20;   matriz1.append(fila)



print("\\nIngresa los datos de la Matriz 2:")

matriz2 = \[]

for i in range(filas):

&#x20;   fila = \[]

&#x20;   for j in range(columnas):

&#x20;       n = int(input(f"Posicion \[{i}]\[{j}]: "))

&#x20;       fila.append(n)

&#x20;   matriz2.append(fila)



def restar(m1, m2):

&#x20;   resultado = \[]

&#x20;   for i in range(filas):

&#x20;       fila\_nueva = \[]

&#x20;       for j in range(columnas):

&#x20;           # Restamos los números uno por uno

&#x20;           resta = m1\[i]\[j] - m2\[i]\[j]

&#x20;           fila\_nueva.append(resta)

&#x20;       resultado.append(fila\_nueva)

&#x20;   return resultado



matriz\_final = restar(matriz1, matriz2)



print("\\nLa resta de las matrices es:")

for fila in matriz\_final:

&#x20;   print(fila)





