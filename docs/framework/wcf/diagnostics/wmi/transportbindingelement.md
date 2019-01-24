---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: 303e5523befb68c65bc50ee3933af58897929363
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54668461"
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class TransportBindingElement : BindingElement  
{  
  boolean ManualAddressing;  
  sint64 MaxBufferPoolSize;  
  sint64 MaxReceivedMessageSize;  
  string Scheme;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс TransportBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс TransportBindingElement имеет следующие свойства.  
  
### <a name="manualaddressing"></a>ManualAddressing  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Логическое значение, указывающее, требуется ли пользователю контролировать адресацию сообщений.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Тип данных: sint64  
  
 Тип доступа: Только чтение  
  
 Максимальный размер буферного пула для этой привязки.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Тип данных: sint64  
  
 Тип доступа: Только чтение  
  
 Максимально размер сообщения, обрабатываемого данной привязкой.  
  
### <a name="scheme"></a>Схема  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Схема универсального кода ресурса (URI) для транспорта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.TransportBindingElement>
