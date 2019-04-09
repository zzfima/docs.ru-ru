---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160333"
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
