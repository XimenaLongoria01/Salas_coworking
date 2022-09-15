# Salas_coworking
Evidencia1
from ast import Break, If, Return
import random
import collections
from time import sleep
import datetime
from tkinter import N
usuario1=[]
sala1=collections.deque()
turno1=[]
evento=[]
fecha1=[]
clave=[]
print("==============================================")
print("========Bienvendo a salas Coworking===========")
print("==============================================")
sleep(2)
while True:
    print("1:Reservar sala.")
    print("2:Editarsalas coworking.")
    print("3:Consultar reservacion para una fecha")
    print("4:Registrar nuevo cliente")
    print("5:Registrar una nueva sala")
    print("6:Salir.")
    opcion=int(input("Elija la opcion deseada: "))
    if opcion == 1:
        nom_registro = input("Ingrese su Nombre:")
        for nom_registro in usuario1:
            num_registro= int(input("Ingrese su numero de registro:"))
            fecha_str=input("Fecha del evento dd/mm/aaaa:")
            fecha= datetime.datetime.strptime(fecha_str,"%d/%m/%Y").date()
            fecha_actual=datetime.date.today()
            dia_siguiente= fecha_actual+datetime.timedelta(days=+1)
            if fecha<=dia_siguiente:
                print(f"!Fecha rechazada, se necesitan dos dias de anticipo!")
            else:
                turnos=["Matutino", "Vespertino","Nocturno"]
                turnos_elegir=input("Ingrese el turno que desea: ")
                turno1.append(turnos_elegir)
                print(f"Excelente su turno es: ",turnos_elegir) 
                nom_evento= input("Cual es el nombre de tu evento: ")
                evento.append(nom_evento)
                salas_disponibles=[1,2,3]
                sala_reservada=({random.choice(salas_disponibles)})
                sala1.append(sala_reservada)
                break
    
    if opcion == 2:
        lista = (evento, fecha1)

        def findAndReplace(lista, itemAReemplazar, nuevoValor): 
            for index, item in enumerate(lista):
                if item == itemAReemplazar:
                    lista[index] = nuevoValor

        def mostrarMensajeInicio():
            opcion = int(input("""
            Indique lo que desea realizar:
                \n 
            1) Mostrar los elementos de la lista 
            2) Editar un dato
            """))
            return opcion

        seguir = True

        while seguir:   
            opcion = mostrarMensajeInicio()
            if opcion == 1:
                for index in range(len(lista)):
                    print(f'\n Evento {index} :  {lista[index]}')
                    sleep(4)
                    break

            if opcion == 2:
                registro_evento= input("Introduzca el nombre de su Evento: ")
                recuperado=registro_evento.__len__(evento) 
            if registro_evento in evento:
                nuevo_nombre = input("¿Cual sera el nuevo nombre de su evento: ")
                registro.append({registro_sala:[nuevo_nombre]})
            else:
                print("El numero de folio de reservacion no fue encontrado")
    if opcion == 3:
        import datetime
        fecha_str=input("Fecha de tu reservacion en formato (dd/mm/aaaa): ")
        fecha = datetime.datetime.strptime(fecha_str, "%d/%m/%Y").date()
        turno_elegir=input("Ingrese el turno a elegir: ")
        if fecha_str and turnos_elegir in fecha1 and turno1:
            print("ESTA FECHA NO ESTA DISPONIBLE")
        else: 
            print("ESTA FECHA ESTA DISPONIBLE")

    if opcion == 4:
        import random
        cliente=[]
        clave_unica=[10,20,30,40,50,60,70]
        nombre=input(f"Coloque su nombre de usuario: ") 
        clave_unica=(print(f"La clave unica del cliente es:{random.choice(clave_unica)}"))
        cliente.append(nombre)
        clave.append(clave_unica)

        
        usuario1.append(cliente) 
    if opcion==5:
        import random
        registro=[]
        nombre=[]
        cupo=[]
        clave_unica=[10,20,30,40,50,60,70]
        registro_sala=("La clave unica de la sala es: ", {random.choice(clave_unica)})

        nombre_sala=input("Cual es el nombre de tu sala?: ")
        nombre.append(nombre_sala)

        cupo1=int(input("De cuanto es el cupo de tu sala?: "))

        cupo.append(cupo1)

        print("Tu clave de registro es: ",registro_sala)
        print("El nombre de tu sala es: ",nombre)
        print("El cupo de tu sala es: ",cupo)
        sala1.append(nombre)
    if opcion==6:
        print("***********************************************************")
        print("****   Reporte de reservaciones para para el dia hoy ****")
        print("************************************************************")
        print("                 SALA",sala1)      
        print("                 CLIENTE",usuario1)
        print("                 EVENTO",evento)
        print("                 TURNO",turno1)
        break
