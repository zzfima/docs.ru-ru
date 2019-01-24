---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: 330496d5f0f80affcb6bc44a1f66f4321a635f00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580594"
---
# <a name="binarymessageencodingbindingelement"></a>BinaryMessageEncodingBindingElement
BinaryMessageEncodingBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp  
class BinaryMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  sint32 MaxReadPoolSize;  
  sint32 MaxSessionSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс BinaryMessageEncodingBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс BinaryMessageEncodingBindingElement имеет следующие свойства.  
  
## <a name="maxreadpoolsize"></a>MaxReadPoolSize  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Целое число, определяющее количество сообщений, которые можно читать одновременно, не выделяя памяти для новых средств чтения.  
  
## <a name="maxsessionsize"></a>MaxSessionSize  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Значение, указывающее максимальный размер буфера, используемого для кодирования (в байтах).  
  
## <a name="maxwritepoolsize"></a>MaxWritePoolSize  
 Тип данных: sint32  
  
 Тип доступа: Только чтение  
  
 Целое число, обозначающее количество сообщений, которые можно отправлять одновременно, не выделяя памяти для новых средств записи.  
  
## <a name="readerquotas"></a>ReaderQuotas  
 Тип данных: XmlDictionaryReaderQuotas  
  
 Тип доступа: Только чтение  
  
 Квоты средств чтения.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>
