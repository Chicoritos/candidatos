import random
N=int(input("Ingresar número de candidatos:"))
nombres=[]
partidos= []
municipios=[]

for i in range(N):
  print("Candidato "+str(i+1)+": ")
  nom = input("Nombre: ")
  par = input("Partido: ")
  mun = input("Municipio: ")
  nombres.append(nom)
  partidos.append(par)
  municipios.append(mun)

def Mesas():
    munivotantes=[]
    muni = input('Ingrese el nombre de la municipalidad: ')
    munivotantes.append(muni)
    mesas = int(input('Ingrese el número de mesas: '))
    for i in range(mesas):
        votantes = int(input('Ingrese el número de votantes de la mesa '+str(i+1)+': '))
        munivotantes.append(votantes)
    return munivotantes[1:]

def escrutinio():
    vot=random.randrange(0,N)
    return vot

time=0
for i in Mesas():
    for k in range(0,i):
        ed=random.randint(18, 65)
        if ed>=18 and ed<=35:
            time=+2
            print(escrutinio())
        elif ed>35 and ed<=55:
            time=+4
            print(escrutinio())
        else:
            time=+6
            print(escrutinio())
print(time)
