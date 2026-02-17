# Especificación funcional: flujo de viaje compartido

## Objetivo
Definir el flujo mínimo para que una persona pueda solicitar y completar un viaje desde la app.

## Flujo principal
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

## Requisitos funcionales
- RF-01: El usuario puede fijar origen y destino mediante interacción en mapa.
- RF-02: El sistema ofrece al menos dos modalidades: inmediato y programado.
- RF-03: Cada opción de viaje incluye precio estimado, asientos y rating del conductor.
- RF-04: El usuario puede reservar un asiento disponible.
- RF-05: Tras reservar, se habilita vista de seguimiento en tiempo real.
- RF-06: El pago puede completarse desde la aplicación.
- RF-07: El usuario puede calificar al conductor/viaje al finalizar.

## Criterios de aceptación (MVP)
- CA-01: Si origen o destino faltan, no se habilita la consulta de opciones.
- CA-02: Si no hay asientos disponibles, la reserva no se permite y se informa al usuario.
- CA-03: El precio estimado se muestra antes de confirmar reserva.
- CA-04: La reserva confirmada muestra estado del viaje y ubicación actualizada.
- CA-05: La calificación solo se habilita cuando el viaje está completado.

## Próximos pasos técnicos sugeridos
- Definir modelo de datos: usuarios, conductores, viajes, reservas, pagos, calificaciones.
- Diseñar API base para búsqueda de rutas, reserva, tracking y cobro.
- Elegir proveedor de mapas y de pagos.
- Definir estrategia de actualización en tiempo real (websocket o polling).
