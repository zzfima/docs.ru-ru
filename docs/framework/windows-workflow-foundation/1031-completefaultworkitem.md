---
title: 1031 - CompleteFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 95f4ccb0-6be4-41f3-9330-fae43165828f
ms.openlocfilehash: cdcbe516fc8ba7440b3d109a5e5cadc105ecee9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1031---completefaultworkitem"></a>1031 - CompleteFaultWorkItem
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1031|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что FaultWorkItem завершено.  
  
## <a name="message"></a>Сообщение  
 FaultWorkItem завершено для действия «%1», DisplayName «%2», InstanceId «%3». Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».  
  
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
