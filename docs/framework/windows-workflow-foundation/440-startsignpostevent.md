---
title: 440 - StartSignpostEvent1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2b7772bcd8d637b14e3f91feceaccc9f045f390c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="440---startsignpostevent1"></a>440 - StartSignpostEvent1
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|440|  
|Ключевые слова|Устранение неполадок|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 В трассировке действий указывает на то, что сообщение начало пересекать границу действия при отправке или приеме.  
  
## <a name="message"></a>Сообщение  
 Граница действия.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|ExtendedData|`xs:string`|Имя действия.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
