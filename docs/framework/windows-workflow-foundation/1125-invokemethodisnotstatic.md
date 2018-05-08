---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 692c5e56dac0a69ab5705acd284f048391145641
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1125---invokemethodisnotstatic"></a>1125 - InvokeMethodIsNotStatic
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1125|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 На шаге CacheMetadata действие InvokeMethod означает, что вызываемый метод - не статический.  
  
## <a name="message"></a>Сообщение  
 Метод InvokeMethod «%1»: метод не является статическим.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|InvokeMethod|xs:string|Отображаемое имя действия InvokeMethod.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
