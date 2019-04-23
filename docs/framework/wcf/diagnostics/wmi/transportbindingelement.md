---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: bdb5ca7400a41dd724c2ad7fc76695a82874ded6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2019
ms.locfileid: "59974179"
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
