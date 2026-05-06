**Ejercicio #1**

matriz = \[

&#x20;   \[1, 2, 3],

&#x20;   \[1, 1, 1],

&#x20;   \[8, 7, 5]

]



sumfil = \[0, 0, 0]

sumcol = \[0, 0, 0]



for i in range(3):

&#x20;   for j in range(3):

&#x20;       valor = matriz\[i]\[j]

&#x20;       sumfil\[i] += valor

&#x20;       sumcol\[j] += valor



print("Matriz:")

for fila in matriz:

&#x20;   print(fila)



print(f"\\nVector Suma de Filas: {sumfil}")

print(f"Vector Suma de Columnas: {sumcol}")



**Ejercicio #2**

cuadrado = \[]



print("Introduce los números del 1 al 9 para el cuadrado:")



for i in range(3):

&#x20;   fila = \[]

&#x20;   for j in range(3):

&#x20;       num = int(input(f"Número en \[{i}]\[{j}]: "))

&#x20;       fila.append(num)

&#x20;   cuadrado.append(fila)



lista\_plana = cuadrado\[0] + cuadrado\[1] + cuadrado\[2]

numeros\_validos = True



for n in range(1, 10):

&#x20;   if n not in lista\_plana:

&#x20;       numeros\_validos = False



es\_magico = True

suma\_ref = 15 



if numeros\_validos:

&#x20;   for f in cuadrado:

&#x20;       if sum(f) != suma\_ref:

&#x20;           es\_magico = False

&#x20;   

&#x20;   for c in range(3):

&#x20;       suma\_col = cuadrado\[0]\[c] + cuadrado\[1]\[c] + cuadrado\[2]\[c]

&#x20;       if suma\_col != suma\_ref:

&#x20;           es\_magico = False

&#x20;           

&#x20;   diag1 = cuadrado\[0]\[0] + cuadrado\[1]\[1] + cuadrado\[2]\[2]

&#x20;   diag2 = cuadrado\[0]\[2] + cuadrado\[1]\[1] + cuadrado\[2]\[0]

&#x20;   

&#x20;   if diag1 != suma\_ref or diag2 != suma\_ref:

&#x20;       es\_magico = False

else:

&#x20;   es\_magico = False



print("\\n--- Verificación ---")

if es\_magico:

&#x20;   print("¡Felicidades! Es un cuadrado mágico.")

else:

&#x20;   print("No es un cuadrado mágico.")











