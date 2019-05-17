# DemoMagentoModule
Creado por: Yoelvys.
Ejemplo de creacion de un Modulo en Magento 2

Pasos para la habilitacion del modulo:
0.- Crear la carpeta code en magento/app/code
1.- Copiar la carpeta Demo al directorio magento/app/code
2.- Ejecutamos el comando bin/magento module:status para verificar que el modulo este disponible para si habilitacion, debe salir que el modulo Demo_Blog esta deshabilitado
3.- Procedemos a habilitar el modulo bin/magento module:enable Demo_Blog
4.- Luego ejecutamos el comando bin/magento setup:upgrade para ejecutar la creacion de la tabla Demo_blog_post e insertar datos en ella, esto se hace a traves de los ficheros magento/app/code/Demo/Blog/Setup/InstallSchema.php y magento/app/code/Demo/Blog/Setup/UpgradeData.php
5.- Finalmente ejecutamos bin/magento setup:di:compile

Con estos pasos queda habilitado el modulo, en el fichero magento/app/code/Demo/Blog/etc/module.xml con el parametro setup_version podemos versionar la actualizacion de los datos del modulo esto se verifica en el fichero magento/app/code/Demo/Blog/Setup/UpgradeData.php
6.- Acceder a tu http://ip:port/blog    //Se debe mostrar en el body de la pagina el texto siguiente: Demo Posts
Otras notas:
si quieres que aparezca informacion, cambia la version en el fichero module.xml y en UpgradeData.php y vuelves a ejecutar setup:upgrade y setup:di:compile
