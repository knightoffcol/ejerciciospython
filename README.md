# ejerciciospython
### Desarrollar los siguientes ejercicios en PYTHON.
1. Hacer un algoritmo que calcule el promedio de 3 notas de una asignatura y determine si ganó o perdió. La asignatura se gana sobre 3,5
```
calificacion1 = input("Ingrese la primera calificacion: ")
calificacion2 = input("Ingrese la segunda calificacion: ")
calificacion3 = input("Ingrese la terceracalificacion: ")

calificacion_definitiva = (float(calificacion1) + float(calificacion2)  + float(calificacion3))/3
print("La calificaci�n definitiva del estudiante es: ", calificacion_definitiva)

if calificacion_definitiva >= 3.5:
    print("paso")
else:
    print("perdio")
```
2. Hacer un algoritmo que convierta un valor ingresado en centímetros a:
- a. Pies
- b. Pulgadas
- c. Yardas
- d. Metros.
```
metros=input("Ingrese la longitud en metros: ") 
pies= float (metros) * 3.28084	
pulgadas = float(metros) * 39.3701	
yardas = float(metros) * 1.09361	
centimetros = float (metros) * 100	
print(f"La longitud en pies es:  {pies}")
print(f"La longitud en pulgadas es:  {pulgadas}")
print(f"La longitud en yardas es:  {yardas}")
print(f"La longitud en centimetros es:  {centimetros}")
```
3. Dado un grupo de 5 Números (Diferentes a Cero), realice un algoritmo que
permita determinar y dar como salida lo siguiente:
- a. Número mayor encontrado en el grupo
- b. Número menor encontrado en el grupo
- c. Cantidad de números mayores a 10
- d. Suma de números negativos encontrados
- e. Promedio de números positivos encontrados.

```
def analizar_numeros(numeros):
    if len(numeros) != 5:
        raise ValueError("La lista debe contener exactamente 5 números")

    mayor = numeros[0]
    menor = numeros[0]
    cuenta_mayores_10 = 0
    suma_negativos = 0
    suma_positivos = 0
    cuenta_positivos = 0
    
    for numero in numeros:
        if numero > mayor:
            mayor = numero
        if numero < menor:
            menor = numero
        if numero > 10:
            cuenta_mayores_10 += 1
        if numero < 0:
            suma_negativos += numero
        if numero > 0:
            suma_positivos += numero
            cuenta_positivos += 1
    promedio_positivos = suma_positivos / cuenta_positivos if cuenta_positivos > 0 else 0
    
    print(f"Número mayor: {mayor}")
    print(f"Número menor: {menor}")
    print(f"Cantidad de números mayores a 10: {cuenta_mayores_10}")
    print(f"Suma de números negativos: {suma_negativos}")
    print(f"Promedio de números positivos: {promedio_positivos}")
numeros = []
print("Por favor, ingrese 5 números diferentes a cero:")
for i in range(5):
    while True:
        try:
            numero = float(input(f"Ingrese el número {i + 1}: "))
            if numero == 0:
                print("El número no puede ser cero. Inténtelo de nuevo.")
            else:
                numeros.append(numero)
                break
        except ValueError:
            print("Entrada no válida. Por favor ingrese un número.")
analizar_numeros(numeros)
```
4. Los bancos manejan como seguridad en sus cajeros electrónicos un máximo de 3 intentos para el ingreso de la clave. Elaborar un programa que pida una contraseña y si no es la adecuada debe salir un mensaje de error indicando que le quedan X números de intentos; cuando exceda el máximo de intentos debe salir un mensaje de TARJETA BLOQUEADA. La clave para hacer la verificación debe ser 0258.
```
correct_password = "0258"

max_attempts = 3

attempts = 0

while attempts < max_attempts:
    password = input("Ingrese su contraseña: ")
    
    if password == correct_password:
        print("Contraseña correcta. Acceso concedido.")
        break
    else:
        attempts += 1
        remaining_attempts = max_attempts - attempts
        if remaining_attempts > 0:
            print(f"Contraseña incorrecta. Le quedan {remaining_attempts} intentos.")
        else:
            print("TARJETA BLOQUEADA.")
```
