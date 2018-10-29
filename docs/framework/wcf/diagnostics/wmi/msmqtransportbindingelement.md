---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 33cd9c427ed5ad04eaf9e9889f60f091f335d1e7
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198111"
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
