---
title: MsmqTransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c4cfa3d58127fa560f39ce0dcfe51b97ded6223a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс MsmqTransportBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс MsmqTransportBindingElement имеет следующие свойства.  
  
### <a name="maxpoolsize"></a>MaxPoolSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
