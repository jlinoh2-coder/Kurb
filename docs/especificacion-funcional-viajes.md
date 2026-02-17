# Especificación funcional: flujo de viaje compartido

## Objetivo
Definir el flujo mínimo para que una persona pueda solicitar y completar un viaje desde la app, y para que una persona conductora pueda publicar y gestionar viajes.

## 1. Flujo del pasajero
1. Seleccionar **origen** y **destino** en el mapa.
2. Ver opciones de viaje:
   - Viaje inmediato.
   - Viaje programado.
3. Para cada opción mostrar:
   - Precio estimado.
   - Asientos disponibles.
   - Calificación del conductor.
4. Permitir **reservar asiento**.
5. Mostrar **seguimiento en tiempo real** del viaje.
6. Permitir **pago en app**.
7. Al finalizar, permitir **calificar** la experiencia.

## 2. Flujo del conductor
1. Activar estado de disponibilidad:
   - **Modo conectado** para recibir/gestionar pasajeros.
   - **Modo desconectado** para no aparecer disponible.
2. Crear viaje con modalidad:
   - Viaje inmediato (tipo Uber).
   - Viaje programado (tipo BlaBlaCar).
3. Definir datos del viaje:
   - Ruta.
   - Precio por asiento.
   - Número de lugares.
4. Aceptar pasajeros para completar los asientos disponibles.
5. Iniciar navegación durante el viaje.
6. Ver ganancias asociadas a viajes completados.

## Requisitos funcionales
### Pasajero
- RF-PAS-01: El usuario puede fijar origen y destino mediante interacción en mapa.
- RF-PAS-02: El sistema ofrece al menos dos modalidades: inmediato y programado.
- RF-PAS-03: Cada opción de viaje incluye precio estimado, asientos y rating del conductor.
- RF-PAS-04: El usuario puede reservar un asiento disponible.
- RF-PAS-05: Tras reservar, se habilita vista de seguimiento en tiempo real.
- RF-PAS-06: El pago puede completarse desde la aplicación.
- RF-PAS-07: El usuario puede calificar al conductor/viaje al finalizar.

### Conductor
- RF-CON-01: El conductor puede alternar entre modo conectado y desconectado.
- RF-CON-02: El conductor puede crear viajes inmediatos o programados.
- RF-CON-03: El conductor define ruta, precio por asiento y número de lugares.
- RF-CON-04: El conductor puede aceptar o rechazar solicitudes de pasajeros.
- RF-CON-05: El conductor dispone de navegación para ejecutar la ruta activa.
- RF-CON-06: El conductor puede visualizar ganancias por viaje y acumuladas.

## Criterios de aceptación (MVP)
### Pasajero
- CA-PAS-01: Si origen o destino faltan, no se habilita la consulta de opciones.
- CA-PAS-02: Si no hay asientos disponibles, la reserva no se permite y se informa al usuario.
- CA-PAS-03: El precio estimado se muestra antes de confirmar reserva.
- CA-PAS-04: La reserva confirmada muestra estado del viaje y ubicación actualizada.
- CA-PAS-05: La calificación solo se habilita cuando el viaje está completado.

### Conductor
- CA-CON-01: En modo desconectado, el conductor no aparece en resultados de viajes inmediatos.
- CA-CON-02: Un viaje no puede publicarse si falta ruta, precio por asiento o número de lugares.
- CA-CON-03: No se pueden aceptar más pasajeros que los lugares definidos.
- CA-CON-04: La navegación solo se habilita para viajes en estado "en curso".
- CA-CON-05: Las ganancias se actualizan al marcar un viaje como completado y pagado.

## Próximos pasos técnicos sugeridos
- Definir modelo de datos: usuarios, conductores, viajes, reservas, pagos, calificaciones, estados de disponibilidad y liquidaciones.
- Diseñar API base para búsqueda de rutas, publicación de viajes, reserva, aceptación, tracking y cobro.
- Elegir proveedor de mapas y de pagos.
- Definir estrategia de actualización en tiempo real (websocket o polling).
- Definir reglas antifraude y políticas de cancelación para pasajero y conductor.
