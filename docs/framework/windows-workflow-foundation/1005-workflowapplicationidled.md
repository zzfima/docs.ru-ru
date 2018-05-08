---
title: 1005 - WorkflowApplicationIdled
ms.date: 03/30/2017
ms.assetid: 74d77dfa-f20d-4fe9-a6ae-e6d1b5fe4182
ms.openlocfilehash: 6bbd12e8025b6a127dbfec8e5d3690825c188c4d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1005---workflowapplicationidled"></a>1005 - WorkflowApplicationIdled
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1005|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что приложение рабочего процесса простаивало.  
  
## <a name="message"></a>Сообщение  
 WorkflowApplication с идентификатором «%1» перешло в состояние простоя.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор приложения рабочего процесса|  
|AppDomain|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
