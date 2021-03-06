---
title: 'Aptitud de Cognitive Search para la detección de idiomas: Azure Search'
description: Evalúa el texto no estructurado y, en cada registro, devuelve un identificador de idioma con una puntuación que indica la solidez del análisis en una canalización de enriquecimiento de Azure Search.
services: search
manager: pablocas
author: luiscabrer
ms.service: search
ms.devlang: NA
ms.workload: search
ms.topic: conceptual
ms.date: 01/17/2019
ms.author: luisca
ms.custom: seodec2018
ms.openlocfilehash: 088a147bbcf4f94209ce9faf62e14833a818408c
ms.sourcegitcommit: 82cdc26615829df3c57ee230d99eecfa1c4ba459
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "54411313"
---
#   <a name="language-detection-cognitive-skill"></a>Aptitud cognitiva para la detección de idiomas

La aptitud para la**detección de idiomas** no solo ofrece la posibilidad de usar hasta 120 idiomas, además, detecta el idioma del texto de entrada y usa un código de idioma único para informar acerca de cada documento enviado en la solicitud. El código de idioma se empareja con una puntuación que indica la intensidad del análisis. Esta aptitud utiliza los modelos de aprendizaje automático proporcionados por [Text Analytics](https://docs.microsoft.com/azure/cognitive-services/text-analytics/overview) en Cognitive Services.

Esta funcionalidad es especialmente útil cuando necesita proporcionar el idioma del texto como entrada para otras aptitudes (por ejemplo, la [aptitud de análisis de opiniones](cognitive-search-skill-sentiment.md) o la [aptitud de división de texto](cognitive-search-skill-textsplit.md)).

> [!NOTE]
> A partir del 21 de diciembre de 2018, podrá [asociar un recurso de Cognitive Services](cognitive-search-attach-cognitive-services.md) con un conjunto de aptitudes de Azure Search. Esto nos permite empezar a cobrar por la ejecución del conjunto de aptitudes. En esta fecha, también empezamos a cobrar por la extracción de imágenes como parte de la fase de descifrado de documentos. La extracción de texto de documentos continuará ofreciéndose sin costo adicional.
>
> La ejecución de [aptitudes cognitivas integradas](cognitive-search-predefined-skills.md) se cobra al [precio de pago por uso de Cognitive Services](https://azure.microsoft.com/pricing/details/cognitive-services), con la misma tarifa que tendría si hubiese realizado la tarea directamente. La extracción de imágenes es un cargo de Azure Search que actualmente se ofrece al precio de la versión preliminar. Para obtener más información, consulte la [página de precios de Azure Search](https://go.microsoft.com/fwlink/?linkid=2042400) o [cómo funciona la facturación](search-sku-tier.md#how-billing-works).

## <a name="odatatype"></a>@odata.type  
Microsoft.Skills.Text.LanguageDetectionSkill

## <a name="data-limits"></a>Límites de datos
El tamaño máximo de un registro debe tener 50 000 caracteres según lo que mida `String.Length`. Si tiene que dividir los datos antes de enviarlos al analizador de opiniones, puede usar la [aptitud de división de texto](cognitive-search-skill-textsplit.md).

## <a name="skill-inputs"></a>Entradas de aptitudes

Los parámetros distinguen mayúsculas de minúsculas.

| Entradas     | DESCRIPCIÓN |
|--------------------|-------------|
| text | Texto que se va a analizar.|

## <a name="skill-outputs"></a>Salidas de aptitudes

| Nombre de salida    | DESCRIPCIÓN |
|--------------------|-------------|
| languageCode | El código de idioma ISO 6391 para el idioma identificado. Por ejemplo, "en". |
| languageName | El nombre del idioma. Por ejemplo, "inglés". |
| de la aplicación | Un valor entre 0 y 1. La probabilidad de que el lenguaje esté correctamente identificado. La puntuación puede ser inferior a 1 si la oración tiene distintos idiomas.  |

##  <a name="sample-definition"></a>Definición de ejemplo

```json
 {
    "@odata.type": "#Microsoft.Skills.Text.LanguageDetectionSkill",
    "inputs": [
      {
        "name": "text",
        "source": "/document/text"
      }
    ],
    "outputs": [
      {
        "name": "languageCode",
        "targetName": "myLanguageCode"
      },
      {
        "name": "languageName",
        "targetName": "myLanguageName"
      },
      {
        "name": "score",
        "targetName": "myLanguageScore"
      }

    ]
  }
```

##  <a name="sample-input"></a>Entrada de ejemplo

```json
{
    "values": [
      {
        "recordId": "1",
        "data":
           {
             "text": "Glaciers are huge rivers of ice that ooze their way over land, powered by gravity and their own sheer weight. "
           }
      },
      {
        "recordId": "2",
        "data":
           {
             "text": "Estamos muy felices de estar con ustedes."
           }
      }
    ]
```


##  <a name="sample-output"></a>Salida de ejemplo

```json
{
    "values": [
      {
        "recordId": "1",
        "data":
            {
              "languageCode": "en",
              "languageName": "English",
              "score": 1,
            }
      },
      {
        "recordId": "2",
        "data":
            {
              "languageCode": "es",
              "languageName": "Spanish",
              "score": 1,
            }
      }
    ]
}
```


## <a name="error-cases"></a>Casos de error
Si el texto está escrito en un idioma no compatible, se genera un error y no se devuelve ningún identificador de idioma.

## <a name="see-also"></a>Otras referencias

+ [Aptitudes predefinidas](cognitive-search-predefined-skills.md)
+ [Definición de un conjunto de aptitudes](cognitive-search-defining-skillset.md)
