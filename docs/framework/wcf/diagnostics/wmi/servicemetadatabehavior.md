---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: e96a732f8b3b4d78d597429905cc7dd290dcc606
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="servicemetadatabehavior"></a>ServiceMetadataBehavior
ServiceMetadataBehavior  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
 Тип доступа: только для чтения  
  
 Задает расположение, в которое служба перенаправляет запросы метаданных.  
  
### <a name="httpgetenabled"></a>HttpGetEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой код WSDL по адресу, определяемому атрибутом `HttpGetUrl`.  
  
### <a name="httpgeturl"></a>HttpGetUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTP.  
  
### <a name="httpsgetenabled"></a>HttpsGetEnabled  
 Тип данных: boolean  
  
 Тип доступа: только для чтения  
  
 Определяет, публикует ли служба свой язык WSDL через HTTPS по адресу, указанному в атрибуте `HttpsGetUrl`.  
  
### <a name="httpsgeturl"></a>HttpsGetUrl  
 Тип данных: string  
  
 Тип доступа: только для чтения  
  
 Задает расположение для публикации языка WSDL службы и его получения с помощью HTTPS.  
  
## <a name="requirements"></a>Требования  
  
|MOF|Объявлено в файле Servicemodel.mof.|  
|---------|-----------------------------------|  
|Пространство имен|Определено в root\ServiceModel.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
