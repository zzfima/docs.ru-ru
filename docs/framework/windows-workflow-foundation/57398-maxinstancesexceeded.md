---
title: 57398 - MaxInstancesExceeded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f943d209-dfeb-43e5-b572-c9a06217936e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 803616fdd287491afa27d3ac23dfce99c5db08ca
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="57398---maxinstancesexceeded"></a>57398 - MaxInstancesExceeded
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|57398|  
|Ключевые слова|WFServices|  
|Уровень|Предупреждение|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Указывает, что система достигла предела, заданного для ограничителя MaxConcurrentInstances.  
  
## <a name="message"></a>Сообщение  
 Система достигла предела, заданного для ограничителя «MaxConcurrentInstances». Для этого ограничителя был задан предел %1. Значение ограничителя можно изменить, изменив атрибут maxConcurrentInstances в элементе serviceThrottle или свойство MaxConcurrentInstances для поведения ServiceThrottlingBehavior.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|Имя|xs:string|Имя элемента.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
