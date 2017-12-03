---
title: "1004 ― WorkflowInstanceAborted"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: edb9ab8c-0b9a-488d-aa96-9c8c7984b53c
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 564e94d94dc5e3579dc4a80d734db78e90db91fb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1004---workflowinstanceaborted"></a>1004 ― WorkflowInstanceAborted
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1004|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что экземпляр рабочего процесса был прерван с исключением.  
  
## <a name="message"></a>Сообщение  
 Выполнение элемента WorkflowInstance с идентификатором «%1» было прервано в результате исключения.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|Исключение|`xs:string`|Сведения об исключении|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
