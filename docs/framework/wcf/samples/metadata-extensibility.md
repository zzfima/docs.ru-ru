---
title: "Расширяемость метаданных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f92fcc76-0806-4c84-9d63-7aae0d3899de
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: abdc2a1cca721450a780f81ff8795fc4e648453f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="metadata-extensibility"></a>Расширяемость метаданных
В этом разделе содержатся образцы, демонстрирующие пользовательские метаданные.  
  
## <a name="in-this-section"></a>Содержание  
 [Пользовательские защищенной конечной точки метаданных](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)  
 Демонстрирует реализацию службы, конечную точку метаданных, безопасности, использующий одну из привязок, не принадлежащий метаданным exchange и настройте [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) или клиенты для извлечения метаданных из такой конечной точки метаданных.  
  
 [Пользовательская публикация WSDL](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)  
 Показывает, как среди прочих функциональных возможностей реализовать <xref:System.ServiceModel.Description.IWsdlExportExtension?displayProperty=nameWithType> пользовательского атрибута <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> для экспорта свойств атрибута в виде заметок WSDL.
