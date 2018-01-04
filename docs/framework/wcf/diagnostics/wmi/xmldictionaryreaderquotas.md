---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a3afb9b8cfede60c773d146f4d1728d7fe02b75
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="xmldictionaryreaderquotas"></a>XmlDictionaryReaderQuotas
XmlDictionaryReaderQuotas  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс XmlDictionaryReaderQuotas не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс XmlDictionaryReaderQuotas имеет следующие свойства:  
  
### <a name="maxarraylength"></a>MaxArrayLength  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимально допустимая длина массива.  
  
### <a name="maxbytesperread"></a>MaxBytesPerRead  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимально допустимое число байтов, возвращаемых для каждой операции чтения.  
  
### <a name="maxdepth"></a>MaxDepth  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальная глубина вложенного узла для каждого чтения.  
  
### <a name="maxnametablecharcount"></a>MaxNameTableCharCount  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимально допустимое количество символов в имени таблицы.  
  
### <a name="maxstringcontentlength"></a>MaxStringContentLength  
 Тип данных: sint32  
  
 Тип доступа: только для чтения  
  
 Максимальное допустимое число символов в содержимом элемента XML.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
