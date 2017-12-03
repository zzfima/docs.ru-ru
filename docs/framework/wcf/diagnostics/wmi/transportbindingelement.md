---
title: TransportBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54ecfbee-53c0-410c-a7fa-a98f2e40c545
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c2605e1a1f88434a9052059ac3ebdce429d6d6c8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
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
