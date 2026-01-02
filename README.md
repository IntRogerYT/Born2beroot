*Este proyecto ha sido creado como parte del currículo de 42 por <rcamps-v>[rcamps-v]().*
# Born2beroot
## Descripción del proyecto
Este proyecto se basa en crear y configurar un sistema operativo (SO), en mi caso un Sistema Debian Linux. En este caso uso una maquina virtual de virtualbox para dicho proyecto.
En este proyecto se aprende...
- Como crear y configurar una màquina virtual con Virtualbox
- Como instalar y configurar un sisteam operativo con sus respectivas particiones, con su usuario root, etc.
- Como instalar i configurar sudo (permisos del sistema)
- Como instalar i configurar SSH (Acceso remoto)
- Como instalar i configurar UFW (Firewall)
- Como crear un script Bash y configurar Crontab (Automatizacion)

Como he dicho anteriormente, he elegido Debian como Sistema Operativo a usar. La razon por la que he elegido Debian es que es mas intuitivo y va dirigido mas para particulares, como yo.
###Debian vs Rocky Linux
####Ventajas de Debian:

Extremadamente estable gracias a pruebas rigurosas en su rama "Stable".
Repositorio enorme con miles de paquetes, ideal para desktops, desarrollo y usos generales.
Gran comunidad y soporte largo en versiones LTS.
Fuerte enfoque en seguridad con actualizaciones oportunas.
Muy versátil, funciona bien en hardware antiguo y soporta arquitecturas como 32-bit.

####Desventajas de Debian:

En la rama Stable, los paquetes suelen ser más antiguos, lo que puede significar falta de características nuevas.
Menos soporte comercial directo comparado con distribuciones enterprise.
No ofrece compatibilidad exacta "bug-for-bug" con RHEL, lo que complica migraciones desde entornos Red Hat.

####Ventajas de Rocky Linux:

Compatibilidad bug-for-bug con RHEL, perfecta para entornos enterprise y migraciones desde CentOS.
Ciclo de vida largo (10 años) con soporte gratuito estilo enterprise.
Integración profunda con herramientas como SELinux, más robustas por defecto.
Optimizado para servidores y workloads de producción.

####Desventajas de Rocky Linux:

Menos paquetes disponibles; está más enfocado en enterprise que en desktop o multimedia.
Actualizaciones pueden llegar con algo de retraso respecto a RHEL.
Documentación menos extensa para usuarios principiantes o usos no enterprise.
Menos versátil para desktops o hardware muy antiguo.

###AppArmor vs SELinux
####Ventajas de AppArmor:

Mucho más fácil de aprender y configurar (se basa en rutas de archivos simples).
Curva de aprendizaje corta y perfiles preconfigurados en distribuciones como Ubuntu o SUSE.
Menor sobrecarga de rendimiento.
Ideal para confinamiento rápido de aplicaciones en entornos simples.

####Desventajas de AppArmor:

Menos granular que SELinux; no soporta características avanzadas como MLS/MCS.
No tan potente para separación estricta en entornos de alta seguridad o con containers complejos.

####Ventajas de SELinux:

Control de acceso extremadamente granular (MAC completo, con soporte para RBAC, Type Enforcement, MLS/MCS).
Más seguro en entornos de alta compliance (gubernamental, enterprise estricta).
Políticas preconfiguradas robustas en distribuciones como RHEL/Rocky/Fedora.
Mejor para protección en profundidad.

####Desventajas de SELinux:

Muy complejo de configurar y depurar; curva de aprendizaje alta.
Políticas mal configuradas pueden causar muchos problemas (muchos usuarios lo desactivan).
Mayor sobrecarga en algunos escenarios.
Problemas ocasionales al mover archivos (se basa en etiquetas de inodos).

###UFW vs firewalld
####Ventajas de UFW:

Sintaxis extremadamente simple e intuitiva, perfecta para principiantes.
Reglas fáciles de revisar y gestionar.
Frontend ligero para iptables/nftables con funciones básicas como rate-limiting.
Ideal para servidores simples o desktops.

####Desventajas de UFW:

Menos características avanzadas (no tiene zonas nativas).
Peor integración con containers modernos (Docker/Podman puede ignorarlo fácilmente).
No maneja bien escenarios con múltiples redes o cambios dinámicos.

####Ventajas de firewalld:

Soporte para zonas (reglas diferentes según interfaz/red), ideal para laptops o servidores con redes variables.
Cambios dinámicos sin reiniciar el servicio.
Excelente integración con Podman/Docker y systemd.
Herramientas GUI disponibles y fácil reversión de cambios.

####Desventajas de firewalld:

Interfaz de línea de comandos más verbosa y compleja.
Puede ser excesivo para configuraciones muy básicas.
A veces abre puertos automáticamente al interactuar con containers, lo que puede sorprender.

###VirtualBox vs UTM
####Ventajas de VirtualBox:

Multiplataforma (funciona en Windows, Linux y macOS).
Muchas características avanzadas: snapshots, carpetas compartidas, modo seamless, aceleración 3D/GPU, soporte USB completo.
Amplio soporte para diferentes sistemas operativos invitados.
Bueno en Macs Intel y entornos donde necesitas funcionalidades complejas.

####Desventajas de VirtualBox:

Rendimiento pobre en Macs con Apple Silicon (M1/M2/M3+), ya que depende de emulación.
Mayor consumo de recursos en general.
Configuración de algunas funciones (como USB) puede ser complicada.

####Ventajas de UTM:

Optimizado específicamente para macOS, especialmente en Apple Silicon (usa el hypervisor nativo de Apple).
Muy ligero y rápido en Macs modernos M-series.
Interfaz simple y configuración fácil.
Completamente gratuito y open-source sin restricciones.

####Desventajas de UTM:

Solo disponible para macOS (no multiplataforma).
Menos características avanzadas: sin aceleración gráfica 3D completa en Windows, snapshots más limitados.
No ideal para workloads gráficos intensos o gaming en VMs.
Rendimiento inferior en Macs Intel antiguos.
## Instrucciones
En este proyecto se trabaja con una maquina virtual, para crear-la hay que comprovar los requisitos minimos para el Sistema Operativo que se quiere emplear. Por ejemplo, buscando por internet, descubri que los requisitos minimos de Debian sin entorno grafico son:
- Procesador: 1 GHz.
- RAM: 512MB - 1GB.
- Disco Duro: 4GB - 10GB.
Esto hay que tener-lo en cuenta a la hora de configurar la maquina virtual.
## Recursos
- [Virtualbox](https://www.virtualbox.org/)(Pagina oficial).
