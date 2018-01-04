---
title: MsmqBindingElementBase
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10e476931ef07ec694dff200e64ce2ded74c8dfb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="msmqbindingelementbase"></a>MsmqBindingElementBase
MsmqBindingElementBase  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
 Тип доступа: только для чтения  
  
 Универсальный код ресурса (URI), содержащий местоположение очереди недоставленных сообщений для каждого приложения; в эту очередь помещаются просроченные сообщения или сообщения, которые не удалось передать или доставить.  
  
### <a name="deadletterqueue"></a>DeadLetterQueue  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение перечисления, указывающее тип используемой очереди недоставленных сообщений.  
  
### <a name="durable"></a>Durable  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее, являются ли сообщения, обрабатываемые этой привязкой, устойчивыми или неустойчивыми.  
  
### <a name="exactlyonce"></a>ExactlyOnce  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, доставляются ли сообщения, обрабатываемые этой привязкой, только один раз.  
  
### <a name="maxretrycycles"></a>MaxRetryCycles  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество циклов повторных попыток доставить сообщение принимающему приложению.  
  
### <a name="receiveerrorhandling"></a>ReceiveErrorHandling  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Параметры обработки подозрительных сообщений.  
  
### <a name="receiveretrycount"></a>ReceiveRetryCount  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное количество немедленных повторных попыток считывания сообщения из очереди приложения.  
  
### <a name="retrycycledelay"></a>RetryCycleDelay  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Значение, указывающее временную задержку между циклами повторных попыток доставить сообщение, которое не удалось доставить немедленно.  
  
### <a name="timetolive"></a>TimeToLive  
 Тип данных: datetime  
  
 Тип доступа: только для чтения  
  
 Промежуток времени, соответствующий максимальному сроку нахождения в очереди сообщений, обрабатываемых этой привязкой.  
  
### <a name="usemsmqtracing"></a>UseMsmqTracing  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, следует ли трассировать сообщения, обрабатываемые этой привязкой.  
  
### <a name="usesourcejournal"></a>UseSourceJournal  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, должны ли сохраняться в очереди журнала источника копии сообщений, обрабатываемых этой привязкой.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.NetMsmqBinding>  
 <xref:System.ServiceModel.MsmqBindingBase>
