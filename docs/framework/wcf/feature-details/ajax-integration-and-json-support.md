---
title: "Интеграция с AJAX и поддержка JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "интеграция с AJAX и поддержка JSON [WCF]"
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Интеграция с AJAX и поддержка JSON
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] Поддержка формата данных асинхронных сценариев JavaScript и XML \(AJAX\) и Javascript Object Notation \(JSON\) ASP.NET позволяет клиентам AJAX использовать операции служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Клиенты AJAX представляют собой веб\-страницы, на которых выполняется код Javascript и которые обращаются к этим службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью запросов HTTP.В этом разделе приведены сведения о такой поддержке и способах ее реализации.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] ASP.NET AJAX и интеграции с ASP.NET 2.0 см. в разделе [Общие сведения об ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=96725).  
  
## В этом подразделе  
 [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 Описывается, как клиенты AJAX могут использовать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], добавляя соответствующую конечную точку AJAX через конфигурацию или с помощью производства узла службы, настроенного на создание узла службы, который предназначен для автоматической настройки конечной точки AJAX.  
  
 [Создание служб WCF AJAX без использования ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 Описывается, как создать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], не используя ASP.NET.  
  
 [Поддержка JSON и других форматов передачи данных](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX \(вместо XML\).  
  
 [Практическое руководство. Миграция веб\-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 Описывается, как перенести веб\-службу ASP.NET с поддержкой AJAX в веб\-службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
## См. также  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>   
 [Модель веб\-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)