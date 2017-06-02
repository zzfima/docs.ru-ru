---
title: "Расширяемость метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Расширяемость метаданных
В этом разделе содержатся образцы, демонстрирующие пользовательские метаданные.  
  
## В этом подразделе  
 [Пользовательская конечная точка защищенных метаданных](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 Показывает, как реализовать службу с защищенной конечной точкой метаданных, которая использует одну из привязок, не предназначенную для обмена метаданными, и как настроить средство [Служебное средство ServiceModel Metadata Utility Tool \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) или клиентов для извлечения метаданных из такой конечной точки метаданных.  
  
 [Пользовательская публикация WSDL](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)  
 Показывает, как среди прочих функциональных возможностей реализовать <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=fullName> пользовательского атрибута <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> для экспорта свойств атрибута в виде заметок WSDL.