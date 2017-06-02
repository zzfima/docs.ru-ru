---
title: "Форматы метаданных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: baad1e68-28fc-4a6a-8a43-75e47e7fa871
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# Форматы метаданных
В следующей таблице перечислены форматы метаданных, поддерживаемые [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## Спецификации и использование метаданных  
  
|Протокол|Спецификация и использование|  
|--------------|----------------------------------|  
|WSDL 1.1|[Язык описания веб\-служб \(WSDL\) 1.1](http://go.microsoft.com/fwlink/?LinkId=94859)<br /><br /> В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] язык WSDL используется для описания служб.|  
|схема XML|[XML Schema Part 2: Datatypes Second Edition](http://go.microsoft.com/fwlink/?LinkId=94861) и [XML Schema Part 1: Structures Second Edition](http://go.microsoft.com/fwlink/?LinkId=94862)<br /><br /> В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] схема XML используется для описания типов данных, используемых в сообщениях.|  
|WS Policy|[Политика веб\-служб 1.2 — платформа \(WS\-Policy\)](http://go.microsoft.com/fwlink/?LinkId=94864)<br /><br /> [Политика веб\-служб 1.5 — платформа](http://go.microsoft.com/fwlink/?LinkId=94865)<br /><br /> В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] спецификации WS\-Policy 1.2 или 1.5 используются вместе с доменными утверждениями для описания требований и возможностей служб.|  
|Вложения WS Policy|[Политика веб\-служб 1.2 — Вложение \(WS\-PolicyAttachment\)](http://go.microsoft.com/fwlink/?LinkId=94866)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификацию вложений WS\-Policy для прикрепления выражений политики в различных областях на языке WSDL.|  
|WS Metadata Exchange|[Обмен метаданными веб\-служб \(WS\-MetadataExchange\) версия 1.1](http://go.microsoft.com/fwlink/?LinkId=94868)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификацию WS\-MetadataExchange для извлечения схемы XML, языка WSDL и спецификации WS\-Policy.|  
|Привязка WS Addressing для WSDL|[Адресация веб\-служб \(WSDL\) 1.0 — привязка WSDL](http://go.microsoft.com/fwlink/?LinkId=94869)<br /><br /> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализует спецификацию привязки WS\-Addressing для WSDL для вложения сведений об адресации в WSDL.|  
  
## См. также  
 [Протоколы веб\-служб, поддерживаемые предоставляемыми системой привязками](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)   
 [WSDL и политика](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)