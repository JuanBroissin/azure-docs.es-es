---
title: archivo de inclusión
description: archivo de inclusión
services: virtual-machines
author: roygara
ms.service: virtual-machines
ms.topic: include
ms.date: 06/03/2018
ms.author: rogarana
ms.custom: include file
ms.openlocfilehash: 403f1cee04da17086a55adfbaed28388afd24d29
ms.sourcegitcommit: d4f728095cf52b109b3117be9059809c12b69e32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/10/2019
ms.locfileid: "54211909"
---
# <a name="azure-managed-disks-overview"></a>Introducción a Azure Managed Disks

Azure Managed Disks simplifica la administración de discos para las máquinas virtuales de Azure IaaS, ya que administra las [cuentas de almacenamiento](../articles/storage/common/storage-introduction.md) asociadas a los discos de la máquina virtual. Solo tiene que especificar el tipo ([HDD estándar](../articles/virtual-machines/windows/standard-storage.md), [SSD estándar](../articles/virtual-machines/windows/disks-standard-ssd.md) o [SSD Premium](../articles/virtual-machines/windows/premium-storage.md)) y el tamaño del disco que necesita, y Azure creará y administrará el disco automáticamente.

## <a name="benefits-of-managed-disks"></a>Ventajas de los discos administrados

Vea algunas de las ventajas que obtendrá al usar discos administrados, comenzando con este vídeo de Channel 9, [Better Azure VM Resiliency with Managed Disks](https://channel9.msdn.com/Blogs/Azure/Managed-Disks-for-Azure-Resiliency) (Mejorar la resistencia de las máquinas virtuales de Azure con discos administrados).
<br/>
> [!VIDEO https://channel9.msdn.com/Blogs/Azure/Managed-Disks-for-Azure-Resiliency/player]

### <a name="simple-and-scalable-vm-deployment"></a>La implementación de las máquina virtuales es simple y escalable

Managed Disks controla automáticamente el almacenamiento en segundo plano. Anteriormente, era preciso crear cuentas de almacenamiento que contuvieran los discos (archivos VHD) de las máquinas virtuales de Azure. Al escalar verticalmente, era preciso asegurarse de que se habían creado cuentas de almacenamiento adicionales, para que no se superase el límite de IOPS de almacenamiento con cualquiera de los discos. Si Managed Disks controla el almacenamiento, desaparecen los límites de la cuenta de almacenamiento (por ejemplo, 20 000 IOPS por cuenta). Tampoco es preciso copiar las imágenes personalizadas (archivos VHD) en varias cuentas de almacenamiento. Puede administrarlas en una ubicación central (una cuenta de almacenamiento por región de Azure) y utilizarlas para crear cientos de máquinas virtuales en una suscripción.

Managed Disks le permitirá crear un máximo de 50 000 **discos** de máquina virtual de un tipo en una suscripción por región, lo que le permitirá crear miles de **máquinas virtuales** en una sola suscripción. Esta característica también aumenta la escalabilidad de [Virtual Machine Scale Sets](../articles/virtual-machine-scale-sets/virtual-machine-scale-sets-overview.md), ya que permite crear hasta mil máquinas virtuales en un conjunto de escalado de máquinas virtuales con una imagen de Marketplace.

### <a name="better-reliability-for-availability-sets"></a>Mayor confiabilidad para los conjuntos de disponibilidad

Managed Disks proporciona una mayor confiabilidad para los conjuntos de disponibilidad, ya que garantiza que los discos de las [máquinas virtuales de un conjunto de disponibilidad](../articles/virtual-machines/windows/manage-availability.md#use-managed-disks-for-vms-in-an-availability-set) están suficientemente aislados entre sí para evitar puntos únicos de error. Los discos se colocan automáticamente en diferentes unidades de escalado de almacenamiento (marcas). Si se produce un error en una marca debido a un error de hardware o software, solo dejarán de funcionar las instancias de máquina virtual con discos de dichas marcas. Por ejemplo, suponga que tiene una aplicación que se ejecuta en cinco máquinas virtuales y estas están en un conjunto de disponibilidad. No todos los discos de dichas máquinas virtuales se almacenarán en la misma marca, por lo que, si se produce un error en una, no se detiene la ejecución de las restantes instancias de la aplicación.

### <a name="highly-durable-and-available"></a>Mayor durabilidad y disponibilidad

Los discos de Azure están diseñados para ofrecer una disponibilidad del 99,999 %. Descanse tranquilo sabiendo que tiene tres réplicas de sus datos que aportan alta durabilidad. Si una o incluso dos réplicas experimentan problemas, las réplicas restantes garantizan la persistencia de los datos y una gran tolerancia a errores. Esta arquitectura ha contribuido a que Azure destaque en el sector por ofrecer, de manera constante, durabilidad de nivel empresarial para discos IaaS, con una tasa de error anualizada del 0 %.

### <a name="granular-access-control"></a>Control de acceso pormenorizado

Puede usar el [control de acceso basado en rol de Azure (RBAC)](../articles/role-based-access-control/overview.md) para asignar permisos concretos a un disco administrado a uno o varios usuarios. Managed Disks expone varias operaciones, entre las que se incluyen la lectura, escritura (creación o actualización), eliminación y recuperación de un [identificador URI de la firma de acceso compartido (SAS) URI](../articles/storage/common/storage-dotnet-shared-access-signature-part-1.md) para el disco. Puede conceder acceso solo a las operaciones necesarias para que una persona pueda realizar su trabajo. Por ejemplo, si no desea que una persona copie un disco administrado a una cuenta de almacenamiento, puede decidir no conceder acceso a la acción de exportación de dicho disco administrado. De igual forma, si no desea que una persona use URI de SAS para copiar un disco administrado, puede elegir no conceder dicho permiso al disco administrado.

### <a name="azure-backup-service-support"></a>Soporte técnico del servicio Azure Backup

Utilice el servicio Azure Backup con Managed Disks para crear un trabajo de copia de seguridad con copias de seguridad basadas en tiempo, fácil restauración de la máquina virtual y directivas de retención de copia de seguridad. Managed Disks admite solo almacenamiento con redundancia local (LRS) como opción de replicación. Se conservan tres copias de los datos en una única región. Para recuperación ante desastres regionales, debe realizar una copia de los discos de máquina virtual en una región distinta con el [servicio Azure Backup](../articles/backup/backup-introduction-to-azure-backup.md) y una cuenta de almacenamiento GRS como almacén de Backup. Actualmente, Azure Backup admite discos de hasta 4 TB de tamaño, vea [Instant Restore](../articles/backup/backup-instant-restore-capability.md) (Restauración instantánea) para obtener asistencia con los discos de 4 TB. Para más información, consulte [Uso del servicio de Azure Backup para máquinas virtuales con Managed Disks](../articles/backup/backup-introduction-to-azure-backup.md#using-managed-disk-vms-with-azure-backup).

## <a name="pricing-and-billing"></a>Precios y facturación

Al usar Managed Disks, se aplican las siguientes consideraciones de facturación:

* Tipo de almacenamiento

* Tamaño del disco

* Número de transacciones

* Transferencias de datos de salida

* Instantáneas de disco administradas (copia de disco completo)

Veamos estas opciones más detalladamente.

**Storage type** (Tipo de almacenamiento): Managed Disks ofrece tres nivel de rendimiento: [HDD estándar](../articles/virtual-machines/windows/standard-storage.md), [SSD estándar](../articles/virtual-machines/windows/disks-standard-ssd.md) y [Prémium](../articles/virtual-machines/windows/premium-storage.md). La facturación de un disco administrado depende del tipo de almacenamiento que se haya seleccionado para el disco.

**Tamaño del disco**: la facturación de los discos administrados depende del tamaño aprovisionado del disco. Azure asigna el tamaño aprovisionado (redondeado) a la opción de disco de Managed Disks más cercana, como se especifica en las tablas siguientes. Cada disco administrado se asigna a uno de los tamaños aprovisionados admitidos y se factura según corresponda. Por ejemplo, si crea un disco administrado estándar y especifica un tamaño aprovisionado de 200 GB, se le facturará según los precios del tipo de disco S15.

Estos son los tamaños de disco disponibles para un disco administrado premium; los tamaños que se indican con un asterisco están actualmente en versión preliminar:

| **Tipo de disco<br> administrado SSD Premium** | **P4** | **P6** | **P10** | **P15** | **P20** | **P30** | **P40** | **P50** | **P60*** | **P70*** | **P80*** |
|------------------|---------|---------|--------|--------|--------|----------------|----------------|----------------|----------------|----------------|----------------|
| Tamaño del disco        | 32 GiB  | 64 GiB  | 128 GB | 256 GiB | 512 GB | 1024 GiB (1 TiB) | 2048 GiB (2 TiB) | 4095 GiB (4 TiB) | 8192 GiB (8 TiB) | 16 384 GiB (16 TiB) | 32 767 GiB (TiB) |

Estos son los tamaños de disco disponibles para un disco administrado SSD estándar; los tamaños que se indican con un asterisco están actualmente en versión preliminar:

| **Tipo de disco<br> administrado SSD estándar** | **E10** | **E15** | **E20** | **E30** | **E40** | **E50** | **E60*** | **E70*** | **E80*** |
|------------------|--------|--------|--------|----------------|----------------|----------------|----------------|----------------|----------------|
| Tamaño del disco        | 128 GB | 256 GiB | 512 GB | 1024 GiB (1 TiB) | 2048 GiB (2 TiB) | 4095 GiB (4 TiB) | 8192 GiB (8 TiB) | 16 384 GiB (16 TiB) | 32 767 GiB (TiB) |

Estos son los tamaños de disco disponibles para un disco administrado HDD estándar; los tamaños que se indican con un asterisco están actualmente en versión preliminar:

| **Tipo de disco<br> administrado HDD estándar** | **S4** | **S6** | **S10** | **S15** | **S20** | **S30** | **S40** | **S50** | **S60*** | **S70*** | **S80*** |
|------------------|---------|---------|--------|--------|--------|----------------|----------------|----------------|----------------|----------------|----------------|
| Tamaño del disco        | 32 GiB  | 64 GiB  | 128 GB | 256 GiB | 512 GB | 1024 GiB (1 TiB) | 2048 GiB (2 TiB) | 4095 GiB (4 TiB) | 8192 GiB (8 TiB) | 16 384 GiB (16 TiB) | 32 767 GiB (TiB) |

**Número de transacciones**: se le factura por el número de transacciones que realiza en un disco administrado estándar.

Los discos SSD estándar usan un tamaño de unidad de E/S de 256 KB. Si el tamaño de los datos transferidos es inferior a 256 KB, se considera una unidad de E/S. Los tamaños de E/S más grandes se cuentan como varias operaciones de E/S con un tamaño de 256 KB. Por ejemplo, una E/S de 1100 KB se cuenta como cinco unidades de E/S.

Las transacciones de un disco administrado premium no tienen coste.

**Transferencias de datos de salida**: [transferencias de datos de salida](https://azure.microsoft.com/pricing/details/data-transfers/) (datos que salen de los centros de datos de Azure) incurren en la facturación por el uso de ancho de banda.

Para obtener información detallada acerca de los precios de Managed Disks, consulte [Precios de Managed Disks](https://azure.microsoft.com/pricing/details/managed-disks).


## <a name="managed-disk-snapshots"></a>Instantáneas de disco administradas

Una instantánea administrada es una copia completa de solo lectura de un disco administrado que se almacena como disco administrado estándar de forma predeterminada. Con las instantáneas, puede realizar una copia de seguridad de sus discos administrados en cualquier momento. Estas instantáneas existen independientemente del disco de origen y se pueden usar para una instancia de Managed Disks. Se facturan según el tamaño usado. Por ejemplo, si crea una instantánea de un disco administrado con capacidad aprovisionada de 64 GiB y el tamaño de datos usado real es de 10 GiB, solo se le cobrará por el tamaño de datos usado de 10 GiB.  

Actualmente, las [instantáneas incrementales](../articles/virtual-machines/windows/incremental-snapshots.md) no son compatibles con Managed Disks.

Para más información acerca de cómo crear instantáneas con Managed Disks, consulte estos recursos:

* [Creación de una copia del disco duro virtual que se almacene como un disco administrado mediante instantáneas en Windows](../articles/virtual-machines/windows/snapshot-copy-managed-disk.md)
* [Creación de una copia del disco duro virtual que se almacene como un disco administrado mediante instantáneas en Linux](../articles/virtual-machines/linux/snapshot-copy-managed-disk.md)

## <a name="images"></a>Imágenes

Managed Disks también admite la creación de una imagen personalizada administrada. Puede crear una imagen desde un disco duro virtual personalizado en una cuenta de almacenamiento, o bien directamente desde una máquina virtual generalizada (con Sysprep). Este proceso captura en una sola imagen todos los discos administrados con una máquina virtual, entre los que se incluyen tanto el disco de datos como el del sistema operativo. Esta imagen personalizada administrada permite crear cientos de máquinas virtuales con la imagen personalizada sin necesidad de copiar o administrar cuentas de almacenamiento.

Para más información sobre la creación de imágenes, consulte los artículos siguientes:

* [How to capture a managed image of a generalized VM in Azure](../articles/virtual-machines/windows/capture-image-resource.md) (Captura de una imagen administrada de una máquina virtual generalizada en Azure)
* [How to generalize and capture a Linux virtual machine using the Azure CLI 2.0](../articles/virtual-machines/linux/capture-image.md) (Procedimiento de generalización y captura de una máquina virtual Linux con la CLI de Azure 2.0)

## <a name="images-versus-snapshots"></a>Imágenes frente a instantáneas

A menudo se ve la palabra "imagen" utilizada con máquinas virtuales, pero ahora también se puede ver "instantáneas". Es importante saber en qué se diferencian estos términos. Con Managed Disks, es posible tomar una imagen de una máquina virtual generalizada que se ha desasignado. Dicha imagen incluirá todos los discos conectados a la máquina virtual, se puede usar para crear una máquina virtual e incluirá todos los discos.

Una instantánea es una copia de un disco en un momento dado. Solo se aplica a un disco. Si tiene una máquina virtual con un solo disco (el del sistema operativo), puede tomar una instantánea o una imagen del mismo y crear una máquina virtual a partir de cualquiera de ellas.

¿Qué sucede si una máquina virtual tiene cinco discos y se seccionan? Puede tomar una instantánea de cada uno de los discos, pero en la máquina virtual no se conoce el estado de los discos (las instantáneas solo "conocen" un disco). En este caso, las instantáneas tendrían que coordinarse entre sí, algo que actualmente no se no se admite.

## <a name="managed-disks-and-encryption"></a>Managed Disks y cifrado

Hay dos tipos de cifrado que comentar en referencia a Managed Disks. El primero de ellos es el cifrado de servicio de almacenamiento (SSE), que se realiza mediante el servicio Storage. El segundo es Azure Disk Encryption, que se puede habilitar en los discos de datos y del sistema operativo de las máquinas virtuales.

### <a name="storage-service-encryption-sse"></a>cifrado del servicio de almacenamiento (SSE)

[Cifrado del servicio Azure Storage](../articles/storage/common/storage-service-encryption.md) proporciona cifrado en reposo y protege sus datos con el fin de cumplir con los compromisos de cumplimiento y seguridad de su organización. SSE está habilitado de forma predeterminada para todos los discos administrados, instantáneas e imágenes en todas las regiones donde hay discos administrados. Desde el 10 de junio de 2017, todos los nuevos discos administrados, instantáneas e imágenes, así como los datos nuevos que se escriban en discos administrados existentes, se cifran automáticamente en reposo con claves administradas por Microsoft de forma predeterminada. Visite la [página de preguntas más frecuentes sobre discos administrados](../articles/virtual-machines/windows/faq-for-disks.md#managed-disks-and-storage-service-encryption) para obtener más detalles.

### <a name="azure-disk-encryption-ade"></a>Azure Disk Encryption (ADE)

Azure Disk Encryption le permite cifrar los discos de datos y del sistema operativo usados por una máquina virtual de IaaS. Este cifrado incluye discos administrados. Para Windows, las unidades se cifran mediante la tecnología de cifrado de BitLocker estándar del sector. Para Linux, los discos se cifran mediante la tecnología DM-Crypt. El proceso de cifrado se integra con Azure Key Vault para permitirle controlar y administrar las claves de cifrado del disco. Para más información, consulte [Azure Disk Encryption para máquinas virtuales IaaS de Windows y Linux](../articles/security/azure-security-disk-encryption.md).

## <a name="next-steps"></a>Pasos siguientes

Para más información acerca de Managed Disks, consulte los siguientes artículos.

### <a name="get-started-with-managed-disks"></a>Introducción a Managed Disks

* [Creación de una máquina virtual con Resource Manager y PowerShell](../articles/virtual-machines/scripts/virtual-machines-windows-powershell-sample-create-vm.md)

* [Creación de una máquina virtual con Linux desde cero con la CLI de Azure](../articles/virtual-machines/linux/quick-create-cli.md)

* [Conexión de un disco de datos administrado a una máquina virtual Windows con PowerShell](../articles/virtual-machines/windows/attach-disk-ps.md)

* [Adición de un disco administrado a una máquina virtual Linux](../articles/virtual-machines/linux/add-disk.md)

* [Scripts d ejemplo de PowerShell de Managed Disks](https://github.com/Azure-Samples/managed-disks-powershell-getting-started)

* [Usar Managed Disks en plantillas de Azure Resource Manager](../articles/virtual-machines/windows/using-managed-disks-template-deployments.md)

### <a name="compare-managed-disks-storage-options"></a>Comparación de las opciones de almacenamiento de Managed Disks

* [Discos SSD premium](../articles/virtual-machines/windows/premium-storage.md)

* [Discos SSD y HDD estándar](../articles/virtual-machines/windows/standard-storage.md)

### <a name="operational-guidance"></a>Guía de operaciones

* [Migración desde AWS y otras plataformas a Managed Disks en Azure](../articles/virtual-machines/windows/on-prem-to-azure.md)

* [Conversión de máquinas virtuales de Azure a discos administrados en Azure](../articles/virtual-machines/windows/migrate-to-managed-disks.md)
