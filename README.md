# Hospital farmacologico

## Ejercicio integrador - Paradigma Funcional

**El Hospital Juan Carlos Batman nos llama para simular la atención a los pacientes, que consiste básicamente en venderle remedios para que se curen sus enfermedades.**

![](remedios.jpg)

A las enfermedades se las conoce por su nombre
~~~Haskell
type Enfermedad =  String
~~~

Una persona puede tener varias enfermedades, se sabe cuánto dinero tiene y su edad.
~~~Haskell
data Persona = … 
~~~

Cuando una persona toma un remedio puede curarse de sus enfermedades dependiendo de las drogas que contenga y sus respectivas dosis. 

Pero, ojo, estamos en mundo capitalista, y cada remedio tiene su precio. Como bien sabemos, este dinero no depende de sus componentes sino del precio arbitrario que ponga el laboratorio y del marketing, pero el análisis de por qué un remedio es más caro o más barato queda fuera del análisis de este simulador.

~~~Haskell
type Dosis = Float
data Remedio = Remedio { componentes :: [(Droga, Dosis)], precio :: Float } ...
~~~

Un coctel de remedios es simplemente muchos remedios juntos.
~~~Haskell
type Coctel = [Remedio]
~~~

Algunas de las drogas conocidas son:
* Benzoprolamina: cura la Dispepsia Muscular, independientemente de la dosis.
* Trifosfato de Anarcokirchnerismo: cura la Paradigmitis si se toma en cantidades menores a 25 mg, en caso contrario no hace nada.
* Barbaduranio: cura el Mal de la Guarda Loca, el de la Lambda Loca, y cualquier enfermedad que temine con "Loca", simpre que la dosis supere el largo del nombre de la enfermedad.
* Trumpacio: cura una enfermedad puntual que depende de qué trumpacio se trate. Puede haber Trumpacios para la Paradigmitis, para el Mal de la Guarda Loca y para cualquier otra enfermedad. 

Inventar una nueva droga cuyo efecto curativo dependa de la dosis, pero sin definir una nueva función para ello. Mostrar un ejemplo de remedio que lo contenga.

1. Implementar la función que permita obtener cómo queda una persona luego de tomar un remedio. Algunos de los remedios son:
* Leninol: sólo contiene 50mg de Trumpacio de Capitalismitis. Tiene el valor simbólico de un peso.
* Gariol: 10mg de Trifosfato de Anarcokirchnerismo y 5 gramos de Trumpacio de Mal de la Guarda Loca. Al ser un remedio sin efectos colaterales, sale 500 pesos.

2. Reforzar un remedio N veces: al reforzar un remedio se obtiene un nuevo remedio con el doble de precio pero con todos los componentes con dosis N veces mayores. Si el remedio tiene un solo componente, sin embargo, el refuerzo falla y nos da un remedio sin componentes.

3. Averiguar si es cierto que para una persona un remedio es mejor que otro, lo que ocurre si le cura más enfermedades que el otro. 

4. Saber si un cóctel de remedios es una estafa para una persona: se dice que es una estafa si al tomarlos la persona queda con las mismas enfermedades que tenia antes y además no le alcanza el dinero para comprarlos.

5. Se presenta al hospital el señor que tiene el récord Guinness de la Hipocondría: dice tener enfermedades infinitas. 
* ¿Qué sucede cuando toma un remedio? 
* ¿Podemos saber si un cóctel de remedios es una estafa o no?
