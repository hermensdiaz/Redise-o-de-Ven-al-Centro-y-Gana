# Requisitos funcionales

Cada requisito cuenta con un ID estructurado por módulos para facilitar su trazabilidad en Issues, commits y pruebas.


### Pantalla de Inicio 

* **RF-001**: El sistema permite al concursante visualizar la información general de la campaña, el botón y un indicador visual que guie al usuario al botón de comienzo, para comenzar su registro de participación. 

* **RF-002**: El sistema permite redirigir al concursante a la lista de sucursales participantes en la campaña (páginas externas al sistema). 

* **RF-003**: El sistema permite redirigir al concursante a las bases oficiales para participar. 

### Registro de participación 

* **RF-004**: El sistema permite ingresar el número telefónico para verificar si el concursante ya está registrado. Si lo está, se le dirige al registro de datos, si no lo está se le muestra una ventana emergente atractiva visualmente que le indique que se registra por primera vez.  

* **RF-005**: El sistema permite capturar los datos personales del concursante (nombre, apellidos, teléfono, correo electrónico y domicilio) y aceptar el aviso de privacidad para continuar, solo se presenta a concursantes nuevos. Se le muestra un ejemplo establecido de cómo debe ingresarse el dato en cuestión 

* **RF-006**: El sistema permite seleccionar la sucursal donde se realizó la compra, ingresar el monto (mínimo $200) y adjuntar la foto del ticket. Al completarlo correctamente se avanza a la trivia.  

* **RF-007**: El concursante responde 3 preguntas de opción múltiple seleccionadas aleatoriamente. Debe contestarlas todas correctamente para validar su participación. 

### Resultados de la Trivia 

* **RF-008**: El sistema permite informa al concursante que contestó correctamente, que su participación fue registrada y que finalizó con la dinámica. El sistema envía automáticamente un mensaje con el folio de participación vía mensaje SMS.  

* **RF-009**: El sistema permite informa al concursante que su respuesta fue incorrecta y que su participación no fue registrada, indicando que puede volver a participar con el mismo número telefónico y que finalizó con la dinámica. 