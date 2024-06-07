# Spoofing_AuthorityM3Xa

![Descripción de la imagen](https://github.com/Valentespiegel/Spoofing_AuthorityM3Xa/blob/master/Evidencia/1.png?raw=true)

---

### Metodología

<font color="red">Este texto estará en rojo</font>


Este ataque involucra la creación de un punto de acceso inalámbrico falso que imita a una red legítima (Evil Twin), junto con la implementación de un portal cautivo abusivo que engaña a los usuarios haciéndoles creer una cosa:

> La empresa responsable de su servicio de internet está pasando por una eventualidad técnica en su zona geográfica., Así como no dar lugar a dudas de que ya se está en contacto con la autoridad responsable, dándoles la oportunidad de resolver la interrupción de su servicio de internet solo proporcionando su contraseña, con la excusa de que solo así se podrá autorizar el cambio de conexión al clúster más cercano geográficamente y poder resolver el evento.
  
Simultáneamente, se ejecuta un Deauth aireplay attack con el objetivo de:

> Dar veracidad haciendo real este evento técnico, interrumpiendo el servicio de internet a los dispositivos conectados a la red legítima y obtener un WPS handshake.

La comparación del WPS Handshake se encarga de:

> Confirmar si la contraseña ingresada por la víctima es correcta mediante la comparación con el handshake ya obtenido anteriormente.

El ataque de desautenticación continúa interrumpiendo la conectividad de los dispositivos a la red legítima de manera indefinida hasta proporcionar las credenciales correctas. El conocimiento de la ubicación geográfica puede ayudar a la credibilidad del phishing.

---

### Puntos a considerar
Se utilizará la herramienta automatizada de v1s1t0r1sh3r3 llamada [airgeddon](https://github.com/v1s1t0r1sh3r3/airgeddon) en su versión de desarrollador para que nos permita trabajar con redes de 5GHz, junto con los [plugins](https://github.com/KeyofBlueS/airgeddon-plugins) de KeyofBlueS que se alojarán dentro del proyecto en el directorio **/airgeddon/plugins/**. Asi como los portales cautivos de este proyecto en el directorio **/airgeddon/plugins/Custom_portals**

 Debido a la sofisticación del ataque es necesario tener en cuenta que se necesitan dos tarjetas de red para llevar a cabo este ataque, con algunas de las siguientes especificaciones:

> Una o ambas tarjetas de red deben tener acceso a modo maestro para poder levantar el AP y que la tarjeta lo permita. Comúnmente, si una tarjeta soporta modo maestro, se espera que también pueda acceder al modo monitor.
> La segunda tarjeta de red no necesariamente tendrá que soportar el modo maestro, pero sí el modo monitor.

Si hablamos de chipsets en tarjetas de red, podemos hablar de cuál es el tipo de tarjeta que necesitamos. En esta ocasión estamos usando el chip **Mediatek MT7612u**, el cual soporta el modo maestro y monitor, al igual que una **Atheros AR9271**, el cual soporta solo el modo monitor.

![Descripción de la imagen](https://github.com/Valentespiegel/Spoofing_AuthorityM3Xa/blob/master/Evidencia/2.png?raw=true)

---

#### **Instrucciones**

1. Ejecute como usuario **sudo** la aplicación **airgeddon**.
2. Establezca el chip **Mediatek MT7612U** en estado **monitor**.
3. Muestre el **Evil Twin attacks menú**.
4. Seleccione el ataque **Evil Twin AP attack with captive portal (monitor mode needed)**.
5. Escanee el entorno para establecer nuestro objetivo.
6. Active el **"DoS Pursuit Mode"** estableciendo el chip **Atheros AR9271** para esta tarea en modo monitor.
7. Durante el ataque, es necesario el **Spoof MAC**.
8. El intervalo de captura del **handshake** será de 20 segundos.
9. Elija una de las 3 **interfaces de autoridad**.
10. Acepte la captura de caracteres especiales, así como el idioma en el que se desplegará el sitio falso.
11. A continuación, se desplegarán 6 consolas en la pantalla. La que nos interesa se encuentra situada en la esquina superior izquierda, donde se indican **Víctimas ya en el portal cautivo**, **Intentos de contraseña** y **Ruta de las credenciales obtenidas en caso de tener éxito**.

![Descripción de la imagen](https://github.com/Valentespiegel/Spoofing_AuthorityM3Xa/blob/master/Evidencia/3.png?raw=true)

---

### Ética

> Mi intención al publicar esta información es únicamente para concienciar y educar. Jamás deberá ser replicada sin los permisos correspondientes. Me deslindo de cualquier responsabilidad por el uso malintencionado de esta información.
