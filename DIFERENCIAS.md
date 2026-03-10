# Diferencias entre HSRP y VRRP

## Introducción
HSRP y VRRP son protocolos de redundancia de gateway utilizados en redes para garantizar la disponibilidad del gateway predeterminado. Permiten que varios routers trabajen juntos para proporcionar una dirección IP virtual que actúa como puerta de enlace para los dispositivos de la red.

Si el router principal falla, otro router toma su lugar automáticamente, evitando interrupciones en la conectividad.

---

# HSRP vs VRRP

| Característica | HSRP | VRRP |
|---|---|---|
| Nombre completo | Hot Standby Router Protocol | Virtual Router Redundancy Protocol |
| Desarrollador | Cisco | Estándar abierto |
| Estándar | Propietario | Estándar IEEE |
| Compatibilidad | Solo dispositivos Cisco | Multivendor |
| Router activo | Active / Standby | Master / Backup |
| Dirección virtual | Sí | Sí |
| Protocolo | Propietario de Cisco | Basado en estándares |
| Puerto | UDP 1985 | IP protocolo 112 |
| Balanceo de carga | Limitado | Puede implementarse más fácilmente |
| Interoperabilidad | Solo Cisco | Compatible con múltiples fabricantes |

---

# Funcionamiento de HSRP

En HSRP existen dos routers principales:

- **Active Router:** Maneja todo el tráfico.
- **Standby Router:** Espera en caso de falla.

Si el router activo deja de responder, el router en espera toma el control automáticamente.

### Ejemplo

Router 1  
IP: 192.168.1.2  

Router 2  
IP: 192.168.1.3  

IP virtual (Gateway):  
192.168.1.1

Los dispositivos de la red usan **192.168.1.1** como gateway.

---

# Funcionamiento de VRRP

VRRP funciona de manera similar, pero con diferentes nombres de roles:

- **Master Router:** Router principal.
- **Backup Router:** Router de respaldo.

Los routers comparten una **dirección IP virtual** que es utilizada por los dispositivos como puerta de enlace.

Si el **Master** falla, un **Backup** toma el control automáticamente.

---

# Ventajas de HSRP

- Fácil configuración en equipos Cisco
- Muy estable en redes Cisco
- Amplio soporte en equipos Cisco

---

# Ventajas de VRRP

- Estándar abierto
- Compatible con múltiples fabricantes
- Mayor interoperabilidad
- Puede usarse en redes mixtas

---
# TOPOLOGIAS

<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/75db52d8-8d58-4c23-ae48-1759bf58be12" />

---

# Conclusión

HSRP y VRRP cumplen el mismo objetivo: proporcionar redundancia en el gateway de una red.  
La principal diferencia es que **HSRP es propietario de Cisco**, mientras que **VRRP es un estándar abierto** compatible con diferentes fabricantes.

Por esta razón, VRRP suele utilizarse en redes con equipos de diferentes marcas, mientras que HSRP se utiliza principalmente en infraestructuras basadas en Cisco.

---

# Referencias

- Cisco Networking Academy
- RFC 5798 - Virtual Router Redundancy Protocol
