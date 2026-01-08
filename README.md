# Men-de-Validaci-n-Num-rica
def pedir_entero(mensaje, minimo=None, maximo=None):
    while True:
        try:
            valor = int(input(mensaje))
            if minimo is not None and valor < minimo:
                print("❌ El número es menor al permitido.")
            elif maximo is not None and valor > maximo:
                print("❌ El número es mayor al permitido.")
            else:
                return valor
        except ValueError:
            print("❌ Debe ingresar un número entero válido.")

def pedir_texto(mensaje):
    while True:
        texto = input(mensaje).strip()
        if texto == "":
            print("❌ El texto no puede estar vacío.")
        else:
            return texto

# Programa principal
print("=== REGISTRO DE USUARIO ===")

nombre = pedir_texto("Ingrese su nombre: ")
edad = pedir_entero("Ingrese su edad: ", minimo=1, maximo=120)
nota = pedir_entero("Ingrese su nota (0 a 100): ", minimo=0, maximo=100)

print("\n=== DATOS INGRESADOS ===")
print("Nombre:", nombre)
print("Edad:", edad)
print("Nota:", nota)

if nota >= 70:
    print("Resultado: APROBADO ✅")
else:
    print("Resultado: REPROBADO ❌")