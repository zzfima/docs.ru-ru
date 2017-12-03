---
title: ServiceDebugBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5c829f68fe994b47fe880febb4d3ac2020fde2d1
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior
ServiceDebugBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceDebugBehavior не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceDebugBehavior имеет следующие свойства.  
  
### <a name="httphelppageenabled"></a>HttpHelpPageEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
