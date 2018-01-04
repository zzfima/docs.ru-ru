---
title: 1008 - WorkflowApplicationUnloaded
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a605b780-4a7e-43ab-92e7-0a3b01d053b0
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26491c1e2b20f4285aaedbcd12947cad3562f041
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="1008---workflowapplicationunloaded"></a>1008 - WorkflowApplicationUnloaded
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1008|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что приложение рабочего процесса выгружено.  
  
## <a name="message"></a>Сообщение  
 Элемент WorkflowInstance с идентификатором «%1» выгружен из памяти.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
