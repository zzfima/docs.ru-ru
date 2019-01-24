---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 76e28b18cd595a4a18f573dfe9539b646196c944
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720346"
---
# <a name="servicemetadatabehavior"></a>ServiceMetadataBehavior
ServiceMetadataBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a>Методы  
 Класс ServiceMetadataBehavior не определяет никаких методов.  
  
## <a name="properties"></a>Свойства  
 Класс ServiceMetadataBehavior имеет следующие свойства.  
  
### <a name="externalmetadatalocation"></a>ExternalMetadataLocation  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Задает расположение, в которое служба перенаправляет запросы метаданных.  
  
### <a name="httpgetenabled"></a>HttpGetEnabled  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.  
  
### <a name="httpgeturl"></a>HttpGetUrl  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.  
  
### <a name="httpsgetenabled"></a>HttpsGetEnabled  
 Тип данных: boolean  
  
 Тип доступа: Только чтение  
  
 Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.  
  
### <a name="httpsgeturl"></a>HttpsGetUrl  
 Тип данных: string  
  
 Тип доступа: Только чтение  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также
- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
