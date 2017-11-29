---
title: 1104 - WorkflowActivityResume
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7fe95d1e-34bd-43ca-b92e-587d2d248fff
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8ffba47fa7cd865b604704a3819cbe89be1ed5cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="1104---workflowactivityresume"></a>1104 - WorkflowActivityResume
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1104|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что действие рабочего процесса возобновлено.  
  
## <a name="message"></a>Сообщение  
 Элемент WorkflowInstance с идентификатором «%1», действие E2E  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Идентификатор экземпляра рабочего процесса.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
