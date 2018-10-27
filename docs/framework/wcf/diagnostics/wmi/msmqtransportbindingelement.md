---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 33cd9c427ed5ad04eaf9e9889f60f091f335d1e7
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50045992"
---
# <a name="msmqtransportbindingelement"></a>MsmqTransportBindingElement
MsmqTransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
