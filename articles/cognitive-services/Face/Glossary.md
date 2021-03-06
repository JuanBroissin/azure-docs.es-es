---
title: Glosario del servicio Face API
titleSuffix: Azure Cognitive Services
description: En el glosario se explican los términos que puede encontrar cuando use el servicio Face API.
services: cognitive-services
author: SteveMSFT
manager: nitinme
ms.service: cognitive-services
ms.subservice: face-api
ms.topic: conceptual
ms.date: 03/01/2018
ms.author: sbowles
ms.openlocfilehash: ad3ea9b0cde16d5c9645e7eacee9ba7f9a08ed2d
ms.sourcegitcommit: 90cec6cccf303ad4767a343ce00befba020a10f6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55859172"
---
# <a name="glossary"></a>Glosario

## <a name="a"></a>Una 

#### <a name="attributes"></a>Atributos

Los atributos son opcionales en los resultados de la detección, como la [edad](#Age-Attribute), el [género](#Gender-Attribute), la [posición de la cabeza](#Head-Pose-Attribute), el [vello facial](#Facial-Hair-Attribute) y la [sonrisa](#Smile-Attribute).
Se pueden obtener de la API de detección especificando los parámetros de consulta: returnFaceAttributes. Los atributos ofrecen información adicional en relación con las [caras](#Face) seleccionadas; además de la [id. de cara](#Face-ID) y el [rectángulo](#Face-Rectangle).

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

#### <a name="age-attribute"></a>Edad (atributo)

La edad es uno de los [atributos](#Attributes) que describen la edad de una cara determinada. El atributo de edad es opcional en los resultados de la detección y se puede controlar con una solicitud de detección mediante la especificación del parámetro returnFaceAttributes.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

## <a name="b"></a>b

## <a name="c"></a>C

#### <a name="candidate"></a>Candidato

Los candidatos son esencialmente los resultados de la [identificación](#Identification) (por ejemplo, las personas identificadas y el nivel de confianza de las detecciones). Un candidato se representa mediante la [id. de persona](#Person-ID) y la [confianza](#Confidence), que indican que la persona se ha identificado con un alto nivel de confianza.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395239) (Cara: identificar).

#### <a name="confidence"></a>Confianza

La confianza es una medida que revela la similitud entre las [caras](#Face) o las [personas](#Person) en valores numéricos y que se usa en la [identificación](#Identification) y la [comprobación](#Verification) para indicar las similitudes en los resultados de la búsqueda, identificados y comprobados.

Para más información, consulte las guías siguientes: [Face - Find Similar](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395237), (Cara. buscar similares) [Face - Identify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395239) (Cara. identificar), [Face - Verify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523a) (Cara: comprobar).

## <a name="d"></a>D

#### <a name="detectionface-detection"></a>Detección/detección de caras

La detección de caras es la acción de localizar caras en imágenes. Los usuarios pueden cargar una imagen o especificar una dirección URL de imagen en la solicitud. Las caras detectadas se devuelven con las [id. de cara](#Face-ID) que indican una identidad única en Face API. Los rectángulos indican las ubicaciones de la cara en la imagen en píxeles, así como los [atributos](#Attributes) opcionales para cada cara, como la [edad](#Age-Attribute), el [género](#Gender-Attribute), la [posición de la cabeza](#Head-Pose-Attribute), el [vello facial](#Facial-Hair-Attribute) y la [sonrisa](#Smile-Attribute).

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

## <a name="e"></a>E

## <a name="f"></a>F

#### <a name="face"></a>Caras

Cara es un término unificado para los resultados que se derivan de Face API relacionados con las caras detectadas. En última instancia, la cara se representa mediante una identidad unificada ([id. de cara](#Face-ID)), una región especificada en las imágenes ([rectángulo de cara](#Face-Rectangle)) y los atributos adicionales relacionados con la cara, como la [edad](#Age-Attribute), el [género](#Gender-Attribute), los puntos de referencia y la [posición de la cabeza](#Head-Pose-Attribute). Además, las caras se pueden devolver en la detección.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

#### <a name="face-api"></a>Face API

Face API es una API basada en la nube que proporciona los algoritmos más avanzados para la detección y el reconocimiento de caras. La funcionalidad principal de Face API puede dividirse en dos categorías: detección de caras con atributos y [reconocimiento](#Recognition) de caras.

Para más información, consulte las guías siguientes: [Introducción a Face API](./Overview.md), [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar), [Face - Find Similar](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395237) (Cara: búsqueda de similares), [Face - Group](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395238) (Cara: agrupar), [Face - Identify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395239) (Cara: identificar), [Face - Verify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523a) (Cara: comprobar).

#### <a name="face-attributesfacial-attributes"></a>Atributos de cara/atributos faciales

Vea [Atributos](#Attributes).

#### <a name="face-id"></a>Id. de cara

La id. de cara se deriva de los resultados de la detección, en los que una cadena representa un [cara](#Face) en [Face API](#Face-API).

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

#### <a name="face-landmarksfacial-landmarks"></a>Puntos de referencia de cara/puntos de referencia faciales

Los puntos de referencia son opcionales en los resultados de la detección y son puntos faciales semánticos, como los ojos, la nariz y la boca (ilustrados en la figura siguiente). Los puntos de referencia se pueden controlar con una solicitud de detección mediante el número booleano returnFaceLandmarks. Si returnFaceLandmarks se establece en true, las caras devueltas tendrán atributos de punto de referencia.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

![HowToDetectFace](./Images/landmarks.1.jpg)

#### <a name="face-rectangle"></a>Rectángulo de cara

El rectángulo de cara se deriva de los resultados de la detección y es un rectángulo vertical (izquierda, arriba, ancho, alto) en las imágenes en píxeles. La esquina superior izquierda de una [cara](#Face) (izquierda, arriba), además del ancho y alto, indica los tamaños de la cara en los ejes X e Y respectivamente.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

#### <a name="facial-hair-attribute"></a>Vello facial (atributo)

El vello facial es uno de los [atributos](#Attributes) utilizado para describir la longitud del vello facial de las caras disponibles. El atributo de vello facial es opcional en los resultados de la detección y se puede controlar con una solicitud de detección de returnFaceAttributes. Si returnFaceAttributes contiene "facialHair", las caras devueltas contendrán atributos de vello facial.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

#### <a name="facelist"></a>FaceList

FaceList es una colección de [PersistedFace](#PersistedFace) y es la unidad de [buscar similar](#Find-Similar). Un elemento FaceList tiene una [id. de FaceList](#FaceList-ID), además de otros atributos como el nombre y los datos de usuario.

Para más información, consulte las guías siguientes: [FaceList - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039524b) (Creación de una lista de caras), [FaceList - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039524c) (Obtención de una lista de caras).

#### <a name="facelist-id"></a>Id. de FaceList

La id. de FaceList es una cadena proporcionada por el usuario que se utiliza como identificador de un elemento [FaceList](#FaceList). La id. de FaceList debe ser única dentro de la suscripción.

Para más información, consulte las guías siguientes: [FaceList - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039524b) (Creación de una lista de caras), [FaceList - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039524c) (Obtención de una lista de caras).

#### <a name="find-similar"></a>Buscar similares

Esta API se utiliza para buscar o consultar caras similares basadas en una colección de caras. Las caras de consultas y las colecciones de caras se representan como [id. de cara](#Face-ID) o [id. de FaceList](#FaceList-ID)/[id. de LargeFaceList](#LargeFaceList-ID) en la solicitud. Los resultados devueltos son caras similares buscadas, representadas por las [id. de cara](#Face-ID) o las id. de PersistedFace.

Para más información, consulte las guías siguientes: [Face - Find Similar](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395237) (Búsqueda de caras similares), [LargeFaceList - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a157b68d2de3616c086f2cc) (LargeFaceList: crear), [FaceList - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039524b) (FaceList: crear).

## <a name="g"></a>G

#### <a name="gender-attribute"></a>Género (atributo)

El género es uno de los [atributos](#Attributes) utilizado para describir los géneros de las caras disponibles. El atributo de género es opcional en los resultados de la detección y se puede controlar con una solicitud de detección de returnFaceAttributes. Si returnFaceAttributes contiene "gender", las caras devueltas tendrán atributos de género.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

#### <a name="grouping"></a>Agrupación

La agrupación de caras es la agrupación de una colección de caras según las similitudes faciales. Las colecciones de caras se indican mediante las colecciones de id. de cara en la solicitud. Como resultado de la agrupación, las caras similares se agrupan como [grupos](#Groups) y las caras que no son similares a cualquier otra cara se combinan como un grupo desordenado. Como máximo, hay un [grupo desordenado](#Messy-Group) en el resultado de la agrupación.

Para más detalles, consulte la guía [Face - Group](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395238) (Cara: grupo).

#### <a name="groups"></a>Grupos

Los grupos se derivan de los resultados de la [agrupación](#Grouping). Cada grupo contiene una colección de caras similares, donde las caras se indican mediante las [id. de cara](#Face-ID).

Para más detalles, consulte la guía [Face - Group](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395238) (Cara: grupo).

## <a name="h"></a>H

#### <a name="head-pose-attribute"></a>Posición de la cabeza (atributo)

La posición de la cabeza es uno de los [atributos](#Attributes) que representa la orientación de la cara en un espacio 3D según los ángulos de rotación alrededor de los ejes X (pitch), Y (yaw) y Z (roll), tal y como se muestra en la siguiente ilustración. Los intervalos de valores de la rotación alrededor del eje Z (roll) e Y (yaw) son [-180, 180] y [-90, 90] en grados. En la versión actual, el valor de la rotación alrededor del eje X (pitch) procedente de la detección es siempre 0. El atributo de posición de la cabeza es opcional en los resultados de la detección y se puede controlar con una solicitud de detección del parámetro returnFaceAttributes. Si el parámetro returnFaceAttributes contiene "headPose", las caras devueltas tendrán atributos de posición de la cabeza.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

![GlossaryHeadPose](./Images/headpose.1.jpg)

## <a name="i"></a>I

#### <a name="identification"></a>Identificación

La identificación es identificar una o más caras de LargePersonGroup/PersonGroup.
[PersonGroup](#PersonGroup)/[LargePersonGroup](#LargePersonGroup) es una colección de [personas](#Person).
Las caras y LargePersonGroup/PersonGroup se representan mediante las [id. de cara](#Face-ID) y las [id. de LargePersonGroup](#LargePersonGroup-ID)/[id. de PersonGroup](#PersonGroup-ID) respectivamente en la solicitud.
Los resultados identificados son los [candidatos](#Candidate), representados por [personas](#Person) con confianza.
Las distintas caras de la entrada se consideran por separado y cada cara tendrá su propio resultado identificado.

> [!NOTE]
> El elemento LargePersonGroup/PersonGroup se debe entrenar correctamente antes de la identificación. Si el elemento LargePersonGroup/PersonGroup no se entrena o el [estado](#Status-Train) del entrenamiento no se muestra como "correcto" (es decir, "en ejecución", "error" o "tiempo de expiración"), la respuesta de la solicitud es 400.
> 

Para más información, consulte las guías siguientes: [Face - Identify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395239) (Cara: identificar), [LargePersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adcba3a7b9412a4d53f40) (Persona LargePersonGroup: crear), [LargePersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acdee6ac60f11b48b5a9d) (LargePersonGroup: crear), [LargePersonGroup - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599ae2d16ac60f11b48b5aa4) (LargePersonGroup: entrenar), [PersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523c) (Persona PersonGroup: crear), [PersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395244) (PersonGroup: crear) y [PersonGroup - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395249) (PersonGroup: entrenar).

#### <a name="isidentical"></a>IsIdentical

IsIdentical es un campo booleano de los resultados de la [comprobación](#Verification) que indica si dos caras pertenecen a la misma persona.

Para más detalles, consulte la guía [Face - Verify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523a) (Cara: verificar).

## <a name="j"></a>J

## <a name="k"></a>K

## <a name="l"></a>L

#### <a name="landmarks"></a>Puntos de referencia

Vea los puntos de referencia de cara.

#### <a name="largefacelist"></a>LargeFaceList

LargeFaceList es una colección de [PersistedFace](#PersistedFace) y es la unidad de [buscar similar](#Find-Similar). Un elemento LargeFaceList tiene una [id. de LargeFaceList](#LargeFaceList-ID), además de otros atributos como el nombre y los datos de usuario.

Para más información, consulte las guías siguientes: [LargeFaceList - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a157b68d2de3616c086f2cc) (LargeFaceList: crear), [LargeFaceList - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a15827cd2de3616c086f2ce) (LargeFaceList: obtener), [LargeFaceList - List Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a158db4d2de3616c086f2d6) (LargeFaceList: enumerar caras).

#### <a name="largefacelist-id"></a>Id. de LargeFaceList

La id. de LargeFaceList es una cadena proporcionada por el usuario que se utiliza como identificador de un elemento [LargeFaceList](#LargeFaceList). La id. de LargeFaceList debe ser única dentro de la suscripción.

Para más información, consulte las guías siguientes: [LargeFaceList - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a157b68d2de3616c086f2cc) (LargeFaceList: crear), [LargeFaceList - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a15827cd2de3616c086f2ce) (LargeFaceList: obtener).

#### <a name="largepersongroup"></a>LargePersonGroup

LargePersonGroup es una colección de [personas](#Person) y es la unidad de la [identificación](#Identification). Un elemento LargePersonGroup tiene una [id. de LargePersonGroup](#LargePersonGroup-ID), además de otros atributos como el nombre y los datos de usuario.

Para más información, consulte las guías siguientes: [LargePersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acdee6ac60f11b48b5a9d) (LargePersonGroup: crear), [LargePersonGroup - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acebb6ac60f11b48b5a9e) (LargePersonGroup: obtener), [LargePersonGroup Person - List](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adda06ac60f11b48b5aa1) (Persona LargePersonGroup: enumerar).

#### <a name="largepersongroup-id"></a>Id. de LargePersonGroup

La id. de LargePersonGroup es una cadena proporcionada por el usuario y que se utiliza como identificador de un elemento [LargePersonGroup](#LargePersonGroup). La id. de LargePersonGroup debe ser única dentro de la suscripción.

Para más información, consulte las guías siguientes: [LargePersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acdee6ac60f11b48b5a9d) (LargePersonGroup: crear), [LargePersonGroup - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acebb6ac60f11b48b5a9e).(LargePersonGroup: obtener)

## <a name="m"></a>M

#### <a name="messy-group"></a>Grupo desordenado

El grupo desordenado se deriva de los resultados de la [agrupación](#Grouping) y que contiene caras que no son similares a ningún otro tipo. Cada cara de un grupo desordenado se indica mediante la [id. de cara](#Face-ID).

Para más detalles, consulte la guía [Face - Group](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395238) (Cara: grupo).

## <a name="n"></a>N

#### <a name="name-person"></a>Nombre (persona)

El nombre es una cadena descriptiva para la [persona](#Person). A diferencia de la [id. de persona](#Person-ID), el nombre de personas se puede duplicar dentro de un grupo.

Para más información, consulte las guías siguientes: [LargePersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adcba3a7b9412a4d53f40) (Persona LargePersonGroup: crear), [LargePersonGroup Person - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599add376ac60f11b48b5aa0) (Persona LargePersonGroup: obtener), [PersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523c) (Persona PersonGroup: crear), [PersonGroup Person - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523f) (Persona PersonGroup: obtener).

#### <a name="name-largepersongrouppersongroup"></a>Nombre (LargePersonGroup/PersonGroup)

El nombre también es una cadena descriptiva del usuario para [LargePersonGroup](#LargePersonGroup)/[PersonGroup](#PersonGroup). A diferencia de la [id. de LargePersonGroup](#LargePersonGroup-ID)/[id. de PersonGroup](#PersonGroup-ID), el nombre de LargePersonGroups/PersonGroups se puede duplicar dentro de una suscripción.

Para más información, consulte las guías siguientes: [LargePersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acdee6ac60f11b48b5a9d) (LargePersonGroup: crear), [LargePersonGroup - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acebb6ac60f11b48b5a9e) (LargePersonGroup: obtener), [PersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395244) (PersonGroup: crear), [PersonGroup - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395246). (PersonGroup: obtener)

## <a name="o"></a>O

## <a name="p"></a>P

#### <a name="persistedface"></a>PersistedFace

PersistedFace es una estructura de datos en Face API. Un elemento PersistedFace tiene una id. de PersistedFace, además de otros atributos como el nombre y los datos de usuario.

Para más información, consulte las guías siguientes: [LargeFaceList - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a158c10d2de3616c086f2d3) (LargeFaceList: agregar cara), [FaceList - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395250) (FaceList: agregar cara), [LargePersonGroup Person - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adf2a3a7b9412a4d53f42) (Persona LargePersonGroup: agregar cara), [PersonGroup Person - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523b) (Persona PersonGroup: agregar cara).

#### <a name="person-id"></a>Id. de persona

La id. de persona se genera cuando se crea correctamente un elemento [PersistedFace](#PersistedFace). Se crea una cadena para representar esta cara en [Face API](#Face-API).

Para más información, consulte las guías siguientes: [LargeFaceList - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a158c10d2de3616c086f2d3) (LargeFaceList: agregar cara), [FaceList - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395250) (FaceList: agregar cara), [LargePersonGroup Person - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adf2a3a7b9412a4d53f42) (Persona LargePersonGroup: agregar cara), [PersonGroup Person - Add Face](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523b) (Persona PersonGroup: agregar cara).

#### <a name="person"></a>Persona

La persona es una estructura de datos administrada en Face API. La persona tiene una [id. de persona](#Person-ID), además de otros atributos como el nombre, una colección de elementos [PersistedFace](#PersistedFace) y datos de usuario.

Para más información, consulte las guías siguientes: [LargePersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adcba3a7b9412a4d53f40) (Persona LargePersonGroup: crear), [LargePersonGroup Person - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599add376ac60f11b48b5aa0) (Persona LargePersonGroup: obtener), [PersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523c) (Persona PersonGroup: crear), [PersonGroup Person - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523f) (Persona PersonGroup: obtener).

#### <a name="person-id"></a>Id. de persona

La id. de persona se genera cuando se crea correctamente una [persona](#Person). Se crea una cadena para representar esta persona en [Face API](#Face-API).

Para más información, consulte las guías siguientes: [LargePersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adcba3a7b9412a4d53f40) (Persona LargePersonGroup: crear), [LargePersonGroup Person - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599add376ac60f11b48b5aa0) (Persona LargePersonGroup: obtener), [PersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523c) (Persona PersonGroup: crear), [PersonGroup Person - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523f) (Persona PersonGroup: obtener).

#### <a name="persongroup"></a>PersonGroup

PersonGroup es una colección de [personas](#Person) y es la unidad de la [identificación](#Identification). Un elemento PersonGroup tiene una [id. de PersonGroup](#PersonGroup-ID), además de otros atributos como el nombre y los datos de usuario.

Para más información, consulte las guías siguientes: [PersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395244) (PersonGroup: crear), [PersonGroup - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395246) (PersonGroup: obtener), [PersonGroup Person - List](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395241) (Persona PersonGroup: enumerar).

#### <a name="persongroup-id"></a>Id. de PersonGroup

La id. de PersonGroup es una cadena proporcionada por el usuario que se utiliza como identificador de un elemento [PersonGroup](#PersonGroup). La id. de grupo debe ser única dentro de la suscripción.

Para más información, consulte las guías siguientes: [PersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395244) (PersonGroup: crear), [PersonGroup - Get](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395246) (PersonGroup: obtener).

#### <a name="pose-attribute"></a>Posición (atributo)

Vea [Posición de la cabeza](#Head-Pose-Attribute).

## <a name="q"></a>Q

## <a name="r"></a>R

#### <a name="recognition"></a>Reconocimiento

El reconocimiento es un área de aplicación popular para las tecnologías de cara, como [buscar similar](#Find-Similar), [agrupación](#Grouping), [identificar](#Identification) o [comprobar si dos caras son la misma o no ](#Verification).

Para más información, consulte las guías siguientes: [Face - Find Similar](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395237) (Cara: buscar similares), [Face - Group](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395238) (Cara: agrupar), [Face - Identify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395239) (Cara: identificar), [Face - Verify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523a) (Cara: comprobar).

#### <a name="rectangle-face"></a>Rectángulo (cara)

Vea [rectángulo de cara](#Face-Rectangle).

## <a name="s"></a>S

#### <a name="similar-face-searching"></a>Búsqueda de caras similares

Vea [Buscar similar](#Find-Similar).

#### <a name="smile-attribute"></a>Sonrisa (atributo)

La sonrisa es uno de los [atributos](#Attributes) utilizados para describir la expresión de sonrisa de las caras disponibles. El atributo de sonrisa es opcional en los resultados de la detección y se puede controlar con una solicitud de detección de returnFaceAttributes. Si returnFaceAttributes contiene "smile", las caras devueltas contendrán atributos de sonrisa.

Para más detalles, consulte la guía [Face - Detect](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395236) (Cara: detectar).

#### <a name="snapshot"></a>Instantánea

Una instantánea es el almacenamiento remoto temporal de ciertos tipos de datos de Face. Funciona como una especie de Portapapeles para copiar datos de una suscripción a otra. En primer lugar, el usuario "toma" una instantánea de los datos de la suscripción de origen y luego la "aplica" a un objeto de datos nuevo en la suscripción de destino. 

Para obtener más información, consulte [Guía de migración de caras](./face-api-how-to-topics/how-to-migrate-face-data.md), así como la referencia en la documentación (REST) de [Snapshot - Take](https://docs.microsoft.com/rest/api/cognitiveservices/face/snapshot/take) (Instantánea: tomar) y [Snapshot - Apply](https://docs.microsoft.com/rest/api/cognitiveservices/face/snapshot/apply) (Instantánea: aplicar).

#### <a name="status-train"></a>Estado (entrenar)

El estado es una cadena que se utiliza para describir el procedimiento para entrenar LargeFaceList/LargePersonGroups/PersonGroups, incluidos "notstarted", "running", "succeeded", "failed".

Para obtener más información, consulte las guías [LargeFaceList - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a158422d2de3616c086f2d1) (LargeFaceList: entrenar), [LargePersonGroup - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599ae2d16ac60f11b48b5aa4) (LargePersonGroup: entrenar) y [PersonGroup - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395249) (PersonGroup: entrenar).

#### <a name="subscription-key"></a>Subscription key

La clave de suscripción es una cadena que se debe especificar como parámetro de cadena de consulta para invocar cualquier Face API. La clave de suscripción se puede encontrar en la página Mis suscripciones después de iniciar sesión en el portal de Microsoft Cognitive Services. Habrá dos claves asociadas a cada suscripción: una clave principal y una clave secundaria. Ambos se pueden usar para invocar la API de forma idéntica. Debe proteger las claves de suscripción y también puede regenerar las claves de suscripción en cualquier momento desde la página Mis suscripciones.

## <a name="t"></a>T

#### <a name="train-largefacelistlargepersongrouppersongroup"></a>Entrenar (LargeFaceList/LargePersonGroup/PersonGroup)

Esta API se usa para preprocesar [LargeFaceList](#LargeFaceList)/[LargePersonGroup](#LargePersonGroup)/[PersonGroup](#PersonGroup) para asegurar el rendimiento de [Buscar similar](#Find-Similar)/[Identificación](#Identification). Si no se realiza el entrenamiento o el [estado del entrenamiento](#Status-Train) no se muestra como correcto, se producirá un error en la identificación de este PersonGroup.

Para más información, consulte las guías siguientes: [LargeFaceList - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/5a158422d2de3616c086f2d1) (LargeFaceList: entrenar), [LargePersonGroup - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599ae2d16ac60f11b48b5aa4) (LargePersonGroup: entrenar), [PersonGroup - Train](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395249) (PersonGroup: entrenar), [Face - Identify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395239) (Cara: identificar).

## <a name="u"></a>U

#### <a name="userdatauser-data"></a>UserData/datos de usuario

Los datos de usuario son información adicional asociada a la [persona](#Person) y a [PersonGroup](#PersonGroup)/[LargePersonGroup](#LargePersonGroup). Los datos de usuario los establecen los usuarios para que sea más fácil utilizar, comprender y recordar los datos.

Para más información, consulte las guías siguientes: [LargePersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acdee6ac60f11b48b5a9d) (LargePersonGroup: crear), [LargePersonGroup - Update](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599acfc83a7b9412a4d53f3f) (LargePersonGroup: actualizar), [LargePersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599adcba3a7b9412a4d53f40) (Persona LargePersonGroup: crear), [LargePersonGroup Person - Update](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/599ade043a7b9412a4d53f41) (Persona LargePersonGroup: actualizar), [PersonGroup - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395244) (PersonGroup: crear), [PersonGroup - Update](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039524a) (PersonGroup: actualizar), [PersonGroup Person - Create](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523c) (Persona PersonGroup: crear), [PersonGroup Person - Update](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f30395242) (Persona PersonGroup: actualizar).

## <a name="v"></a>V

#### <a name="verification"></a>Comprobación

Esta API se usa para comprobar si dos caras son la misma o no. Ambas caras se representan como las id. de cara en la solicitud. Los resultados comprobados contienen un campo booleano (isIdentical) que indica que son la misma si es true y un campo numérico ([confidence](#Confidence)) que indica el nivel de confianza.

Para más detalles, consulte la guía [Face - Verify](https://westus.dev.cognitive.microsoft.com/docs/services/563879b61984550e40cbbe8d/operations/563879b61984550f3039523a) (Cara: verificar).

## <a name="w"></a>W

## <a name="x"></a>X

## <a name="y"></a>Y

## <a name="z"></a>Z
