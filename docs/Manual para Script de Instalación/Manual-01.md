# Manual para Script de Instalación

## Docker | GitLab | Opción SSL | Opción SSH
*Facturador PRO4*

### Descripción

Hemos elaborado un script para uso en instancias Linux con Ubuntu 18 o superior. Este es un archivo que actualiza el sistema, instala las herramientas, sus dependencias y realiza todas las configuraciones previas, dejando el aplicativo listo para probar en menos de 20 minutos (siempre y cuando el dominio ya esté configurado hacia la instancia), su ejecución es muy sencilla.

### Requisitos previos

- Tener acceso a su servidor, VPS, máquina virtual o local vía SSH. En las instalaciones que realizamos para AWS o Google Cloud, hacemos entrega del usuario, la IP del servidor y la clave SSH que puede ser un archivo .ppk o .pem. Recuerde almacenarlas en su equipo local.
- Tener instalada una versión de SSH en su máquina para conectarse de manera remota. Puede utilizar Putty, FileZilla o una consola terminal. Para mayor información sobre el acceso SSH, visite los siguientes manuales:
  - [Guía para acceder con Putty (gestión de servidor)](enlace_a_la_guia_putty)
  - [Guía para acceder con WinSCP (gestión de archivos con aplicación de escritorio)](enlace_a_la_guia_winscp)
- Si es posible, configurar su dominio apuntando a su instancia para que al finalizar la instalación se encuentre disponible el aplicativo. Edite los registros A y CNAME, donde A debe contener su IP y CNAME el valor * (asterisco) para que se tomen los subdominios registrados por la herramienta.

### Precaución

En caso de contar con servicios instalados en su instancia como MySQL, Apache o Nginx, debe detenerlos, ya que estos ocupan los puertos que pasarán a usar el aplicativo con los contenedores de Docker.

![Docusaurus Logo](./img/Imagen01.png)
