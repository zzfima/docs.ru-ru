---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 2e38eb2c2d42ffc5436562b254a42215ccabbab2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090918"
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
