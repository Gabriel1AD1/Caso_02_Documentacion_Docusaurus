---
sidebar_position: 4
---
# Recomendaciones

Después de instalar el facturador, se sugiere realizar algunas configuraciones adicionales en el archivo `.env` para adaptar el sistema a sus necesidades:

- **Dirección de envío de correos:** Modificar la dirección de envío de correos utilizada por el facturador para enviar archivos PDF, XML y CDR a los clientes.

- **Configuraciones de plantillas PDF:** Ajustar algunas configuraciones de las plantillas de los archivos PDF según las preferencias o requisitos específicos.

Recuerde seguir estos pasos adicionales:

1. **Configuración del archivo .env:**
   - Edite el archivo `.env` con las configuraciones deseadas.

2. **Actualizar configuración en el contenedor FPM1:**
   - Después de editar el archivo `.env`, es necesario ejecutar el siguiente comando dentro del contenedor FPM1 para refrescar la configuración:
     ```bash
     php artisan config:cache
     ```
   - Esto asegura que los cambios en la configuración se apliquen correctamente.

3. **Permisos de la ruta de ejecución del script:**
   - La ruta donde ejecutó el script será donde se clone el repositorio. Asegúrese de que los usuarios del servidor tengan los permisos adecuados en esa ruta.
   - Esto es crucial si planea acceder desde FTP o SCP.

Estas recomendaciones garantizan una configuración óptima y funcionalidad del facturador después de la instalación inicial.
