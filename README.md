# python
ayuda mi código presenta múltiples fallas

import random

def numeral1 (fam , hij , familias  , EdadHijos):
    f = fam
    h = hij
    contMen = 0
    acumEdad = 0
    promedioGen = 0
    
    for i in range(f):
        for j in list(h):
            acumEdad = acumEdad +EdadHijos[i][j]
            
    promedioGen = (acumEdad/(f*5))
    print ('Promedio general: ',promedioGen)
    
    for i in range(f):
        contMen = 0
        acumSub = 0
        for j in range(h):             
           if (EdadHijos[i][j] < promedioGen ):
                contMen = contMen + 1
                acumSub = acumSub + 60.000
    
        print("La familia " + familias[i] + " recibio un subsidio de alimentos de " + str(acumSub))

    print("\n")

def numeral2(fam , hij , familias , estado , EdadHijos):
    
    f = fam
    h = hij
    becados = 0
    porcentaje = 0
    
    for i in range(f):
        becados = 0
        porcentaje = 0
        for j in range(h):
            
            if(EdadHijos[i][j] > 18):
                becados = becados + 1
                
        porcentaje = (becados/h)   
        print("A la familia " + familias[i] + " le asignaron " + str(becados) + " beca(s) , con un porcentaje del " + str(porcentaje) + " respecto a la cantidad de hijos\n")
            
                
def numeral3(fam , Familias , SiNo):
    i = 0 
    cont = 0
    f = fam
    promedio = 0 
   
    for i in range (f):
        if (SiNo[i] == 'no'):
            cont = cont + 1
            print ("La familia " + Familias[i] + " paga una cuota mensual de 125.000")
        else:
            print("La familia " + Familias[i] + " paga una cuota mensual de 100.000" )
    promedio = (cont / f)*100
    print("\n")
    print ("El porcentaje de familias que paga una cuota de 125.000 es de " + str(promedio) + "%")
    print("\n")
    
        
def main():
    from  random import  randint
    fam = int(input("Ingrese la cantidad de familias :"))
    i = 0
    Familias =  list(range(fam))
    hij=list(range(fam))
    EdadHijos = []
    Estado = []
    SiNo = []
    
    for i in range (fam):
        SiNo.append(random.choice(['si' ,'no']))
        
    for i in range(fam):
        Familias[i] = input("Ingrese el apellido de la familia " + str(i+1) + " :")
        hij[i]= int(input("Ingrese la cantidad de hijos de la familia " + str(i+1)+ ' :'))
    
    for i in range(fam):
        EdadHijos.append([ randint(0, 23)for i in range(hij[i])])
        
        
    print ("Edad de los hijos :\n" , EdadHijos)
    print("\n")
    print("Familias :\n" , Familias)
    print("Numeral 1:\n")
    numeral1(fam, hij, Familias, EdadHijos)
    print("Numeral 2:\n")
    numeral2(fam , hij[i] , Familias, Estado, EdadHijos)
    print("Numeral 3:\n")
    numeral3(fam , Familias , SiNo)
   
main()        
