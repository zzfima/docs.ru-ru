---
title: 39460 - TrackingValueNotSerializable
ms.date: 03/30/2017
ms.assetid: 476a29ad-24d8-4359-8c17-d4e20c1e1c15
ms.openlocfilehash: e0e5515563ba77426a5f45d92977014c456ab779
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774391"
---
# <a name="39460---trackingvaluenotserializable"></a>39460 - TrackingValueNotSerializable
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|39460|  
|Ключевые слова|WFTracking|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что извлеченные переменная или аргумент в записи отслеживания не сериализуются.  
  
## <a name="message"></a>Сообщение  
 Извлеченный аргумент или переменная «%1» не сериализуется.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|name|xs:string|Имя элемента.|  
|Домен приложения|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
