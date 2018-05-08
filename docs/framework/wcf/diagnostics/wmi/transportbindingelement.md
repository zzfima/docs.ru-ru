---
title: TransportBindingElement
ms.date: 03/30/2017
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
ms.openlocfilehash: dc7a29e5911a9d0a774e36f5be8c1f3cacad69b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="transportbindingelement"></a>TransportBindingElement
TransportBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
 Тип доступа: только для чтения  
  
 Логическое значение, указывающее, требуется ли пользователю контролировать адресацию сообщений.  
  
### <a name="maxbufferpoolsize"></a>MaxBufferPoolSize  
 Тип данных: sint64  
  
 Тип доступа: только для чтения  
  
 Максимальный размер буферного пула для этой привязки.  
  
### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize  
 Тип данных: sint64  
  
 Тип доступа: только для чтения  
  
 Максимально размер сообщения, обрабатываемого данной привязкой.  
  
### <a name="scheme"></a>Схема  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Схема универсального кода ресурса (URI) для транспорта.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.TransportBindingElement>
