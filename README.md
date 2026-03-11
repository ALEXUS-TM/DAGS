# Sistema de Venta de Videojuegos

## Descripción
Este sistema permite registrar ventas de videojuegos según el tipo de consola y el valor individual de cada juego.  
El sistema calcula el valor total de ventas realizadas durante el día y almacena cada registro.

---

## Historia de Usuario

**Título:** Registro de ventas de videojuegos

**Como:** Vendedor de videojuegos  
**Quiero:** Registrar cada venta indicando el tipo de consola y el valor del juego  
**Para:** Llevar control de las ventas realizadas durante el día

---

## Criterios de aceptación

- El sistema debe permitir registrar ventas de videojuegos.
- El tipo de videojuego puede ser:
  - PS4
  - PS5
  - NS
- El sistema debe guardar el valor de cada videojuego vendido.
- El sistema debe calcular el total vendido durante el día.
- El sistema debe almacenar el registro de cada venta.

---

# Venta de Videojuegos

Se propone diseñar software en el que se calcule el número de videojuegos vendido en la tienda según el tipo y el valor individual. La tienda vende sus videojuegos dependiendo de si el juego vendido es de **PS4, PS5 o NS** y del valor individual de cada uno. El software debe registrar la venta individual y almacenarla en el registro para al final sumar y dar la venta del día.

## Aclaraciones

- El valor de la venta individual puede variar con respecto a las demás.
- El cálculo corresponde únicamente al valor bruto.
- La aplicación debe calcular la venta individual y la del día para almacenarla.
- Los datos de venta deben almacenarse para llevar un registro.

---

# Historia de usuario

**Título:** Cálculo y registro de ventas  

**Como:** Vendedor de juegos.  

**Quiero:** Registrar cada venta indicando el tipo de videojuego (PS4, PS5 o NS) y su valor individual.  

**Para:** Calcular automáticamente el total vendido en el día y mantener un registro organizado de las ventas realizadas.

## Descripción

El sistema permitirá registrar ventas individuales de videojuegos, almacenando el tipo de consola y el valor de cada venta. Con esta información, el software calculará tanto el valor de cada venta como el total acumulado del día, facilitando el control diario de ingresos.

## Criterios de aceptación

El sistema debe permitir registrar una venta indicando:

- Tipo de videojuego: **PS4, PS5 o NS**
- Valor individual del videojuego

El sistema debe calcular automáticamente:

- El valor de cada venta registrada
- El total acumulado de ventas del día

Además:

- El sistema debe almacenar los datos de cada venta para consulta posterior.
- El sistema solo calculará valores brutos, sin impuestos ni descuentos.
- El sistema debe permitir registrar múltiples ventas durante el día.

---

# Diagrama UML: Caso de Uso
<img width="889" height="497" alt="image" src="https://github.com/user-attachments/assets/a5b75587-cdfd-4611-9003-24f2773fbb52" />


## Caso de Uso: Registrar Venta

**Nombre:** Registrar venta de videojuego  

**Actores:** Vendedor  

**Propósito:** Permitir al vendedor registrar la venta de un videojuego indicando el tipo de consola y su valor, para que el sistema calcule y actualice el total de ventas del día y almacene el registro.

## Curso de eventos

1. El vendedor selecciona la opción **Registrar venta**.
2. El sistema solicita el tipo de consola (**PS4, PS5 o NS**) y el valor del videojuego.
3. El vendedor ingresa la información solicitada.
4. El sistema valida que los datos sean correctos.
5. El sistema calcula el valor de la venta.
6. El sistema almacena la venta en el registro.
7. El sistema actualiza el total de ventas del día.
8. El sistema confirma que la venta fue registrada exitosamente.

## Postcondición

- La venta queda registrada en el sistema.
- El total de ventas del día se actualiza correctamente.
- La información queda disponible para consultas posteriores.

---

# Pseudocódigo
    DEFINIR listaVentas COMO LISTA VACÍA
    DEFINIR totalDia COMO REAL ← 0
    DEFINIR opcion COMO ENTERO

    REPETIR

    MOSTRAR "==============================="
    MOSTRAR "      SISTEMA DE VENTAS        "
    MOSTRAR "==============================="
    MOSTRAR "1. Registrar venta"
    MOSTRAR "2. Consultar total del día"
    MOSTRAR "3. Mostrar registro de ventas"
    MOSTRAR "4. Salir"
    LEER opcion

    SEGÚN opcion HACER

        CASO 1:

            DEFINIR tipo COMO CADENA
            DEFINIR valor COMO REAL
            DEFINIR venta COMO ESTRUCTURA

            MOSTRAR "Ingrese tipo de videojuego (PS4, PS5, NS): "
            LEER tipo
            tipo ← MAYUSCULAS(tipo)

            SI tipo ≠ "PS4" Y tipo ≠ "PS5" Y tipo ≠ "NS" ENTONCES
                MOSTRAR "Error: Tipo de consola inválido."
            SINO

                MOSTRAR "Ingrese valor del videojuego: "
                LEER valor

                SI valor <= 0 ENTONCES
                    MOSTRAR "Error: El valor debe ser mayor que 0."
                SINO

                    venta.tipo ← tipo
                    venta.valor ← valor

                    AGREGAR venta A listaVentas
                    totalDia ← totalDia + valor

                    MOSTRAR "Venta registrada correctamente."

                FIN SI

            FIN SI

        FIN CASO


        CASO 2:
            MOSTRAR "Total acumulado del día: ", totalDia
        FIN CASO


        CASO 3:

            SI listaVentas ESTÁ VACÍA ENTONCES
                MOSTRAR "No hay ventas registradas."
            SINO
                PARA CADA venta EN listaVentas HACER
                    MOSTRAR "Tipo: ", venta.tipo
                    MOSTRAR "Valor: ", venta.valor
                    MOSTRAR "--------------------------"
                FIN PARA
            FIN SI

        FIN CASO


        CASO 4:
            MOSTRAR "Cerrando sistema..."
        FIN CASO


        OTRO CASO:
            MOSTRAR "Opción inválida."
        FIN CASO

    FIN SEGÚN

    HASTA QUE opcion = 4

<img width="691" height="1007" alt="image" src="https://github.com/user-attachments/assets/6c48eea2-2b92-4a59-9dd0-36aff1527f81" />
