**Ejercicio #1**

def datos(cant, num):

&#x20;   listmul = \[]

&#x20;   for i in range(1, cant + 1):

&#x20;       result = num \* i

&#x20;       listmul.append(result)

&#x20;   return listmul



elementos = int(input("Tamaño de la lista: "))

base = int(input("Número base: "))



lista = datos(elementos, base)

print("Resultado:", lista)





**Ejercicio #2**

numnom=int(input("Cuántos nombres anotaras?: "))

nombres = \[]

largos = \[]



for i in range(numnom):

&#x20;   nomb = input("Escribe el nombre: ")

&#x20;   nombres.append(nomb)

&#x20;   

&#x20;   largonom = len(nomb)

&#x20;   largos.append(largonom)



print("LOS RESULTADOS SON:")

for i in range(numnom):

&#x20;   print(nombres\[i], "tiene", largos\[i], "letras")





**Ejercicio #3**

cant = int(input("Cuantos clientes fueron atendidos?: "))

evaluac = \[]



for i in range(cant):

&#x20;   voto = int(input(f"Cliente {i+1} - Ingrese su evaluación (de 1 a 5): "))

&#x20;   while voto < 1 or voto > 5:

&#x20;       voto = int(input("Error. Ingrese un valor entre 1 y 5: "))

&#x20;   evaluac.append(voto)



excelente = evaluac.count(5)

muy\_buena = evaluac.count(4)

buena = evaluac.count(3)

regular = evaluac.count(2)

malo = evaluac.count(1)



conteos = \[malo, regular, buena, muy\_buena, excelente]

max\_votos = max(conteos)



mas\_frecuente = conteos.index(max\_votos) + 1



suma\_total = sum(evaluac)

promedio = suma\_total / cant



clientes\_menores = 0

for nota in evaluac:

&#x20;   if nota < promedio:

&#x20;       clientes\_menores += 1



porcentaje\_menor = (clientes\_menores / cant) \* 100



print("\\n RESULTADOS")

print(f"a) Total de respuestas por tipo:")

print(f"   Excelente (5): {excelente}")

print(f"   Muy Buena (4): {muy\_buena}")

print(f"   Buena (3): {buena}")

print(f"   Regular (2): {regular}")

print(f"   Malo (1): {malo}")



print(f"b) La respuesta que más se repitio fue: {mas\_frecuente}")



print(f"c) Promedio de evaluación: {promedio:.2f}")

print(f"   Porcentaje de clientes por debajo del promedio: {porcentaje\_menor:.2f}%")





