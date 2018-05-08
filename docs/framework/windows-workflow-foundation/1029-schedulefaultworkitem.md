---
title: 1029 - ScheduleFaultWorkItem
ms.date: 03/30/2017
ms.assetid: 3a56b29e-f740-459d-8576-d81e58bf5a03
ms.openlocfilehash: f5beab91f7dd39a3f8ed3b76d6c0a1ddd9bd77c3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="1029---schedulefaultworkitem"></a>1029 - ScheduleFaultWorkItem
## <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|Идентификатор|1029|  
|Ключевые слова|WFRuntime|  
|Уровень|Verbose|  
|Канал|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Описание  
 Указывает, что FaultWorkItem было предназначено.  
  
## <a name="message"></a>Сообщение  
 FaultWorkItem был запланирован для действия «%1», DisplayName: «%2», InstanceId: «%3».  Исключение распространено из действия «%4», DisplayName «%5», InstanceId «%6».  
  
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
