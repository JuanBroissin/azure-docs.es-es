---
title: Creación de grupos de administración para organizar los recursos de Azure
description: Aprenda a crear grupos de administración de Azure para administrar varios recursos.
author: rthorn17
manager: rithorn
ms.service: azure-resource-manager
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/20/2018
ms.author: rithorn
ms.topic: conceptual
ms.openlocfilehash: 699a9b7a371a004213419567d0672f56b5365598
ms.sourcegitcommit: eba6841a8b8c3cb78c94afe703d4f83bf0dcab13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2018
ms.locfileid: "52620121"
---
# <a name="create-management-groups-for-resource-organization-and-management"></a>Creación de grupos de administración para la organización y la administración de recursos

Los grupos de administración son contenedores que ayudan a administran el acceso, las directivas y el cumplimiento de varias suscripciones. Cree estos contenedores para construir una jerarquía eficaz y eficiente que pueda usarse con [Azure Policy](../policy/overview.md) y los [controles de acceso basados en roles de Azure](../../role-based-access-control/overview.md). Para obtener más información sobre los grupos de administración, consulte [Organización de los recursos con grupos de administración de Azure](overview.md).

El primer grupo de administración creado en el directorio puede tardar hasta 15 minutos en completarse. Hay procesos que se ejecutan la primera vez para configurar el servicio de grupos de administración dentro de Azure para su directorio. Recibirá una notificación cuando finalice el proceso.

## <a name="create-a-management-group"></a>Creación de un grupo de administración

Puede crear el grupo de administración mediante el portal, PowerShell o la CLI de Azure. Actualmente no se pueden usar plantillas de Resource Manager para crear grupos de administración.

### <a name="create-in-portal"></a>Crear en el portal

1. Inicie sesión en [Azure Portal](https://portal.azure.com).

1. Seleccione **Todos los servicios** > **Grupos de administración**.

1. En la página principal, seleccione **Nuevo grupo de administración**.

   ![Grupo principal](./media/main.png)

1. Rellene el campo de identificador de grupo de administración.

   - El **identificador de grupo de administración** es el identificador único de directorio que se usa para enviar comandos en este grupo de administración. Este identificador no es editable una vez creado el grupo, dado que se usa en todo el sistema de Azure para identificar ese grupo.
   - El campo de nombre para mostrar es el nombre que se muestra en Azure Portal. Un nombre para mostrar independiente es un campo opcional al crear el grupo de administración y se puede cambiar en cualquier momento.  

   ![Crear](./media/create_context_menu.png)  

1. Seleccione **Guardar**.

### <a name="create-in-powershell"></a>Crear en PowerShell

En PowerShell, use el cmdlet New-AzureRmManagementGroup:

```azurepowershell-interactive
New-AzureRmManagementGroup -GroupName 'Contoso'
```

**GroupName** es un identificador único que se crea. Este identificador lo usan otros comandos para hacer referencia a este grupo y no se puede cambiar más adelante.

Si quisiera que el grupo de administración mostrara un nombre diferente en Azure Portal, agregaría el parámetro **DisplayName** con la cadena. Por ejemplo, si quisiera crear un grupo de administración con el nombre de grupo de Contoso y el nombre para mostrar de "Grupo de Contoso", usaría el siguiente cmdlet:

```azurepowershell-interactive
New-AzureRmManagementGroup -GroupName 'Contoso' -DisplayName 'Contoso Group' -ParentId 'ContosoTenant'
```

Use el parámetro **ParentId** para que este grupo de administración se cree en una administración diferente.

### <a name="create-in-azure-cli"></a>Crear en la CLI de Azure

En al CLI de Azure, usará el comando az account management-group create.

```azurecli-interactive
az account management-group create --name 'Contoso'
```

## <a name="next-steps"></a>Pasos siguientes

Para más información sobre los grupos de administración, consulte:

- [Creación de grupos de administración para organizar los recursos de Azure](create.md)
- [Cambio, eliminación y administración de los grupos de administración](manage.md)
- [Revisión de grupos de administración en el módulo de recursos de Azure PowerShell](https://aka.ms/mgPSdocs)
- [Revisión de grupos de administración en la API REST](https://aka.ms/mgAPIdocs)
- [Revisión de grupos de administración en la CLI de Azure](https://aka.ms/mgclidoc)
