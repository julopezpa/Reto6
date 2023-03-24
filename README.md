# Reto6
En este repo se desarrolla y soluciona el reto 6
#  PUNTO 1
![image](https://user-images.githubusercontent.com/124606636/227402173-8fbf758f-7222-42d3-aae8-5bd0b03c8028.png)
Una función matemática para calcular el volumen y el área superficial.from math import pi,sqrt

    from math import pi,sqrt
    def area_figuras(radio_cono:float, radio_esfera:float, altura_cono:float):
        area_esfera=4*pi*(radio_esfera**2)
        diagonal=sqrt(radio_cono**2+altura_cono**2)
        area_cono=(pi*radio_cono*diagonal)+(pi*radio_cono**2)
        area_total=area_cono+area_esfera
        return area_total
    def volumen_figuras(radio_cono:float, radio_esfera:float, altura_cono:float):
        volumen_esfera=(4/3*pi*radio_esfera**3)
        volumen_cono=(altura_cono*(radio_cono**2)*pi)/3
        return volumen_cono + volumen_esfera

    if __name__ == "__main__":
        radio_esfera= float(input("ingrese la longitud del radio de la esfera en cm"))
        radio_cono= float(input("ingrese la longitud del radio del cono en cm"))
        altura_cono= float(input("ingrese la longitud da la altura del cono en cm"))
        volumen_final=volumen_figuras(radio_cono,radio_esfera,altura_cono)
        area_final=area_figuras(radio_cono,radio_esfera,altura_cono)
        print("el superficie de la figura es "+str(area_final)+" cm  cuadrados")
        print("el volumen de la figura es "+ str(volumen_final)+" cm cubicos")
        
# PUNTO 2
![image](https://user-images.githubusercontent.com/124606636/227402389-f5673c45-c116-48c4-915b-68f52d4f97e8.png)
Una función matemática para calcular el área y el perimetro.

    from math import pi
    def perimetro_figura(r=float,altura=float,base=float):
        perimetro_rectangulo=(2*altura)+(2*base)
        perimetro_circulos=2*(2*pi*r)
        return perimetro_circulos + perimetro_rectangulo
    def area_figuras(r=float,altura=float,base=float):
        area_rectangulo=base*altura
        area_circulos=2*(pi*(r**2))
        return area_rectangulo + area_circulos

    if __name__=="__main__":
        r=float(input("ingrese el radio de los circulos en cm"))
        base=float(input("ingrese la longitud de la base en cm"))
        altura=float(input("ingrese la longitud de la altura en cm"))
        perimetro_final=perimetro_figura(r,altura,base)
        area_final=area_figuras(r,altura,base)
        print("el perimetro de la figura es "+str(perimetro_final)+" cm")
        print("el area de la figura es de "+str(area_final)+"cm cuadrados")
        
# PUNTO 3
Diseñe una función que calcule la cantidad de carne de aves en kilos si se tienen N gallinas, M gallos y K pollitos cada uno pesando 6 kilos, 7 kilos y 1 kilo respectivamente.

    def carne(gallinas=int,gallos=int,pollitos=int):
        total_carne_aves=(6*gallinas)+(7*gallos)+(1*pollitos)
        return total_carne_aves

    if __name__=="__main__":
        gallinas=int(input("ingrese el numero de gallinas"))#En enteros porque yo no veo medio pollito caminando 
        gallos=int(input("ingrese el numero de gallos"))
        pollitos=int(input("ingrese el numero de pollitos"))
        carne_que_se_tiene=carne(gallinas,gallos,pollitos)
        print(str(carne_que_se_tiene)+" kg de carne de aves ")
        
# PUNTO 4
Mi mamá me manda a comprar P panes a 300 cada uno, M bolsas de leche a 3300 cada una y H huevos a 350 cada uno. Hacer un programa que me diga las vueltas (o lo que quedo debiendo) cuando me da un billete de B pesos.

    def cambio_en_la_tienda(panes=float,leche=float,huevos=float,billete=float):
        valor_total=(panes*300)+(leche*3300)+(huevos*350)
        return billete-valor_total

    if __name__=="__main__":
        panes=float(input("ingrese el numero de panes que le mandaron comprar"))
        leche=float(input("ingrese el numero de bolsas de leche le mandaron comprar"))
        huevos=float(input("ingrese el numero de huevos que le mandaron comprar"))
        billete=float(input("ingrese el valor del billete que le dio su mama"))
        cambio=cambio_en_la_tienda(panes,leche,huevos,billete)
        if cambio==0:
            print("no debe nada de vueltas")
        elif cambio<0:
            cambio=cambio*(-1)
            print("le faltan por pagar "+str(cambio)+" pesos")
        else:
            cambio>0
            print("le van a dar "+str(cambio)+" de vueltas")

# PUNTO 5
Haga un programa que utilice una función para calcular el valor de un préstamo C usando interés compuesto del i por n meses.

    def interes_compuesto(c=float,i=float,n=float):
        interes=c*((1+(i/100))**n)
        return interes

    if __name__=="__main__":
        c=float(input("ingrese el valor del prestamo"))
        i=float(input("ingrese el porcentaje de interes"))
        n=float(input("ingrese el tiempo en meses que va a durar el prestamo"))
        valor_del_prestamo=interes_compuesto(c,i,n)
        print("el valor que tendra que pagar en "+str(n)+" meses, sera de "+str(valor_del_prestamo)+" pesos")
# PUNTO 6
El número de contagiados de Covid-19 en el país de NuncaLandia se duplica cada día. Hacer un programa que diga el número total de personas que se han contagiado cuando pasen D días a partir de hoy, si el número de contagiados actuales es C.

    def contagios_covid(d=float,c=int):
        return c*(2**d)

    if __name__=="__main__":
        c=int(input("ingrese el numero de personas contagiadas con covid"))
        d=float(input("ingrese el numero de dias que han pasado"))
        contagiados_actuales=contagios_covid(d,c)
        print("si el numero de contagiados es de "+str(c)+", el numero de contagiados para el dia "+str(d)+" es de "+str(contagiados_actuales))
        
# PUNTO 7
Escriba un programa que pida 5 números reales y calcule las siguientes operaciones usando una función para cada una:El promedio, La mediana, El promedio multiplicativo, Ordenar los números de forma ascendente, Ordenar los números de forma descendente, La potencia del mayor número elevado al menor número y La raíz cúbica del menor número

    from statistics import median
    def promedio(n1=float,n2=float,n3=float,n4=float,n5=float):
        x=(n1+n2+n3+n4+n5)/5
        return x
    def mediana(n1=float,n2=float,n3=float,n4=float,n5=float):
        from statistics import median
        numeros=[n1,n2,n3,n4,n5]
        y=median(numeros)
        return y
    def promedio_multiplicativo(n1=float,n2=float,n3=float,n4=float,n5=float):
        y=(n1*n2*n3*n4*n5)**(1/5)
        return y
    def numeros_de_forma_ascendente(n1=float,n2=float,n3=float,n4=float,n5=float):
        numeros=[n1,n2,n3,n4,n5]
        p=sorted(numeros)
        return p
    def numeros_de_forma_descendente(n1=float,n2=float,n3=float,n4=float,n5=float):
        numeros=[n1,n2,n3,n4,n5]
        p=sorted(numeros,reverse=True)
        return p
    def numero_mayor_elevado_el_menor(n1=float,n2=float,n3=float,n4=float,n5=float):
        numeros=[n1,n2,n3,n4,n5]
        mayor = max(numeros)
        menor = min(numeros)
        potencia = mayor ** menor
        return potencia
    def la_raiz_cubica_del_numero_menor(n1=float,n2=float,n3=float,n4=float,n5=float):
        numeros=[n1,n2,n3,n4,n5]
        menor = min(numeros)
        raiz=menor**(1/3)
        return raiz
    if __name__=="__main__":
        n1= float(input("Ingrese un número: ")) 
        n2= float(input("Ingrese un número: ")) 
        n3= float(input("Ingrese un número: ")) 
        n4= float(input("Ingrese un número: ")) 
        n5= float(input("Ingrese un número: ")) 
        promedio=promedio(n1,n2,n3,n4,n5)
        print(str(promedio))
        mediana=mediana(n1,n2,n3,n4,n5)
        print(str(mediana))
        promedio_multiplicativo=promedio_multiplicativo(n1,n2,n3,n4,n5)
        print(str(promedio))
        numeros_de_forma_ascendente=numeros_de_forma_ascendente(n1,n2,n3,n4,n5)
        print(str(numeros_de_forma_ascendente))
        numeros_de_forma_descendente=numeros_de_forma_descendente(n1,n2,n3,n4,n5)
        print(str(numeros_de_forma_descendente))
        numero_mayor_elevado_el_menor=numero_mayor_elevado_el_menor(n1,n2,n3,n4,n5)
        print(str(numero_mayor_elevado_el_menor))
        la_raiz_cubica_del_numero_menor=la_raiz_cubica_del_numero_menor(n1,n2,n3,n4,n5)
        print(str(la_raiz_cubica_del_numero_menor))

por alguna razon no puedo adjutar el archivo de python, entnoces mando camputaras para mostralo

![image](https://user-images.githubusercontent.com/124606636/227404024-20fb0022-624b-4ad5-936e-73f9beb214ce.png)
![image](https://user-images.githubusercontent.com/124606636/227404059-75e1240f-4fd0-4521-9a1a-1f3120c8f7bb.png)

# PUNTO 8
    import prueba

    if __name__=="__main__":
        n1= float(input("Ingrese un número: ")) 
        n2= float(input("Ingrese un número: ")) 
        n3= float(input("Ingrese un número: ")) 
        n4= float(input("Ingrese un número: ")) 
        n5= float(input("Ingrese un número: ")) 
        promedio=prueba.promedio(n1,n2,n3,n4,n5)
        print(str(promedio))
        mediana=prueba.mediana(n1,n2,n3,n4,n5)
        print(str(mediana))
        promedio_multiplicativo=prueba.promedio_multiplicativo(n1,n2,n3,n4,n5)
        print(str(promedio))
        numeros_de_forma_ascendente=prueba.numeros_de_forma_ascendente(n1,n2,n3,n4,n5)
        print(str(numeros_de_forma_ascendente))
        numeros_de_forma_descendente=prueba.numeros_de_forma_descendente(n1,n2,n3,n4,n5)
        print(str(numeros_de_forma_descendente))
        numero_mayor_elevado_el_menor=prueba.numero_mayor_elevado_el_menor(n1,n2,n3,n4,n5)
        print(str(numero_mayor_elevado_el_menor))
        la_raiz_cubica_del_numero_menor=prueba.la_raiz_cubica_del_numero_menor(n1,n2,n3,n4,n5)
        print(str(la_raiz_cubica_del_numero_menor))

# PUNTO 9
Consultar qué es y cómo funciona pip en python.

Pip es el administrador de paquetes de Python, lo que significa que es una herramienta que se utiliza para instalar, actualizar y desinstalar paquetes o módulos de software de Python. Los paquetes de Python son colecciones de archivos que contienen código de Python y se utilizan para agregar funcionalidad a un proyecto de Python.

# PUNTO 10
Hacer un listado de módulos populares para python que se puedan instalar com pip y consultar cómo instalarlos.

1)NumPy: es una biblioteca para Python que se utiliza para trabajar con matrices y vectores. Es muy popular en la comunidad científica y se utiliza comúnmente para el procesamiento de datos y el análisis numérico. Para instalar NumPy, use el siguiente comando: pip install numpy.

2)pandas: es una biblioteca de Python que se utiliza para el análisis de datos. Permite la manipulación de datos en diferentes formatos, como CSV, Excel, SQL, etc. Para instalar pandas, use el siguiente comando: pip install pandas.

3)Matplotlib: es una biblioteca de Python para la visualización de datos. Se puede utilizar para crear gráficos, diagramas de dispersión, diagramas de barras y más. Para instalar Matplotlib, use el siguiente comando: pip install matplotlib.

4)Django: es un marco de trabajo para Python utilizado para crear aplicaciones web. Proporciona una estructura para la creación de aplicaciones web, así como una interfaz de administración para administrar el contenido del sitio. Para instalar Django, use el siguiente comando: pip install django.

5)Flask: es un micro marco de trabajo para Python utilizado para crear aplicaciones web simples y livianas. Es fácil de usar y se puede personalizar según las necesidades del proyecto. Para instalar Flask, use el siguiente comando: pip install flask.

        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        
        






