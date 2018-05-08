---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: 83fa879fbef94e2dc9c142dfb92a51a54a7b60cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="mtommessageencodingbindingelement"></a>MtomMessageEncodingBindingElement
MtomMessageEncodingBindingElement  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс MtomMessageEncodingBindingElement не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс MtomMessageEncodingBindingElement имеет следующие свойства.  
  
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
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
