---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: d6f0e4741aa10bff450a29cfd7a9e63e226c6495
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498886"
---
# <a name="servicedebugbehavior"></a>ServiceDebugBehavior
ServiceDebugBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
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
  
 Тип доступа: Только чтение  
  
 Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.  
  
### <a name="httphelppageurl"></a>HttpHelpPageUrl  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.  
  
### <a name="httpshelppageenabled"></a>HttpsHelpPageEnabled  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.  
  
### <a name="httpshelppageurl"></a>HttpsHelpPageUrl  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.  
  
### <a name="includeexceptiondetailinfaults"></a>IncludeExceptionDetailInFaults  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Указывает, включать ли информацию об управляемых исключениях в сведения об ошибках SOAP, возвращаемые клиентам для отладки.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Description.ServiceDebugBehavior>
