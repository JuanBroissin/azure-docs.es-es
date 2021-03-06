---
title: Planeamiento de la capacidad de los roles de servidor de Azure App Service en Azure Stack | Microsoft Docs
description: Planeamiento de la capacidad de los roles de servidor de Azure App Service en Azure Stack
services: azure-stack
documentationcenter: ''
author: sethmanheim
manager: femila
editor: ''
ms.assetid: ''
ms.service: azure-stack
ms.workload: app-service
ms.tgt_pltfrm: na
ms.devlang: na
ms.topic: article
ms.date: 10/15/2018
ms.author: sethm
ms.reviewer: anwestg
ms.lastreviewed: 10/15/2018
ms.openlocfilehash: 03d29b7f072aaab09b0677031ee34bd61d876ce6
ms.sourcegitcommit: 898b2936e3d6d3a8366cfcccc0fccfdb0fc781b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55242848"
---
# <a name="capacity-planning-for-azure-app-service-server-roles-in-azure-stack"></a>Planeamiento de la capacidad de los roles de servidor de Azure App Service en Azure Stack

*Se aplica a: Sistemas integrados de Azure Stack y Kit de desarrollo de Azure Stack*

Para configurar una implementación lista para producción de Azure App Service en Azure Stack, debe planear la capacidad que espera que el sistema admita.  

En este artículo se ofrece una guía del número mínimo de instancias de proceso y SKU de proceso que debe usar para una implementación de producción.

Puede planear la estrategia de capacidad de App Service mediante estas instrucciones.

| Rol de servidor de App Service | Número mínimo recomendado de instancias | SKU de proceso recomendadas|
| --- | --- | --- |
| Controller | 2 | A1 |
| Front End | 2 | A1 |
| Administración | 2 | A3 |
| Publicador | 2 | A1 |
| Roles de trabajo web: compartidos | 2 | A1 |
| Roles de trabajo web: dedicados | 2 por nivel | A1 |

## <a name="controller-role"></a>Rol de controlador

**Mínima recomendada**: dos instancias de Estándar A1

El controlador de servicio de Azure App Service suele tener un consumo bajo de CPU, memoria y recursos de red. Sin embargo, para lograr una alta disponibilidad, debe tener dos controladores. Dos controladores también son el número máximo de controladores permitidos. Puede crear el segundo controlador de sitios web directamente desde el instalador durante la implementación.

## <a name="front-end-role"></a>Rol de front-end

**Mínima recomendada**: dos instancias de Estándar A1

El front-end enruta las solicitudes a los trabajos web según la disponibilidad de estos. Para lograr una alta disponibilidad, debe tener más de un front-end, y en total puede tener más de dos. A fin de planear la capacidad, tenga en cuenta que cada núcleo puede atender aproximadamente 100 solicitudes por segundo.

## <a name="management-role"></a>Rol de administración

**Mínima recomendada**: dos instancias de Estándar A3

El rol de administración de Azure App Service es responsable de los puntos de conexión de API y Azure Resource Manager de App Service, las extensiones de portales (portal de Functions, administración e inquilino) y el servicio de datos. El rol de servidor de administración solo suele requerir aproximadamente 4 GB de RAM en un entorno de producción. Sin embargo, puede experimentar niveles elevados de CPU cuando se realizan muchas tareas de administración (por ejemplo, la creación de sitios web). Para lograr una alta disponibilidad, debe tener más de un servidor asignado a este rol y al menos dos núcleos por servidor.

## <a name="publisher-role"></a>Rol de publicador

**Mínima recomendada**: dos instancias de Estándar A1

Si muchos usuarios están publicando simultáneamente, el rol de publicador puede experimentar un uso elevado de CPU. Para lograr una alta disponibilidad, asegúrese de disponer de más de un rol de publicador. El publicador solo controla el tráfico FTP o FTPS.

## <a name="web-worker-role"></a>Rol de trabajo web

**Mínima recomendada**: dos instancias de Estándar A1

Para lograr una alta disponibilidad, debe tener al menos cuatro roles de trabajo web, dos para el modo de sitio web compartido y dos para cada nivel de trabajo dedicado que planee ofrecer. Los modos de proceso dedicado y compartido proporcionan diferentes niveles de servicio a los inquilinos. Puede que necesite más roles de trabajo web si tiene muchos clientes:

- Que usen niveles de trabajo de modo de proceso dedicado (que consumen gran cantidad de recursos).
- Que se ejecuten en modo de proceso compartido.

Una vez que un usuario crea un plan de App Service para la SKU de modo de proceso dedicado, el número de trabajos web especificado en el plan de App Service ya no está disponible para los usuarios.

Para proporcionar Azure Functions a los usuarios en el modelo de plan de consumo, debe implementar los roles de trabajo web compartidos.

Cuando decida el número de roles de trabajo web compartidos que utilizará, revise estas consideraciones:

- **Memoria**: es el recurso más crítico para un rol de trabajo web. Si no hay memoria suficiente, afecta al rendimiento del sitio web cuando se intercambia memoria virtual del disco. Cada servidor necesita aproximadamente 1,2 GB de RAM para el sistema operativo. La RAM por encima de este umbral puede utilizarse para ejecutar sitios web.
- **Porcentaje de sitios web activos**: por lo general, aproximadamente el cinco por ciento de las aplicaciones en una instancia de Azure App Service en Azure Stack están activas. Sin embargo, el porcentaje de aplicaciones que están activas en un momento dado puede ser superior o inferior. Con una tasa de aplicaciones activas del cinco por ciento, el número máximo de aplicaciones a colocar en una instancia de Azure App Service en la implementación de Azure Stack debe ser menor que el número de sitios activos multiplicado por 20 (5 x 20 = 100).
- **Superficie de memoria promedio**: la superficie de memoria promedio en las aplicaciones observada en entornos de producción es de aproximadamente 70 MB. Con esta cantidad, la memoria asignada en todos los equipos con el rol de trabajo web o en las VM se puede calcular de la siguiente manera:

   `Number of provisioned applications * 70 MB * 5% - (number of web worker roles * 1044 MB)`

   Por ejemplo, si hay 5000 aplicaciones en el entorno que ejecuta diez roles de trabajo web, cada máquina virtual con el rol de trabajo web debe tener 7060 MB de memoria RAM:

   `5,000 * 70 * 0.05 – (10 * 1044) = 7060 (= about 7 GB)`

   Para obtener información sobre cómo agregar más instancias de trabajo, consulte [Incorporación de más roles de trabajo](azure-stack-app-service-add-worker-roles.md).

## <a name="file-server-role"></a>Rol de servidor de archivos

Para el rol de servidor de archivos, puede usar un servidor de archivos independiente para desarrollo y pruebas. Por ejemplo, cuando implemente Azure App Service en el Kit de desarrollo de Azure Stack (ASDK) puede usar la siguiente plantilla: https://aka.ms/appsvconmasdkfstemplate. Para fines de producción, debe utilizar un servidor de archivos preconfigurado de Windows o un servidor preconfigurado que no sea de Windows.

En entornos de producción, el rol de servidor de archivos experimenta una intensa actividad de E/S de disco. Puesto que contiene todos los archivos de contenido y de aplicación para los sitios web de usuario, debe configurar previamente uno de los siguientes recursos para que ejerza este rol:

- Servidor de archivos de Windows
- Clúster de servidores de archivos de Windows
- Servidor de archivos que no sea de Windows
- Clúster de servidores de archivos que no son de Windows
- Dispositivo NAS (almacenamiento conectado a la red)

Para obtener más información, consulte [Aprovisionamiento de un servidor de archivos](azure-stack-app-service-before-you-get-started.md#prepare-the-file-server).

## <a name="next-steps"></a>Pasos siguientes

Consulte los siguientes artículos para obtener más información:

[Antes de empezar a trabajar con App Service en Azure Stack](azure-stack-app-service-before-you-get-started.md)
