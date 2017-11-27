---
title: 3502 - InferredOperationDescription
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6aebb614-3c72-4537-ba11-3cc7200ef1f1
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 044d67bc2b721451ade04947484899266d288d8c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
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
