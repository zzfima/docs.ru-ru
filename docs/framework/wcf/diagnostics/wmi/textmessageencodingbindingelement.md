---
title: TextMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 966f1ae06f5d7e0dacb8b7d450463c75f783ef1f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="textmessageencodingbindingelement"></a>TextMessageEncodingBindingElement
TextMessageEncodingBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс TextMessageEncodingBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс TextMessageEncodingBindingElement имеет следующие свойства.  
  
### <a name="encoding"></a>кодировка  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Кодировка, используемая при отправке сообщений через привязку.  
  
### <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.  
  
### <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.  
  
### <a name="readerquotas"></a>ReaderQuotas  
 Тип данных: XmlDictionaryReaderQuotas  
  
 Тип доступа: только для чтения  
  
 Квоты средств чтения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
