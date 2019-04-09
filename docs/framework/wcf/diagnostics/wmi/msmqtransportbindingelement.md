---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 706cec5c414197ebabda7939728b95be32582e0f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197936"
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
  
 Тип доступа: Только чтение  
  
 Максимальный размер пула, содержащего внутренние объекты сообщений MSMQ.  
  
### <a name="queuetransferprotocol"></a>QueueTransferProtocol  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Значение перечисления, в котором указывается поставленный в очередь транспорт канала связи, используемый данной привязкой.  
  
### <a name="useactivedirectory"></a>UseActiveDirectory  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Возвращает логическое значение, указывающее, следует ли преобразовывать адреса очередей с помощью Active Directory.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
