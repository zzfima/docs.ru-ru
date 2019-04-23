---
title: BinaryMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: e2bb3cdd-3bbd-4bb5-85fe-570457500a66
ms.openlocfilehash: e0551e7b4b05151490625912742aa6b26ef0216e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59768063"
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
