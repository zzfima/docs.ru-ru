---
title: "&lt;wsdlImporter&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 986b2165-8430-4dba-b1b8-00396841bb96
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# &lt;wsdlImporter&gt;
Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS\-Policy.  
  
## Синтаксис  
  
```  
  
<metadata>  
      <wsdlImporters>  
      <wsdlImporter type="string" />  
   </wsdlImporters>  
</metadata>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`type`|Тип этого элемента.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<wsdlImporters\>](../../../../../docs/framework/configure-apps/file-schema/wcf/wsdlimporters.md)|Задает все средства импорта WSDL, импортирующие метаданные на языке WSDL 1.1 с вложениями WS\-Policy.|  
  
## Заметки  
 Средство импорта WSDL используется для импорта метаданных, а также для их преобразования в различные классы, представляющие данные контракта и конечной точки.  Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.  Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким\-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.WsdlImporterElement>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>   
 <xref:System.ServiceModel.Description.MetadataImporter>   
 <xref:System.ServiceModel.Description.WsdlImporter>   
 [Конфигурация клиента WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Клиенты](../../../../../docs/framework/wcf/feature-details/clients.md)