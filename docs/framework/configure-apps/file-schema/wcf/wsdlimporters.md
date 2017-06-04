---
title: "&lt;wsdlImporters&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 270c7f93-eab7-47b6-8b94-ac3f5b7f17e4
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# &lt;wsdlImporters&gt;
Этот элемент конфигурации указывает всех импортеров WSDL, импортирующих метаданные на языке WSDL 1.1 с вложениями WS\-Policy.  Каждый дочерний элемент — это элемент \<`wsdlImporter`\>, который указывает способ импорта метаданных, а также способ преобразования сведений в различные классы, представляющие сведения контракта и конечной точки.  Он может выборочно импортировать сведения контракта и конечной точки, а также свойства, предоставляющие сведения об ошибках и принимающие сведения о типах, относящиеся к процессу импорта и преобразования.  Оно также поддерживает импорт данных привязки и свойств, предоставляющих доступ к каким\-либо документам политики, документам WSDL, расширениям WSDL и документам схемы XML.  
  
## См. также  
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 <xref:System.ServiceModel.Configuration.WsdlImporterElementCollection>   
 <xref:System.ServiceModel.Description.MetadataImporter>   
 <xref:System.ServiceModel.Description.WsdlImporter>   
 [Конфигурация клиента WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Клиенты](../../../../../docs/framework/wcf/feature-details/clients.md)