---
title: Trabajo con cadenas en consultas de Azure Log Analytics | Microsoft Docs
description: En este artículo se proporciona un tutorial de uso del portal de Analytics para escribir consultas en Log Analytics.
services: log-analytics
documentationcenter: ''
author: bwren
manager: carmonm
editor: ''
ms.assetid: ''
ms.service: log-analytics
ms.workload: na
ms.tgt_pltfrm: na
ms.topic: conceptual
ms.date: 08/16/2018
ms.author: bwren
ms.openlocfilehash: 24f22d659ccfb6923ad2a038e12454716b2c5445
ms.sourcegitcommit: c61777f4aa47b91fb4df0c07614fdcf8ab6dcf32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2019
ms.locfileid: "54263890"
---
# <a name="working-with-json-and-data-structures-in-log-analytics-queries"></a>Trabajo con JSON y estructuras de datos en consultas de Log Analytics

> [!NOTE]
> Debe completar la [Introducción al portal de Analytics](get-started-portal.md) y la [Introducción a las consultas en Log Analytics](get-started-queries.md) antes de completar esta lección.

[!INCLUDE [log-analytics-demo-environment](../../../includes/log-analytics-demo-environment.md)]

Los objetos anidados son objetos que contienen otros objetos en una matriz o un mapa de pares clave-valor. Estos objetos se representan como cadenas JSON. En este artículo se describe cómo se usa JSON para recuperar datos y analizar objetos anidados.

## <a name="working-with-json-strings"></a>Trabajo con cadenas JSON
Use `extractjson` para acceder a un elemento JSON específico en una ruta de acceso conocida. Esta función requiere una expresión de ruta de acceso que use las siguientes convenciones.

- _$_ para hacer referencia a la carpeta raíz
- Use la notación de corchetes o puntos para hacer referencia a los índices y elementos, tal como se muestra en los ejemplos siguientes.


Use corchetes para los índices y puntos para separar los elementos:

```Kusto
let hosts_report='{"hosts": [{"location":"North_DC", "status":"running", "rate":5},{"location":"South_DC", "status":"stopped", "rate":3}]}';
print hosts_report
| extend status = extractjson("$.hosts[0].status", hosts_report)
```

Este es el mismo resultado usando solo la notación de corchetes:

```Kusto
let hosts_report='{"hosts": [{"location":"North_DC", "status":"running", "rate":5},{"location":"South_DC", "status":"stopped", "rate":3}]}';
print hosts_report 
| extend status = extractjson("$['hosts'][0]['status']", hosts_report)
```

Si hay solo un elemento, puede usar únicamente la notación de puntos:

```Kusto
let hosts_report='{"location":"North_DC", "status":"running", "rate":5}';
print hosts_report 
| extend status = hosts_report.status
```


## <a name="working-with-objects"></a>Trabajo con objetos

### <a name="parsejson"></a>parsejson
Para acceder a varios elementos en la estructura JSON, es más fácil acceder como un objeto dinámico. Use `parsejson` para convertir los datos de texto en un objeto dinámico. Después de la conversión en un tipo dinámico, se pueden usar funciones adicionales para analizar los datos.

```Kusto
let hosts_object = parsejson('{"hosts": [{"location":"North_DC", "status":"running", "rate":5},{"location":"South_DC", "status":"stopped", "rate":3}]}');
print hosts_object 
| extend status0=hosts_object.hosts[0].status, rate1=hosts_object.hosts[1].rate
```



### <a name="arraylength"></a>arraylength
Use `arraylength` para contar el número de elementos en una matriz:

```Kusto
let hosts_object = parsejson('{"hosts": [{"location":"North_DC", "status":"running", "rate":5},{"location":"South_DC", "status":"stopped", "rate":3}]}');
print hosts_object 
| extend hosts_num=arraylength(hosts_object.hosts)
```

### <a name="mvexpand"></a>mvexpand
Use `mvexpand` para dividir las propiedades de un objeto en filas independientes.

```Kusto
let hosts_object = parsejson('{"hosts": [{"location":"North_DC", "status":"running", "rate":5},{"location":"South_DC", "status":"stopped", "rate":3}]}');
print hosts_object 
| mvexpand hosts_object.hosts[0]
```

![mvexpand](media/json-data-structures/mvexpand.png)

### <a name="buildschema"></a>buildschema
Use `buildschema` para obtener el esquema que admite todos los valores de un objeto:

```Kusto
let hosts_object = parsejson('{"hosts": [{"location":"North_DC", "status":"running", "rate":5},{"location":"South_DC", "status":"stopped", "rate":3}]}');
print hosts_object 
| summarize buildschema(hosts_object)
```

El resultado es un esquema en formato JSON:
```json
{
    "hosts":
    {
        "indexer":
        {
            "location": "string",
            "rate": "int",
            "status": "string"
        }
    }
}
```
Esta salida describe los nombres de los campos del objeto y sus tipos de datos coincidentes. 

Los objetos anidados pueden tener esquemas diferentes, como en el ejemplo siguiente:

```Kusto
let hosts_object = parsejson('{"hosts": [{"location":"North_DC", "status":"running", "rate":5},{"status":"stopped", "rate":"3", "range":100}]}');
print hosts_object 
| summarize buildschema(hosts_object)
```


![Compilación de esquema](media/json-data-structures/buildschema.png)

## <a name="next-steps"></a>Pasos siguientes
Vea otras lecciones para usar el lenguaje de consulta de Log Analytics:

- [Operaciones de cadena](string-operations.md)
- [Operaciones de fecha y hora](datetime-operations.md)
- [Funciones de agregación](aggregations.md)
- [Agregaciones avanzadas](advanced-aggregations.md)
- [Escritura de consultas avanzadas](advanced-query-writing.md)
- [Combinaciones](joins.md)
- [Gráficos](charts.md)