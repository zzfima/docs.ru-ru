---
title: 3502 - InferredOperationDescription
ms.date: 03/30/2017
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
ms.openlocfilehash: 752cd73066c3c15ecbb36c40c417ee84b3fcf184
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33512009"
---
# <a name="3502---inferredoperationdescription"></a>3502 - InferredOperationDescription
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|3502|  
|Ключевые слова|WFServices|  
|Уровень|Сведения|  
|Канал|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Описание  
 Указывает, что описание операции OperationDescription выведено из WorkflowService.  
  
## <a name="message"></a>Сообщение  
 Описание OperationDescription с параметром Name=«%1» в контракте «%2» было выведено из WorkflowService. IsOneWay=%3.  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|OperationName|xs:string|Имя операции.|  
|ContractName|xs:string|Имя контракта.|  
|IsOneWay|xs:string|Логическое значение True или False, указывающее, является ли контракт односторонним.|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
