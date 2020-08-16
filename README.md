Descripción del playbook (talleragosto2020)
===========================================

Con este playbook y sus roles logramos instalar de cero o actualizar apache en distribuciones basadas en RedHat y Debian. 
A continuación se detallan las configuraciones del playbook:

- Instalación apache con proxy reverso y loadbalancer.
- Instalación de modulos necesarios para apache.
- Configuración de virtualhost.
- Reinicio de servicio web en cada cambio.
- Se deja el servicio web en estado iniciado.
- Configuracion acceso firewall a los puertos HTTP y HTTPS.
- Este playbook se encuentra en el siguiente repositorio de GitHub: https://github.com/rcbarreto/talleragosto2020.git

Requerimientos
--------------

Se debe configurar un usuario con privilegios de sudo llamado Ansible.
Se debe configurar en el/los firewall acceso SSH al usuario Ansible.
Se debe configurar al menos un servidor en una de las distribuciones implementadas.
Se debe configurar archivo inventario_equipos con los hosts deseados. 
Es deseable copiar la key de el servidor que oficia de bastion a los demas host para la ejecución del playbook.

Role Variables
--------------
nombre_cluster: 
nodoP: 
nodoS: 
port1: 
port2: 
red_autorizada: 

Example Playbook
----------------

Se detalla un ejemplo de variables y host utilizados en este playbook para ser modifcadas a necesidad del profesional que tome como referencia este playbook.

-Configuración inventario_equipos
---------------------------------

[RedHat]
ansible.lab.ort ansible_host=192.168.1.33
[Debian]
loadbalancer.lab.ort ansible_host=192.168.1.32


-Variables para virtualhost:
----------------------------
nombre_cluster: balanceo
nodoP: nodo1.lab.ort
nodoS: nodo2.lab.ort
port1: 80
port2: 80
red_autorizada: 192.168.1.0/24

License
-------

BSD

Información de los autores
--------------------------
Ma Eugenia Gardela
Jose Pinto
Rodrigo Barreto


