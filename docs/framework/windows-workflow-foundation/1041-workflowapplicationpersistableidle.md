---
title: 1041 - WorkflowApplicationPersistableIdle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 966adf2f-e21d-44df-a3ec-a8e285e0a316
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea6b31a83df6e15fe34f9e4be31a4eb53bc5bb51
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1041---workflowapplicationpersistableidle"></a>1041 - WorkflowApplicationPersistableIdle
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1041|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что приложение рабочего процесса бездействует и является сохраняемым. Приложение рабочего процесса будет бездействующим или сохраняемым.  
  
## <a name="message"></a>Сообщение  
 WorkflowApplication с идентификатором: «%1» бездействует и является сохраняемым.  Будут выполнены следующие действия: %2.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowApplicationId|xs:string|Идентификатор приложения рабочего процесса|  
|ActionTaken|xs:string|Действие, которое будет выполняться в приложении рабочего процесса.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
