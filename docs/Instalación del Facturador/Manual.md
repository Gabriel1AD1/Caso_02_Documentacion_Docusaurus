
# Instalación del Facturador con 
## Docker en Linux | SSL Externo

## FacturaloPeru 2020

### Pasos:

1. Ejecute el script de instalación, evitando instalar SSL. Se le consultará durante el proceso, y deberá ingresar "n".
   
2. Finalizada la instalación, diríjase a la ruta de instalación:

    ```bash
    cd /root/facturadorpro31/
    ```

3. Edite el archivo `.env` con el editor nano:

    ```bash
    nano .env
    ```

4. Dentro del editor, busque los siguientes parámetros y cámbielos:

   Antes:
   ```env
   APP_URL=http://${APP_URL_BASE}
   FORCE_HTTPS=false
   ```

   Después:
   ```env
   APP_URL=https://${APP_URL_BASE}
   FORCE_HTTPS=true
   ```

5. Una vez finalizado, guarde y salga del editor.

6. Ejecute los siguientes comandos para eliminar la caché de la aplicación:

    ```bash
    php artisan config:cache
    ```

7. Con esto, habrá completado la configuración del lado de la herramienta. En este momento, no podrá acceder a la herramienta hasta que tenga SSL configurado.

:::info Importante:

Recuerde habilitar el puerto 443 para tener acceso a la herramienta.


Este formato facilita la lectura y comprensión de los pasos para la instalación del Facturador con Docker en Linux y SSL externo
:::