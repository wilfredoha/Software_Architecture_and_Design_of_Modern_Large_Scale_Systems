# 📨 Message Brokers

## 📌 ¿Qué es un Message Broker y por qué lo necesitamos?

Un **message broker** es un bloque fundamental en arquitecturas asincrónicas. Su principal función es desacoplar el emisor del receptor, permitiendo que cada uno trabaje de forma independiente sin necesidad de una conexión activa simultánea.

En arquitecturas **sincrónicas**, tanto el emisor como el receptor deben estar disponibles al mismo tiempo. Esto presenta varios inconvenientes:

* Ambos servicios deben estar en línea y funcionando.
* Si el receptor se cae, se pierde la transacción.
* No hay forma de absorber picos de tráfico de manera eficiente.

Imagina un sistema de venta de entradas:
* Un servicio recibe solicitudes de compra.
* Otro servicio procesa la reserva, cobra al usuario y envía confirmaciones.

Si todo esto se hace sincrónicamente, el usuario debe esperar a que toda la operación termine, lo cual es ineficiente y frágil ante fallos.

## 🧱 ¿Qué es un Message Broker?

Un **message broker** es un componente de software que permite el envío de mensajes entre servicios utilizando una **estructura de datos tipo cola (queue)**. A diferencia de un balanceador de carga, **no está expuesto al exterior**, sino que opera dentro del sistema.

Sus funcionalidades incluyen:

* Almacenamiento temporal de mensajes.
* Enrutamiento de mensajes.
* Transformación y validación de mensajes.
* Balanceo de carga interno.
* Implementación del patrón **publish-subscribe**.

## 🧩 Desacoplamiento total entre servicios

Con un message broker:

* El servicio emisor no necesita saber si el receptor está disponible.
* Los mensajes se almacenan hasta que el receptor los consuma.
* Podemos dividir un proceso complejo en etapas, cada una comunicándose mediante colas.

Por ejemplo:
* El frontend recibe la orden de compra.
* Envía un mensaje a la cola de pedidos.
* Otro servicio lo procesa, y así sucesivamente.

## 📊 Capacidad de absorción de picos de tráfico

En un escenario de tráfico elevado (como promociones), el frontend puede:

* Restar inventario en una base de datos.
* Enviar los pedidos a una cola.

Luego, los servicios que procesan pedidos los van atendiendo cuando haya capacidad, **sin perder ningún mensaje** y sin saturar el sistema.

## 📢 Patrón Publish-Subscribe

Con este patrón:

* Varios servicios publican eventos en un canal.
* Varios servicios pueden suscribirse a ese canal y reaccionar.

Ejemplo:
* Cuando se realiza una compra, se publica un evento.
* Un servicio analiza patrones de compra.
* Otro envía notificaciones push.
* Otro solicita una encuesta de satisfacción.

Todo esto sin modificar el sistema original.

## 🏆 Atributos de calidad que aporta un Message Broker

* **Alta disponibilidad**: permite que los servicios funcionen incluso si otros están temporalmente fuera de línea.
* **Tolerancia a fallos**: los mensajes no se pierden.
* **Alta escalabilidad**: las colas actúan como búfer para absorber picos.
* **Menor acoplamiento**: facilita el mantenimiento y la evolución del sistema.

⚠️ El único costo es una **ligera penalización en la latencia**, ya que se introduce un paso adicional en la comunicación.

## ✅ Conclusión

Un **message broker** es un componente clave en sistemas asincrónicos modernos. Su uso permite:

* Desacoplar servicios.
* Escalar de forma eficiente.
* Mejorar la disponibilidad y tolerancia a fallos.
* Introducir nuevos servicios sin cambiar los existentes.

Es un bloque esencial para construir sistemas resilientes, mantenibles y preparados para la escala.

[Anterior](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/02_Load_Balancing_Solutions_%26_Cloud_Technologies.md)   [Siguiente](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/blob/main/04_Large_Scale_Systems_Architectural_Building_Blocks/04_Message_Brokers_Solutions_%26_Cloud_Technologies.md)

[Menú Principal](https://github.com/wilfredoha/Software_Architecture_and_Design_of_Modern_Large_Scale_Systems/tree/main)
