---
title: 1101 - WorkflowActivityStart
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 831cd386-b9b5-47a9-9690-aff6292ff348
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bd7cbf98cb51005fbae5b56a0136e0bb3efe08be
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="1101---workflowactivitystart"></a>1101 - WorkflowActivityStart
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1101|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что началось действие рабочего процесса.  
  
## <a name="message"></a>Сообщение  
 Элемент WorkflowInstance с идентификатором «%1», действие E2E  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Идентификатор экземпляра рабочего процесса.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
