---
title: 1102 - WorkflowActivityStop
ms.date: 03/30/2017
ms.assetid: 285e5cb8-e90d-4914-ac06-e9b176ffefa2
ms.openlocfilehash: 44617e9f53be0e601424746f83b171d33956197e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511492"
---
# <a name="1102---workflowactivitystop"></a>1102 - WorkflowActivityStop
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1102|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что действия рабочего процесса остановлены.  
  
## <a name="message"></a>Сообщение  
 Элемент WorkflowInstance с идентификатором «%1», действие E2E  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|xs:string|Идентификатор экземпляра рабочего процесса.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
