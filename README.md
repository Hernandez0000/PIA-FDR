# PIA-FDR

## Table of Contents
1. [Informacion General](#general-info)
2. [Protocolo utilizados](#Protocolos)
3. [Configuración Básica](#Conf-Basica)
4. [Configuración Servidores](#Conf-Servers)
5. [Seguridad](#Seguridad)

<a name="general-info"></a>
## -Informacion General

La propuesta que se tiene para nuestra red empresarial es 
la de conectar 5 sucursales aledañas de Call Center a una 
sucursal de administración con la finalidad de compartir 
información para el crecimiento de la empresa 
garantizando una comunicación fluida entre las 
sucursales.

Planteles: 
 Oficina Central: ubicada en Monterrey 
 Sucursales ubicadas en:\
  • San Nicolas\
  • San Pedro\
  • Guadalupe\
  • Topo Chico\
  • Garza Sada\
Dentro de las sucursales habrá cuatro departamentos y contaran con la siguiente
distribución de host activos:\
  •Recursos Humanos y Administración (5 hosts)\
  •Finanzas y Contabilidad (25 hosts disponibles)\
  •Atención al Cliente (50 hosts disponibles)\
  •Ventas (125 hosts disponibles)\
Además de que en cada una de las sucursales se aplicaran direcciones de IP públicas 
en los enlaces y direcciones de IP privadas para conectar las sucursales.\

<a name="Protocolos"></a>
## -Protocolos utilizados

  • SSH\
  • DHCP\
  • Enrutamiento estatico\

<a name="Conf-Basica"></a>
## -Configuración Básica

Consideramos diferentes factores como la cantidad de 
agentes que trabajarían en la organización, la cantidad de dispositivos finales requeridos, 
así como la escalabilidad en un 25%. Luego de considerar estas variables, se 
seleccionaron los servidores, router, switches y dispositivos finales adecuados para la 
organización.\

A continuación, procedimos a configurar cada uno de estos dispositivos. Configuramos 
las direcciones IP, (direcciones IP privadas dentro de las redes locales de la organización 
y direcciones públicas para las redes que su objetivo es comunicar sucursales) 
establecimos la red de datos para que los dispositivos pudieran comunicarse entre sí y 
conectamos los dispositivos a través de cables.\

Los dispositivos intermediarios cuentas con la configuración más comunes como el 
nombre de dispositivo, un banner para dar mensajes a los administradores que se 
encargan de darle configuración y mantenimiento a estos dispositivos, contraseñas que 
se basan en los criterios para una contraseña segura (aunque para este proyecto se 
utiliza una contraseña insegura), además de cifrarlas.\

Cada una de nuestros departamento cuentan con Subneteo VLSM para poder dividir 
nuestras redes en subredes para así asignarlas en cuatro diferentes departamentos que 
pueda satisfacer las necesidades que se nos pide (cada departamento requiere 100, 40, 
20 y 4 hosts activos, además de tomar en cuenta la escalabilidad al 20%). 
Además de utilizar algunos protocolos como el SSH, DHCP.\

<a name="Conf-Servers"></a>
## -Configuración de Servidores

Los servidores fueron configurados para asignar de forma dinámica las direcciones IP a 
los dispositivos finales en los departamentos que requieran de una gran cantidad de 
hosts, (también considerando la escalabilidad) para que, de esta forma el 
direccionamiento sea lo más eficiente y rápido posible utilizando el protocolo DHCP.\

<a name="Seguridad"></a>
## -Seguridad
Para la seguridad de nuestra topología de red se implementaron ciertas configuraciones 
en los dispositivos intermediarios, así como, algunos protocolos que darán mas 
seguridad a nuestra red que se mostrarán a continuación:\

Protocolos SSH: Es un protocolo de administración remota que le permite a los usuarios controlar y 
modificar sus servidores remotos a través de Internet a través de un mecanismo de 
autenticación. 
Proporciona un mecanismo para autenticar un usuario remoto, transferir entradas desde 
el cliente al host y retransmitir la salida de vuelta al cliente.\

Contraseñas seguras: En cada uno de los dispositivos intermediarios implementados en nuestra topología se 
asignarán las contraseñas tomando como base los criterios de una contraseña segura, 
las cuales son:\
✓ Tener como mínimo 8 caracteres.\
✓ No usar como contraseñas palabras que puede ser encontradas en el diccionario, 
alguna fecha o dato personal fácil de obtener o deducir.\
✓ Utilizar símbolos y otros caracteres especiales en combinación con letras y 
números.\
✓ En caso de cambio de contraseña, no utilizar una que ya haya sido utilizada con 
anterioridad.\

Otras Configuraciones: 
• Tener un numero límite de intentos para poder evitar que alguien intente entrar 
por medio de fuerza bruta (límite de 4 intentos).\
• Tener un límite de inactividad cuando se está administrando algún dispositivo 
intermediario.\
• Tener un tiempo límite cuando se está iniciando sesión (tiempo límite de 120 
segundos).\
• Únicamente el método de transporte para la comunicación entre dispositivos para 
poder administrarlos es por SSH.\
