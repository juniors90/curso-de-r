Continuación uso de data.frames
=================================

Reemplazo de valores de un data.frame
-----------------------------------------

Trabajaremos con la tablaR141 de la planilla de cálculo ``tablaR1-4.ods/xls``.
Introdúzcala en su espacio de trabajo. Para ello utilice el siguiente código
y lo aprendido en clases anteriores

.. code-block:: R

    > tablaR141<-read.table("clipboard",header=TRUE,dec=",",sep="\t")
    > tablaR141
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

Head
----------

La función ``head()`` nos permite obtener rápidamente información
sobre el ``data.frame``, particularmente nos da las columnas con sus
nombres y los primeros elementos. Se complementa con la función ``summary()``.
El número luego de la coma indica la cantidad de filas que se desean ver.
Para el ejemplo siguiente le pedimos ver solo :math:`2` filas.

.. code-block:: R

    >  head(tablaR141,2)
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3

Si no se especifica número de filas, la función muestra :math:`5` filas
por defecto

.. code-block:: R

    > head(tablaR141)
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5


Nombre de columnas
-------------------

La función ``names()`` nos da solo los nombre de las columnas del ``data.frame``.
Seguimos con el ``data.frame`` ``tablaR141``, que mostramos nuevamente a continuación


.. code-block:: R
    
    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

ahora veamos solo los nombres de las columnas

.. code-block:: R

    > names(tablaR141);
    [1] "peso"      "minutos"   "atributo"  "atributo2"

Esta función no es útil para tablas pequeñas donde podemos ver todas las columnas.
Pero se torna muy útil cuando las tablas son muy grandes.

Transform
--------------

La función ``transform()`` sirve para transformar los valores de una
columna de un ``data.frame``, aplicando alguna función. Si la ``tablaR141`` es

.. code-block:: R
    
    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

el código siguiente, transformará y reemplazará la columna peso por el logaritmo del peso.

.. code-block:: R
    
    > transform(tablaR141,peso=log(peso))
          peso minutos atributo atributo2
    1 3.135494       1        a     tubo3
    2 3.139833       1        a     tubo3
    3 3.148453       1        b     tubo4
    4 2.602690       1        c     tubo5
    5 2.602690       1        b     tubo5

en el código anterior, la columna peso se modificó por aplicación del logaritmo,
pero si pedimos el ``data.frame``, podemos ver que no se ha modificado el
valor del peso.

.. code-block:: R
    
    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

En cambio sí se modificará si la función anterior la asignamos nuevamente al
objeto ``tablaR141`` como vemos a continuación. Es decir si sobre escribimos
el data.frame ``tablaR141`` con el resultado hallado con ``transform()``
tablaR141<-transform(tablaR141,peso=log(peso));
tablaR141;

.. code-block:: R

    > tablaR141<-transform(tablaR141,peso=log(peso));
    > tablaR141;
          peso minutos atributo atributo2
    1 3.135494       1        a     tubo3
    2 3.139833       1        a     tubo3
    3 3.148453       1        b     tubo4
    4 2.602690       1        c     tubo5
    5 2.602690       1        b     tubo5

Tenga presente que si aplicó el código anterior no tiene más el peso
sino el logaritmo del peso en la columna número ``1`` del ``data.frame``.
Para seguir con la tabla original deberá introducirla nuevamente.

Eliminar/seleccionar/reordenar filas y/o columnas
--------------------------------------------------

eliminar/seleccionar filas
~~~~~~~~~~~~~~~~~~~~~~~~~~

Sigamos trabajando con el ``data.frame`` ``tablaR141``. Si lo ha modificado
puede volver a introducirlo, con el código ya aplicado

.. code-block:: R

    > tablaR141<-read.table("clipboard",header=TRUE,dec=",",sep="\t")
    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

Para varias acciones siguientes tiene que tener en cuenta que si
escribimos el nombre del ``data.frame`` seguido de corchete, por ejemplo
``tablaR141[filas,columnas]``, entre corchete se indica antes de la coma
las filas. que se desean seleccionar y después de la coma, las columnas
a seleccionar.

Por ejemplo si en el ``data.frame`` ``tablaR141`` deseamos eliminar la fila ``5``,
utilizaremos el siguiente código

.. code-block:: R

    > tablaR141[c(1:4),]
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5

como puede ver nos quedaron las filas ``1``, ``2``, ``3`` y ``4`` y
todas las columnas. Al no especificar nada después de la coma, dentro
del corchete, se interpreta que no se elimina ninguna columna.
Con el código anterior eliminamos una fila, pero como no lo asignamos
al ``data.frame``, si bien vemos los cambios, el data frame no se ha
modificado. Siempre recuerde que si quiere que los cambios sean guardados
reemplazando el ``data.frame`` original debe escribir el código y
reasignarlo al mismo objeto. El siguiente sería el código a utilizar

.. code-block:: R

    > tablaR141<-tablaR141[c(1:4),];
    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5

Si deseáramos mantener las filas ``1``, ``3``, ``4`` y ``5``,
pero todas las columnas, escribiríamos

.. code-block:: R

    > tablaR141[c(1,3:5),];
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

Los códigos anteriores seleccionaron filas, pero los datos no han
quedado grabados en ningún objeto. En cambio, si quisiéramos las
filas ``1`` y ``2`` además de las ``4`` y ``5``, pero además quisiéramos
guardarlas en otro objeto creamos un ``data.frame`` ``"tabla2"``


.. code-block:: R

    > tabla2<-tablaR141[c(1:2,4:5),]
    > tabla2;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

Se debe notar que las filas mantienen los números originales.
Si bien esto puede ser una ventaja a la hora de trabajar puede
ser una complicación a la hora de ejecutar scripts (tema que
veremos en módulos posteriores).

Si se desea reasignar números de filas, de manera que estos sean
correlativos se puede utilizar la función ``row.names()`` con el
siguiente código que asigna a los números de las filas los datos
de un vector numérico que va desde 1 hasta el número de filas del
``data.frame``, en este caso ``4``.

.. code-block:: R

    > row.names(tabla2)<-c(1:4);
    > tabla2;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 13.5       1        c     tubo5
    4 13.5       1        b     tubo5

Vemos que la primer columna ahora tiene números correlativos.

Es útil en estos casos utilizar la función ``nrow()``, que cuenta
por nosotros el número de filas de un ``data.frame``. Es especialmente
útil si tenemos un ``data.frame`` con un gran número de filas. En lugar de
utilizar el número ``4``, para indicarle la última fila utilizamos
``nrow(tabla2)``, quedando el código como se indica a continuación

.. code-block::

    > row.names(tabla2)<-c(1:nrow(tabla2))
    > tabla2;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 13.5       1        c     tubo5
    4 13.5       1        b     tubo5

Eliminar/seleccionar columnas
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Para seleccionar columnas se sigue el mismo procedimiento, teniendo
en cuenta que las columnas que se desean seleccionar se especifican
después de la coma, dentro de los corchetes. Si antes de la coma no
se pone nada es porque se desean seleccionar todas las filas. Veamos
nuevamente la ``tablaR141``


.. code-block:: R

    > tablaR141
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

Si deseamos seleccionar todas las filas, pero solo las
columnas ``1`` y ``2`` escribiremos


.. code-block:: R

    > tablaR141[,c(1:2)]
      peso minutos
    1 23.0       1
    2 23.1       1
    3 23.3       1
    4 13.5       1
    5 13.5       1

de la misma manera si deseamos las columna ``1``, ``2`` y ``4`` y todas
las filas, escribiremos

.. code-block:: R
    
    > tablaR141[,c(1:2,4)];
      peso minutos atributo2
    1 23.0       1     tubo3
    2 23.1       1     tubo3
    3 23.3       1     tubo4
    4 13.5       1     tubo5
    5 13.5       1     tubo5

Eliminar/seleccionar filas y columnas con condiciones
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Muchas veces no solo queremos seleccionar ciertas filas y columnas,
sino que deseamos filas donde se cumplan ciertas condiciones.
Continuemos con el ``data.frame`` ``tablaR141``

.. code-block:: R

    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4
    4 13.5       1        c     tubo5
    5 13.5       1        b     tubo5

Supongamos que deseamos todas las filas en las que se cumpla que el
``peso>20``. Por otro lado queremos todas las columnas, para ello
utilizamos el mismo mecanismo pero en antes de la coma, indicamos
la columna y la condición, con el siguiente código

.. code-block:: R

    > tablaR141[tablaR141$peso>20,];
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        b     tubo4

Veamos una selección más sofisticada y exigente. Deseamos todas
las columnas, pero solo aquellas filas que simultáneamente tienen
``peso>23`` y la columna ``atributo=a``. Es obvio de mirar la tabla
que mayor que ``23`` son las filas ``2`` y ``3``, pero si
simultáneamente queremos que atributo valga a, nos quedaremos solo
con la fila ``2``. Comprobemos si el código siguiente lo hace

.. code-block:: R

    > tablaR141[tablaR141$peso>23 & tablaR141$atributo=="a",];
      peso minutos atributo atributo2
    2 23.1       1        a     tubo3

.. important::
    
    Si usted utiliza como en el código anterior ``tablaR141$atributo=="a"``.

    El doble igual (``==``) nos permite buscar en que filas la columna atributo
    tiene el valor ``"a"``. Es decir que el signo ``==`` se utiliza para evaluar una
    condición o realizar una comparación.

Si hubiera escrito

.. code-block:: R
    
    > tablaR141$atributo="a";

estará reemplazando en la columna atributo sus elementos por el valor "a", como podemos
comprobar a continuación.

.. code-block:: R

    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        a     tubo4
    4 13.5       1        a     tubo5
    5 13.5       1        a     tubo5


recuerde que este código modificó el ``data.frame``. Deberá reintroducir
``tablaR141`` si desea trabajar con los valores originales.

Reordenar filas y/o columnas
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Cuando deseamos reordenar filas o columnas, básicamente utilizamos las
mismas herramientas que para seleccionar filas o columnas vistas
anteriormente. Supongamos el ``data.frame`` ``tablaR141``

.. code-block:: R
    
    > tablaR141;
      peso minutos atributo atributo2
    1 23.0       1        a     tubo3
    2 23.1       1        a     tubo3
    3 23.3       1        a     tubo4
    4 13.5       1        a     tubo5
    5 13.5       1        a     tubo5

con la función names() podemos ver los nombres de las columnas

.. code-block:: R

    > names(tablaR141)
    [1] "peso"      "minutos"   "atributo"  "atributo2"

Supongamos que deseamos reorganizar la tabla dejando primero ``atributo2``
(columna ``4``), luego ``atributo`` (columna ``3``), ``peso`` (columna ``1``) y
finalmente ``minutos`` (columna ``2``).

A continuación reordenaremos las columnas, colocándolas en el orden ``4``, ``3``,
``1`` y ``2``. Por otra parte para no afectar el ``data.frame`` original lo
asignamos al ``data.frame`` que llamamos ``tabla2``

> tabla2<-tablaR141[,c(4,3,1,2)]


.. code-block:: R
    
    > tabla2<-tablaR141[,c(4,3,1,2)];

veamos ``tabla2``

.. code-block:: R
    
    > tabla2;
      atributo2 atributo peso minutos
    1     tubo3        a 23.0       1
    2     tubo3        a 23.1       1
    3     tubo4        a 23.3       1
    4     tubo5        a 13.5       1
    5     tubo5        a 13.5       1