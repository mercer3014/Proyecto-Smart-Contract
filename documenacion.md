Contrato Subasta
Variables de Estado
owner: Dirección del propietario del contrato.

mejorOferente: Dirección del oferente con la mejor oferta actual.

mejorOferta: Monto de la mejor oferta actual.

inicio: Timestamp de inicio de la subasta.

duracion: Duración inicial de la subasta en segundos.

finalizada: Booleano que indica si la subasta ha finalizado.

comision: Porcentaje de comisión que el owner recibe de la mejor oferta.

ExtencionMinutos: Minutos de extensión de la subasta si se realizan ofertas cerca del final.

Estructuras y Arrays
Oferta: Estructura que almacena la dirección del oferente y el monto de la oferta.

ofertasTotales: Array de todas las ofertas realizadas durante la subasta.

historialOfertas: Mapeo que relaciona direcciones de oferentes con arrays de montos de sus ofertas históricas.

depositos: Mapeo que guarda los depósitos totales realizados por cada dirección.

Eventos
NuevaOferta: Emitido cuando se realiza una nueva oferta. Registra la dirección del oferente y el monto de la oferta.

SubastaFinalizada: Emitido cuando la subasta finaliza. Registra la dirección del ganador y el monto de la mejor oferta.

ReembolsoParcial: Emitido cuando se realiza un reembolso parcial a un oferente. Registra la dirección del oferente y el monto reembolsado.

FondosRetirados: Emitido cuando se retiran fondos de la subasta. Registra la dirección a la que se transfieren los fondos y el monto transferido.

Modificadores
subastaActiva: Requiere que la subasta esté activa y que no haya finalizado ni haya expirado el tiempo.

soloOwner: Requiere que el llamador sea el propietario del contrato.

Funciones
constructor(): Inicializa el contrato estableciendo al creador como propietario y registrando el tiempo de inicio.

ofertar(): Permite realizar una oferta durante la subasta activa, validando el monto mínimo requerido y extendiendo el tiempo si es necesario.

verOfertas(): Devuelve un array con todas las ofertas realizadas durante la subasta.

verHistorialDe(address usuario): Devuelve un array con los montos de las ofertas históricas realizadas por un usuario específico.

reembolsoParcial(): Permite a un oferente retirar parcialmente sus fondos si tiene múltiples ofertas.

finalizar(): Finaliza la subasta, transfiriendo la comisión al propietario y el monto restante al ganador.

retirar(): Permite a los oferentes retirar sus fondos después de que la subasta haya finalizado, excepto al ganador.

retirarFondos(): Permite al propietario retirar los fondos restantes del contrato una vez finalizada la subasta.

tiempoRestante(): Devuelve el tiempo restante en segundos hasta el final de la subasta.

verBalance(): Consulta el saldo actual del contrato en ETH.

https://sepolia.etherscan.io/address/0x32F06F8C1A2d792d3BF2569D62dd5AF8573597f9
