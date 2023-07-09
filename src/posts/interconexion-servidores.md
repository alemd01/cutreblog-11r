---
layout: post
title: "Interconexión de Servidores de Bases de datos"
excerpt: En este articulo, veremos como compilar un kernel linux a medida.
date: 2022-11-16
tags:
  - GBD
draft: true
---
# Interconexión de Servidores de Bases de Datos.

## 1. Realizar un enlace entre dos servidores de bases de datos ORACLE, explicando la configuración necesaria en ambos extremos y demostrando su funcionamiento.

En el escenario, tenemos 2 servidores Oracle, uno creado en mi propio sistema debian y otro en una máquina virtual debian. Ambos se conectan a través de una red virtual. Lo primero que haremos, es crear un usuario en cada servidor con los privilegios suficientes para poder realizar la interconexión.

El usuario del servidor 1:

![BD-P2.2.png](/img/BD-P2.2.png)

El usuario del servidor 2:

![BD-P2.1.png](/img/BD-P2.1.png)

He añadido como ejemplo el esquema SCOTT para poder visualizar algunas tablas. Vamos a configurar el archivo `tnsntames.ora`:

```bash
sudo nano /opt/oracle/product/19c/dbhome_1/network/admin/tnsnames.ora
```

```bash
RCLCDB =
  (DESCRIPTION =
    (ADDRESS = (PROTOCOL = TCP)(HOST = 192.168.122.97)(PORT = 1521))
    (CONNECT_DATA =
      (SERVER = DEDICATED)
      (SERVICE_NAME = ORCLCDB)
    )
  )
```

---

## **Documento realizado por:**

 ✒️ **Alejandro Montes Delgado** - *2º ASIR*
