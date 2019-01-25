---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: a0e2ac250da3837b41134d3a04a21579a2fe923a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569041"
---
# <a name="msmqbindingelementbase"></a>MsmqBindingElementBase
MsmqBindingElementBase  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс MsmqBindingElementBase не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс MsmqBindingElementBase имеет следующие свойства.  
  
### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Универсальный код ресурса (URI), содержащий местоположение очереди недоставленных сообщений для каждого приложения; в эту очередь помещаются просроченные сообщения или сообщения, которые не удалось передать или доставить.  
  
### <a name="deadletterqueue"></a>DeadLetterQueue  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Значение перечисления, указывающее тип используемой очереди недоставленных сообщений.  
  
### <a name="durable"></a>Durable  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее, являются ли сообщения, обрабатываемые этой привязкой, устойчивыми или неустойчивыми.  
  
### <a name="exactlyonce"></a>ExactlyOnce  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, указывающее, доставляются ли сообщения, обрабатываемые этой привязкой, только один раз.  
  
### <a name="maxretrycycles"></a>MaxRetryCycles  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное количество циклов повторных попыток доставить сообщение принимающему приложению.  
  
### <a name="receiveerrorhandling"></a>ReceiveErrorHandling  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Параметры обработки подозрительных сообщений.  
  
### <a name="receiveretrycount"></a>ReceiveRetryCount  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Максимальное количество немедленных повторных попыток считывания сообщения из очереди приложения.  
  
### <a name="retrycycledelay"></a>RetryCycleDelay  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее временную задержку между циклами повторных попыток доставить сообщение, которое не удалось доставить немедленно.  
  
### <a name="timetolive"></a>TimeToLive  
 Тип данных: datetime  
  
 Тип доступа: Только чтение  
  
 Промежуток времени, соответствующий максимальному сроку нахождения в очереди сообщений, обрабатываемых этой привязкой.  
  
### <a name="usemsmqtracing"></a>UseMsmqTracing  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, указывающее, следует ли трассировать сообщения, обрабатываемые этой привязкой.  
  
### <a name="usesourcejournal"></a>UseSourceJournal  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, указывающее, должны ли сохраняться в очереди журнала источника копии сообщений, обрабатываемых этой привязкой.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
