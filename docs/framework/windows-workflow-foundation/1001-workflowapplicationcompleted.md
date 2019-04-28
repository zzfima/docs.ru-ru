---
title: 1001 - WorkflowApplicationCompleted
ms.date: 03/30/2017
ms.assetid: 7a2ab59a-cf66-437a-b01e-f8f7268a3f7a
ms.openlocfilehash: 430174b96a499fff7e0156327bb15e066ce2ca36
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008646"
---
# <a name="1001---workflowapplicationcompleted"></a>1001 - WorkflowApplicationCompleted
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|ID|1001|  
|Ключевые слова|WFRuntime|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что приложение рабочего процесса завершено в состоянии Closed.  
  
## <a name="message"></a>Сообщение  
 Элемент WorkflowInstance с идентификатором «%1» завершил работу в состоянии Closed.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|WorkflowInstanceId|`xs:string`|Идентификатор экземпляра для рабочего процесса.|  
|Домен приложения|`xs:string`|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
