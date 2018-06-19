---
title: 1030 - StartFaultWorkItem
ms.date: 03/30/2017
ms.assetid: e1601fb9-0bc6-4dbe-816f-f24914063d34
ms.openlocfilehash: 3848d644e77041a62a52eb2eae5eeef286dfe334
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509684"
---
# <a name="1030---startfaultworkitem"></a>1030 - StartFaultWorkItem
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1030|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает на начало выполнения FaultWorkItem.  
  
## <a name="message"></a>Сообщение  
 Начинается выполнение элемента FaultWorkItem для действия «%1», DisplayName: «%2», InstanceId: «%3».  Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».  
  
## <a name="details"></a>Подробные сведения  
  
|Имя элемента данных|Тип элемента данных|Описание|  
|--------------------|--------------------|-----------------|  
|FaultActivity|xs:string|Имя типа действия с ошибкой.|  
|FaultActivityDisplayName|xs:string|Отображаемое имя действия с ошибкой.|  
|FaultActivityInstanceId|xs:string|Идентификатор экземпляра действия с ошибкой.|  
|ExceptionActivity|xs:string|Имя типа действия, вызвавшего исключение.|  
|ExceptionActivityDisplayName|xs:string|Отображаемое имя действия, вызвавшего исключение.|  
|ExceptionActivityInstanceId|xs:string|Идентификатор экземпляра действия, вызвавшего исключение.|  
|Исключение|xs:string|Сведения об исключении|  
|AppDomain|xs:string|Строка, возвращаемая AppDomain.CurrentDomain.FriendlyName.|
