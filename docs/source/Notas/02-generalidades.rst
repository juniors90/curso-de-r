Generalidades acerca de R
==========================

Acerca de este módulo
-------------------------

Este módulo contiene información sobre el uso general de R_. Usted deberá instalar R_ [R]_ en su
computadora y luego seguir las instrucciones de este manual. Este curso está administrado desde
computadoras que utilizan Linux como sistema operativo y las aplicaciones se desarrollan desde la
consola, utilizando instrucciones escritas a través de códigos. No se utiliza ninguna interfaz que
simplifique los procedimientos. Los docentes de este curso conocen los beneficios de trabajar
utilizando este tipo de procedimientos como así también reconocen que el principio puede ser
relativamente difícil. Por esta razón se recomienda paciencia y perseverancia en las primeras clases,
apelando a las consultas necesarias con los docentes del curso. Para usuarios de otros sistemas
operativos, no hay diferencias sustanciales con el uso bajo Linux.

Aclaraciones general
~~~~~~~~~~~~~~~~~~~~~~~

En el texto de cada clase encontrará las explicaciones de los temas y se mantendrá a lo largo de todo
el curso el mismo formato.

Cuando mostremos un comando o rutina, ésta aparecerá luego del caracter "``>``", por ejemplo

.. code-block:: R
    
    > t.test(a)

Usted puede copiar la línea (sin el símbolo "``>``"), pegarla en la línea de comando de R_ y oprimir
enter, de esta manera se ejecutará, la orden establecida por el comando.

Si en una línea de comando aparece el caracter ``#``, esto hace que lo que sigue sea un comentario y
aunque lo pegue en la línea de comando y oprima enter, no se ejecutará ninguna orden. Por ejemplo

.. code-block:: R
    
    > # t.test(a)

Aunque el texto es el mismo, este comando no se ejecutará cuando oprima enter. Pruebe, péguelo en
la línea de comando incluyendo el signo ``#`` y verifíquelo.

Para instalar el programa en su computadora, independientemente del sistema operativo, diríjase a
`https://cran.r-project.org/ <https://cran.r-project.org/>`_

Descargue de allí la opción correspondiente a su sistema operativo. Si es usuario de Linux tiene
varias opciones, una de ellas es ejecutar desde una consola, el siguiente comando

.. code-block:: none
    
    sudo apt install r-base

Con esta acción debería quedar instalado y luego podría arrancar el programa.

Otra opción es desde el centro de software. Utilice la lupa para buscar y escriba ``R-base``.

Automaticamente se seleccionará el software y deberá oprimir install. En la figura siguiente en el
boton figura "``Installed``", ya que R_ se halla instalado


También puede instalarlo desde Synaptic. Una vez dentro de esta aplicación busque *r-base*, marque
la casilla correspondiente y oprima "Apply".

Si es usuario de Windows, siga las instrucciones que se detallan a continuación. Puede haber
algunas variantes según la versión del sistema operativo.

Al momento de instalar R_ en una computadora que posea como sistema operativo a Windows es
necesario en primera medida bajar el programa con la ayuda de cualquier navegador instalado en la
misma. Desde el buscador, colocando R_ o bien "the R_ project" nos encontrara el sitio donde
encontraremos el software. Si observamos encontramos entre las opciones que nos remite a "R_ para
Windows", que nos lleva directamente a los links deseados o bien podemos ingresar a la pagina "the
R_ proyect" donde encontraremos una breve descripción de que es R_, noticias sobre el mismo e
incluidas allí las últimas versiones de R_ que se encuentran aptas para su instalación y uso.

Cliqueando en algún link de las versiones de R_, se genera un archivo "``.exe``" que se deberá ejecutar
para instalar R_ en Windows siguiendo las instrucciones del archivo. En el escritorio se instalará un
acceso directo al programa mediante el cual se ingresa al hacer un doble click.


Arrancar R
~~~~~~~~~~~~~~

Si trabaja en Linux

- Abrir una terminal o consola

- moverse al directorio que se desea trabajar, con comando cd

- tipear R_

- mostrará una bienvenida

Como podemos leer allí ya tenemos las primeras instrucciones.
Al final aparece

``[Previously saved workspace restored]``

¿qué significa?
~~~~~~~~~~~~~~~~~
Que como arrancamos R_ en un directorio determinado, allí ya había datos nuestros y R_ ha cargado
los mismos

al final puede observar::
    
    > 

Esa es la línea de comandos. Allí puede escribir o pegar comandos.

Si deseamos citar en un trabajo algo que hemos realizado con R_, debemos ejecutar la función
``citation()``, como mostramos a continuación. Escriba en la línea de comando lo que se muestra a
continuación::
    
    > citation();

oprima enter y verá como citar a R_. Allí lo encontrará en formato de texto para
procesadores como ``Word`` o ``Writer``, pero también hallará la forma si utiliza
:math:`\LaTeX{}`. Así, el texto que verá será:
    
.. code-block:: R

    To cite R in publications use:
    
      R Core Team (2021). R: A language and environment for statistical
      computing. R Foundation for Statistical Computing, Vienna, Austria.
      URL https://www.R-project.org/.
      
    A BibTeX entry for LaTeX users is
    
      @Manual{,
        title = {R: A Language and Environment for Statistical Computing},
        author = {{R Core Team}},
        organization = {R Foundation for Statistical Computing},
        address = {Vienna, Austria},
        year = {2021},
        url = {https://www.R-project.org/},
      }



Salir del programa
~~~~~~~~~~~~~~~~~~~~

Para salir de R_ y terminar la sesión de trabajo, en la línea de comando deberá escribir

.. code-block:: R

    >q()

Luego de oprimir enter, aparecerá en la pantalla

.. code-block:: R

    > Save workspace image? [y/n/c]:

- Si oprimimos ``y``, se guardarán los objetos creados y el trabajo realizado durante la sesión.
- Si opriminos ``n``, no se salvará nada del trabajo realizado y
- Si opriminos ``c``, cancelamos y volvemos al espacio de trabajo.

Obtener información de la versión de R que utilizamos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Si deseamos conocer qué versión de R_ estamos utilizando, en la línea de comando escribimos

.. code-block:: R
    
    > sessionInfo()

Luego de oprimir enter recibiremos la versión y fecha de lanzamiento de la misma

.. code-block:: R
    
    R version 4.1.0 (2021-05-18)
    Platform: i386-w64-mingw32/i386 (32-bit)
    Running under: Windows 7 (build 7601) Service Pack 1
    
    Matrix products: default
    
    locale:
    [1] LC_COLLATE=Spanish_Argentina.1252  LC_CTYPE=Spanish_Argentina.1252
    [3] LC_MONETARY=Spanish_Argentina.1252 LC_NUMERIC=C
    [5] LC_TIME=Spanish_Argentina.1252
    
    attached base packages:
    [1] stats     graphics  grDevices utils     datasets  methods   base
    
    loaded via a namespace (and not attached):
    [1] compiler_4.1.0 tools_4.1.0

También obtendrá otra información que desestimaremos por el momento.
Este comando será de mucha importancia en futuras clases cuando comencemos a utilizar
bibliotecas para aplicaciones especiales y necesitemos bibliotecas adecuadas a nuestra versión de R_.
Volveremos sobre esto más adelante

Conocer bibliotecas cargadas
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

R_ es un entorno que necesita bibliotecas para ejecutar sus acciones. A fines prácticos y de manera de
optimizar su funcionamiento, R_ solo carga algunas bibliotecas básicas y luego el usuario debe
cargar las bibliotecas que desea. Si no tuviera claro que es una biblioteca, podemos decir de manera
sencilla que es un conjunto de funciones que le permiten realizar acciones específicas. Podemos
pensar una biblioteca como una herramienta para realizar un determinado trabajo. ¿Como saber qué
bibliotecas están cargadas? Podemos hacerlo con cualquiera de los dos comando que se muestran a
continuación

.. code-block:: R
    
    > library()

Esta función nos mostrará las bibliotecas o paquetes instalados en nuestra computadora y la
ubicación de los mismos en nuestro sistema de directorios. De esta lista se sale escribiendo ``q``.
a continuación se muestra la respuesta obtenido al oprimir enter



La columna de la izquierda es el nombre de la biblioteca que tenemos instalada en la dirección que
se indica en la primer línea. En la columna de la derecha nos da una breve explicación o aclaración
sobre el uso de la misma.

La función ``search()`` nos da las bibliotecas cargadas en nuestro espacio de trabajo y que estarán
disponibles para usar.

.. code-block:: R
    
    > search();
    [1] ".GlobalEnv"        "package:stats"     "package:graphics"
    [4] "package:grDevices" "package:utils"     "package:datasets"
    [7] "package:methods"   "Autoloads"         "package:base"
    >

Hagamos una homología, especialmente para quienes por primera vez enfrentan el tema de
bibliotecas, que también llamaremos ``packages`` (paquetes) o ``libraries``.

Con R_ trabajaremos en un sitio de nuestra computadora a la que llamamos espacio de trabajo o
``work space``. Podemos pensar este espacio como si fuera laboratorio o quirófano. Supongamos que
estoy en un laboratorio y tengo que medir la concentración de glucosa en una muestra de sangre.

Las sangre es un objeto de mi laboratorio y para medir la glucosa necesitaré un kit de reactivos y un
espectrofotómetro. Si tengo la sangre, el kit y el espectrofotómetro, mediré la glucosa y obtendré un
valor que será otro objeto de mi laboratorio, el que quedará registrado en algún lado. Es claro que si
no tengo espectrofotómetro, tendré que buscar uno y traerlo al laboratorio. En R_ el
espectrofotómetro y el kit de reactivos serían nuestras bibliotecas, mientras que la sangre serían mis
datos y la glucemia el resultado de aplicar a la sangre las bibliotecas: kit y espectrotometro.


Conocer el directorio de trabajo
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cada vez que iniciemos R_, lo haremos dentro de un directorio, el cual podremos elegir. Una vez
dentro del mismo, si deseamos conocerlo o recordarlos escribiremos

.. code-block:: R

    > getwd();
    [1] "D:/Documents/posgrado/UNR/R"

Esta función nos mostrará el directorio o workspace, en este caso el directorio se llama modulo1,
que se halla dentro de otros directorios

.. code-block:: R

    [1] "D:/Documents/posgrado/UNR/R"

Ver los comando previos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

R_ nos permite tener una archivo con los comandos previos, del día y los históricos, desde que
iniciamos el espacio de trabajo. La función ``history()`` nos permite conocer esto

.. code-block:: R
    
    > history()
    citation();
    sessionInfo()
    library();
    search();
    getwd();
    history();

Esta funcíón nos muestra los últimos :math:`25` comandos usados. Se sale de la visión oprimiendo la letra
q.

Si deseamos ver toda la historia de trabajo dentro del espacio de trabajo debemos agregar a la
función ``history()``, algúnos argumentos.

Es propicio en este momento reflexionar sobre dos términos: función y argumento. Una función es
una palabra o sucesión de caracteres que escribimos en la línea de comando, seguida de paréntesis
que se abren y cierran al final ``(......)``. Una función ejecuta una serie de ordenes preestablecidas por
quien creo dicha función. Es un ejemplo de función ``getwd()`` o ``history()``. Un argumento es un valor
que le damos a la función para que realice algo más orientado. El ejemplo siguiente es adecuado
para entender estos conceptos. Utilizamos la función ``history()`` que nos mostrará las :math:`25` últimas
acciones ejecutadas con R_, que es la forma en que fue diseñada ``history()``. Ahora si le agregamos el
argumento ``max.show=Inf``, la función nos mostrará todos los comandos desde que estamos
trabajando en este espacio de trabajo.

.. code-block:: R
    
        > history(max.show=Inf)

Nos muestra todos los comando y se retorna a la línea de comandos oprimiendo la letra ``q``.

Recuerde que si desea dejar durante el trabajo comentarios puede hacerlo fácilmente anteponiendo a
su escrito el símbolo ``#``.

Por ejemplo, si cuando arranca una sesión de R puede dejar un comentario como se muestra a
continuación

.. code-block:: R
    
    > # sesión del día 18/9/18. Día soleado, agradable para una sesión de R.
    > # Objetivos: análisis multivariado de datos de la base de datos aguas.
    > # Se realizarán PCA y MCA de los datos en búsqueda de respuestas a los
    > # interrogantes de la reunión anterior. ¿Hay relación entre los
    > # componentes químicos del agua y la provincia de origen? ¿Las personas
    > # están satisfechas con el agua que consumen y el precio que pagan por ella?
    > # este texto quedará en un archivo en su espacio de trabajo, junto con
    > # todo los análisis y resultados hallados.

Hagamos un poco más de reflexión antes de seguir. Trabajar con R,_ como dijimos es como trabajar
en un laboratorio. Compararemos R_ con un laboratorio en dos columnas

+--------------------------------------------------------+--------------------------------------------------+
| Laboratorio                                            | R_                                               |
+========================================================+==================================================+
| Un laboratorio tiene una ubicación y un lugar          | Cuando trabajamos con R_ estaremos en un sitio   |
| físico donde funciona: calle - número - edificio piso. | que llamamos workspace o espacio de trabajo.     |
|                                                        |                                                  |
|                                                        | Es en realidad un directorio dentro de nuestra   |
|                                                        | computadora. En este espacio de trabajo se       |
|                                                        | hallarán objetos de R_.                          |
+--------------------------------------------------------+--------------------------------------------------+
| En un laboratorio utilizamos equipos de                | En R contamos con funciones que realizan tareas  |
| diferentes tipos, que realizan tareas específicas.     | específicas. Habitualmente las reconocemos       |
| Por ejemplo espectrofotómetros, centrífugas, etc       | porque son una palabra seguida de (). Con estas  |
|                                                        | funciones creamos, modificamos y operamos con    |
|                                                        | los objetos.                                     |
+--------------------------------------------------------+--------------------------------------------------+
| Es habitual que los equipos de laboratorio los         | En R_ aquellas funciones que tienen objetivos    |
| tengamos agrupados por box, mesadas, sectores, para    | comunes se agrupan en paquetes o bibliotecas.    |
| facilitar el trabajo. Por ejemplo un contador de       | Por ejemplo el paquete ``pROC``, contiene        |
| centelleo estará en un cuarto para radioisótopos y     | numerosas funciones que permite diseñar,         |
| y seguramente en el mismo sitio existirá otro          | analizar y comparar curvas ``ROC``.              |
| instrumental con el mismo fin como ser contenedores    |                                                  |
| con blindaje, equipo de descontaminación, medidores de |                                                  |
| radiación, etc                                         |                                                  |
+--------------------------------------------------------+--------------------------------------------------+
| En un laboratorio tendremos muestras, reactivos,       | En R_ tendremos objetos que constituyen nuestros |
| mediciones que hemos realizado sobre ellas y           | datos, los análisis que realizamos sobre ellos   | 
| análisis de estos datos.                               | y sus resultados. Estos objetos están en el      |
|                                                        | espacio de trabajo y los manipularemos con las   |
|                                                        | funciones                                        |
+--------------------------------------------------------+--------------------------------------------------+
| Los instrumentos de un laboratorio pueden tener        | En R_ tenemos funciones y estas funciones pueden |
| diferentes modos de uso. Por ejemplo una               | ser adecuadas a diferentes situaciones con el    |
| centrífuga podemos utilizarla a temperatura            | uso de argumentos. Por ejemplo la función        |
| ambiente o refrigerada. También podremos               | ``rect(2,2,3,3)`` dibuja un rectángulo negro con |
| trabajar a diferentes velocidades. Esta                | vértices opuestos en los puntos ``(2,2)`` y      |
| versatilidad la logramos porque disponemos de          | ``(3,3)``. En cambio ``rect(2,2,3,3,col="red)``. |
| controles que nos habilitan para realizar los          | Lo hace de color rojo. En este caso ``col``, es  |
| cambios.                                               | un argumento de la función ``rect()``.           |
+--------------------------------------------------------+--------------------------------------------------+

Sigamos viendo algunas funciones básicas de R_.

Ver el espacio de trabajo
~~~~~~~~~~~~~~~~~~~~~~~~~~

Con la función ``search()``, como vimos anteriormente puedo ver las bibliotecas cargadas en mi
espacio de trabajo. Si se desean ver los objetos que se hallan en el espacio de trabajo se usa el
siguiente código

.. code-block:: R
    
    >ls()

obtendrá la misma información si escribe

.. code-block:: R
    
    > objects()

muestra los objetos, es decir estructuras que almacenan datos o análisis de éstos.

Introducir datos en R
~~~~~~~~~~~~~~~~~~~~~~~~

Los datos y los resultados se almacenan en R_ en lo que llamamos objetos. Dentro de los objetos
para almacenar datos, los más comunes son

- vectores
- data.frame
- matrices

Los objetos también pueden almacenar resultados de análisis realizados.

- **vectores**

Un vector es un conjunto de varios datos. Por ejemplo supongamos que tuviera la glucemia de :math:`4`
ratas, podría guardar ellas en un vector. También se puede guardar en un vector los nombres y
apellidos de los alumnos de un curso o las escala de grises de los pixeles de una imagen.
Veamos algunos tipos de vectores, como crearlos y verlos.

- **Vectores con elementos numéricos**

A continuación desarrollamos como crear un vector con elementos numéricos. Supongamos que
tenemos una serie de datos de tiempo: :math:`1seg`, :math:`2seg`, :math:`3seg`, :math:`\dots`, :math:`5seg`.
Con estos datos creamos un vector que almacena los números. El código para crear el vector es

.. code-block:: R
    
    > a<-c(1,2,3,4,5)

"``a``" es el nombre con que se identifica el objeto y el mismo tiene :math:`5` números. Siempre que desee
crear un objeto deberá asignarle un nombre, y detallar los elementos del vector dentro de un
paréntesis antecedido por la letra ``c``. Veamos algunos ejemplos

.. code-block:: R
    
    > horasdesol<-c(3,5,2,6,7)

también puede definirlo utilizando un signo ``=``

.. code-block:: R
    
    > horasdedescanso=c(3,5,2,6,7)

El nombre de un objeto tiene algunas restricciones que veremos más adelante, pero las más
importantes son que: no puede comenzar con números, no puede tener espacios y otras menos
comunes.

Una vez que hemos creado un objeto, este quedará depositado en el espacio de trabajo, cosa que
podré verificar con la función ``ls()``.

.. code-block:: R

    > ls()
    [1] "a"               "horasdedescanso" "horasdesol"


me mostrará una lista de objetos y allí debe estar el que he creado.
También podemos pedir un detalle de este objeto con

.. code-block:: R

    > summary(a);
       Min. 1st Qu.  Median    Mean 3rd Qu.    Max.
          1       2       3       3       4       5

en este caso no está mostrando el mínimo, el máximo, la mediana y los percentilos :math:`25` y :math:`75\%` de los
valores numéricos del vector.

Podemos también ver que tipo de datos tiene el objeto. La función ``mode()`` permite obtener esta
información

.. code-block:: R

    > mode(a);
    [1] "numeric"

podemos también pasar los datos a otro objeto "``b``" con la función ``assign()``. Con el comando
siguiente creamos un objeto llamado ``b``, que tendrá los mismos datos que el objeto a

.. code-block:: R
    
    > assign("b",a)

De una manera más sencilla sin utilizar ``assign()`` se puede lograr con la siguiente línea de comando

.. code-block:: R
    
    > b<-a

como podemos ver ahora ``b`` también tiene la misma información

.. code-block:: R

    > b;
    [1] 1 2 3 4 5


- **vectores con elementos string**

Un ``string`` es una cadena de caracteres, por ejemplo: ``perro``, ``aa``, ``b``, ``er45z``, ``aar cec``, etc. Si se desea crear
el objeto del tipo vector de nombre '``myvector``', con elementos string, es decir elementos que sean
combinaciones de letras: por ejemplo las letras con la que identifique cinco ratas de mis
experimentos , aplicaremos el siguiente código.

.. code-block:: R
    
    > myvector<-c("x","y","z","u","v")



Es importante tener en cuenta que los elementos de un vector que sean strings deben introducirse
entre comillas (``"..."``). También puede utilizarse el tilde (``'.......'``).

.. warning::
    
    No debe combinar ``" "`` y ``' '``, en la creación de un vector. Utilice una u otra.

Todos los comandos que necesiten escrituras entre comillas (``"......"``) pueden escribirse entre tildes
(``'....'``). La segunda opción es más ventajosa desde el punto de vista de eficiencia en el sentido que el
tilde se utiliza sin oprimir mayúscula, mientras que la comilla requiere oprimir mayúscula y por lo
tanto involucra dos teclas, aumentando el tiempo utilizado y la probabilidad de error. Por lo tanto el
vector ``myvector``, podría escribirse

.. code-block:: R
    
    > myvecto<-c('x','y','z','u','v')

y puedo ver sus propiedades con los comandos, si lo deseara

.. code-block:: R
    
    > summary(myvecto)
    > mode(myvecto)

Algunas funciones y operaciones con vectores (también aplicable a otros objetos)
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- La función ``max()``:

.. code-block:: R
    
    max(a)

Busca el elemento más grande del vector ``a``:

.. code-block:: R
    
    > max(a)
    [1] 5

- Función ``min()``:

.. code-block:: R
    
    > min(a)

Busca el elemento más chico del vector

.. code-block:: R
    
    > min(a)
    [1] 1

- La función ``range()``:

.. code-block:: R
    
    range(a)

Busca el máximo y mínimo del vector ``a``, o sea el rango

.. code-block:: R
    
    > range(a)
    [1] 1 5

- Función ``length()``:

.. code-block:: R
    
    > length(a)

Indica el número de elementos que forman el vector ``a``

.. code-block:: R
    
    [1] 5

- Función ``sum()``:

.. code-block:: R
    
    > sum(a)

Calcula la suma de los componentes del vector ``a``

.. code-block:: R

    [1] 15

- Función ``prod()``:

.. code-block:: R
    
    > prod(a)

Muestra el producto de los componentes del objeto

.. code-block:: R
    
    [1] 120

- La función ``mean()``:

.. code-block:: R
    
    > mean(a)

Calcula la media de los elementos del vector ``a``

.. code-block:: R
    
    > mean(a)

- Función ``median()``:

.. code-block:: R
    
    median(a)

Calcula la mediana de los elementos del vector

.. code-block:: R
    
    > median(a)
    [1] 3

- Función ``sd()``:

.. code-block:: R
    
    sd(a)

Calcula es desvío estándar de los datos del vector ``a``

.. code-block:: R
    
    > sd(a)
    [1] 1.581139

- Función ``var()``:

.. code-block:: R
    
    > var(a)

Calcula la variancia de los elementos del vector

.. code-block:: R
    
    > var(a)
    [1] 2.5

- Función ``sort()``:

.. code-block:: R
    
    > sort(a)

Ordenar datos de un objeto. Si le agregamos es argumento decreasing, nos permite indicarle si el
ordenamiento requerido es en forma ascendente o descendente.

.. code-block:: R
    
    sort(a,decreasing= T or F)

Veamos el vector a creado anteriormente

.. code-block:: R
    
    > a
    [1] 1 2 3 4 5

vemos que está ordenado en forma creciente. Podemos ordenarlo en forma decreciente

.. code-block:: R
    
    > sort(a,decreasing=T)
    [1] 5 4 3 2 1


Crear vector con secuencia numéricas y valores repetidos
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- La función ``seq()`` permite crear secuencias numéricas. Ejecutemos el siguiente comando

.. code-block:: R
    
    > x<-seq(1,33,1) 

Esta función crea un vector (en este caso lo llamamos ``x``) que contiene
los números entre :math:`1` y :math:`33` de a :math:`1`.

.. code-block:: R
    
    > x
    [1] 1 2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32
    33

Si ejecutamos

.. code-block:: R
    
    > seq(1,33,1)

se generará lo mismo, pero no lo estamos asignando ``a`` un objeto, por lo tanto no quedará dicho
vector almacenado en el espacio de trabajo, aunque si lo veremos en la pantalla.

- La función ``rep()``, permite generar también vectores pero incluye repeticiones. Veamos un ejemplo

.. code-block:: R
    
    > quince<-rep(15,37)

- La función ``rep()``, en este caso ha creado un vector con el número :math:`15` repetido :math:`37` veces

.. code-block:: R
    
    > quince
    [1] 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15 15
    [26] 15 15 15 15 15 15 15 15 15 15 15 15

Redondeo y otros
~~~~~~~~~~~~~~~~~~

R_ tiene grandes recursos para este tipo de procedimientos. Veamos algunos ejemplos ilustrativos
Ya tenemos creado un vector ``a``, que podemos ver escribiendo

.. code-block:: R
    
    > a
    [1] 1 2 3 4 5

creamos un vector que llamamos ``d``

.. code-block:: R
    
    > d<-a/10

en este caso ``d`` está formado por los elementos de ``a`` pero todos divididos por :math:`10`.

.. code-block:: R
    
    > d
    [1] 0.1 0.2 0.3 0.4 0.5

- La funcion ``ceiling()``:

.. code-block:: R
    
    > ceiling(d)
    [1] 1 1 1 1 1

``ceiling()`` tomó cada valor de vector ``d`` y regresó el primer entero no menor que el número o bien
dicho también el menor entero superior a cada número del vector

- la función ``floor()``:

.. code-block:: R
    
    > floor(d)
    [1] 0 0 0 0 0

``floor()``, toma los valores del vector ``d`` y retorna el mayor entero posible, pero no superior que el
valor original.


- La función ``trunc()``:

.. code-block:: R

    > trunc(d)
    [1] 0 0 0 0 0

``trunc()`` retorna el número entero que resulta de haber truncado el valor en la coma.

- La función ``round()``:

.. code-block:: R
    
    > round(d,digits=0)
    [1] 0 0 0 0 0

``round()``, con el argumento ``digits=0``, redondea cada número del vector ``d``, sin decimales.

En cambio si utilizamos el argumento ``digits=1``

.. code-block:: R
    
    > round(d,digits=1)
    [1] 0.1 0.2 0.3 0.4 0.5

redondea los números con un decimal.


Generador números aleatorios
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- La función ``runif()``:

.. code-block:: R
    
    > runif(10,0,1)

``runif()`` ha generado :math:`10` números aleatorios entre :math:`0` y :math:`1`.

.. code-block:: R
    
    [1] 0.8304301 0.3168486 0.9059344 0.5761408 0.4335628 0.9095313 0.1411549
    [8] 0.1893361 0.8885673 0.4636167

Una características de las funciones de R_ es que se pueden anidar, es decir aplicar una función al
resultado de otra función. En el ejemplo siguiente se anidan las funciones ``trunc`` y ``runif``

.. code-block:: R
    
    > trunc(runif(10,0,1)*10)

En este caso ``runif()`` genera :math:`10` números aleatorios entre :math:`0` y :math:`1` y luego la
función ``trunc()``, trunca los :math:`10` números que previamente fueron multiplicados por :math:`10`.

.. code-block:: R

    [1] 2 1 5 4 9 0 9 9 2 0
    > floor(runif(10,0,1000))
    [1] 293 541 693 357 337 860 953 405 810 948

¿Se anima a deducir que hicieron las funciones anidadas?.


Visualizar espacio de trabajo
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Si deseamos ver los objetos que se hallan en el espacio de trabajo podemos ejecutar algunas de las
siguientes funciones. Las dos primeras son equivalentes.

.. code-block:: R
    
    > ls()
    > objects()

podemos agregar el argumento sorted, el que podrá tener valores ``TRUE`` o ``FALSE``. En tal caso los
ordenará o no alfabéticamente.

.. code-block:: R
    
    > objects(sorted= FALSE)

en este último caso, si es argumento sorted toma el valor ``T`` (``TRUE``), estarán ordenados
alfabéticamente. En caso que sorted tome el valor ``F`` (``FALSE``), estarán en el orden en que fueron
creados.

Borrar el objeto
~~~~~~~~~~~~~~~~~

A menudo deseamos eliminar un objeto del espacio de trabajo, para ellos contamos con las
funciones ``rm()`` y ``remove()``. Supongamos que deseamos eliminar el objeto ``a``, que creamos durante la
clase.

.. code-block:: R
    
    > rm(a) 

elimina el elemento ``a``

.. code-block:: R
    
    > remove(a)

la función ``remove()`` tiene el mismo efecto que ``rm()``.

La combinación de la función ``rm()`` con ``ls()`` con el siguiente formato

.. code-block:: R
    
    > rm(list=ls())

borra todos los objetos del espacio de trabajo.

Si por error borramos algo, al salir del espacio de trabajo nos pedirá si queremos salvar los cambios
y en dicho caso será conveniente colocar "``n``"

Tenga en cuenta que si borra un objeto no existe "``undo``".


.. _R: https://www.r-project.org/


