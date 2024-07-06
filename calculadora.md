#Mensaje de bienvenida
print('Instituto de Seguridad y Servicios Sociales de los Trabajadores del Estado \n\t Por favor ingresa los datos solicitados a continuación')
# Solicita nombre y apellidos, se condiciona, en caso que no se registre información regresará a la solicitud del dato
def input_non_empty(prompt):
    while True:
        value = input(prompt).strip()
        if value:
            return value
        print("Este campo es obligatorio para continuar.")
nombre = input_non_empty('Nombre: ')
apellido_paterno = input_non_empty('Apellido paterno: ')
apellido_materno = input_non_empty('Apellido materno: ')
# Solicita Edad y se condiciona, en caso que el dato capturado sea menor a 0 o mayor a 102 se regresará a la solicitud del dato
def input_valid_age(prompt):
    while True:
        try:
            age = int(input(prompt).strip())
            if 0 <= age <= 102:
                return age
            else:
                print("Favor de capturar correctamente su edad")
        except ValueError:
            print("El dato capturado debe ser un número entero")
edad = input_valid_age('Su edad en años: ')
# Se solicitan datos de peso y estatura, en caso de capturar un dato distinto a float se solicitará nuevamente
def input_valid_float(prompt):
    while True:
        try:
            value = float(input(prompt).strip())
            return value
        except ValueError:
            print("Favor de capturar correctamente.")
peso = input_valid_float('Su peso en kilogramos: ')
estatura = input_valid_float('Su altura en metros: ')
# Se calcula su IMC
imc = peso / (estatura ** 2)
imc_2 = "{:.2f}".format(imc)
#Identifica en qué indice se encuentra
if imc >= 0 and imc <= 15.99:
    print("Delgadez severa")
elif imc >= 16.00 and imc <= 16.99:
    print("Delgadez moderada")
elif imc >= 17.00 and imc <= 18.49:
    print("Delgadez leve")
elif imc >= 18.50 and imc <= 24.99:
    print("Normal")
elif imc >= 25.00 and imc <= 29.99:
    print("Sobrepeso")
elif imc >= 30.00 and imc <= 34.99:
    print("Obesidad leve")
elif imc >= 35.00 and imc <= 39.00:
    print("Obesidad media")
elif imc >= 40.00:
    print("Obesidad mórbida")
#Imprime resultado y nombre
print(nombre + ' ' + apellido_paterno + ' ' + apellido_materno + ' su IMC es: ' + str(imc_2))
