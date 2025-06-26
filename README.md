usuarios = []
def ingresar_usuario(usuario,sexo,contraseña):
    if nombre in usuarios:
        print("Error: El nombre de usuario ya existe")
        return
    nuevo_usuario = {
        "usuario":usuario,
        "sexo":sexo,
        "contraseña":contraseña
        }
    usuarios.append(nuevo_usuario)

def buscar_usuario(busuario):
    for u in usuarios:
        if u["busuario"] == busuario:
            print(f"El sexo de el usuario es:",{u["sexo"]}, - " Y su contraseña es :",{u["contraseña"]})
        else:
            print("No se ha podido encontrar al usuario ingresado")
        return
    print("El usuario no se encuentra")

def eliminar_usuario(nombre):
    for u in usuarios:
        if u["nombre"] == nombre.lower():
            print("Usuario Eliminado")
            usuarios.romeve(nombre)
        else:
            print("Usuario no encontrado. No se puede Eliminar")

while True:
    print("======Menu Principal======")
    print("1.- Ingresar usuario.")
    print("2.- Buscar usuario.")
    print("3.- Eliminar usuario.")
    print("4.- Salir.")
    try:
        opcion = int(input("Ingrese una opcion: "))
    except ValueError:
        print("Ingresar solo numeros para la opcion. ")
    match opcion:
        case 1:
            nuevusuario = input("Ingrese el Nombre de Usuario: ")
            while True:
                sexo = input("Ingrese sexo M o F: ").upper()
                if sexo in ["M", "F"]:
                    print("SEXO INGRESADO")
                    break
                else:
                    print("Debe ingresar M o F solamente. Intente de nuevo")
            contraseña = input("Por favor Ingrese una Contraseña: ")
            print("Usuario Ingresado con exito!!!")
        case 2:
            busuario = input("Ingrese el usuario que desea buscar: ")
            buscar_usuario(busuario)
        case 3:
            nombre = input("Ingrese el Nombre del usuario que desea eliminar: ")
            eliminar_usuario(nombre)
        case 4:
            print("Programa terminando.")
            print("Saliendo...")
            break
        case _:
            print("Error: Ingresar una opcion valida")
