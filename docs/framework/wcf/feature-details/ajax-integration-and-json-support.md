---
title: "Интеграция с AJAX и поддержка JSON"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 98efc62a133b86ab71e34671bc6385a5a94897ea
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ajax-integration-and-json-support"></a>Интеграция с AJAX и поддержка JSON
Поддержка [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] формата данных асинхронных сценариев JavaScript и XML (AJAX), а также JavaScript Object Notation (JSON) ASP.NET позволяет клиентам AJAX использовать операции служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Клиенты AJAX представляют собой веб-страницы, на которых выполняется код JavaScript и которые обращаются к этим службам [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью HTTP-запросов. В этом разделе приведены сведения о такой поддержке и способах ее реализации.  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)]ASP.NET AJAX и интеграции с ASP.NET 2.0. в разделе [Общие сведения о ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=96725).  
  
## <a name="in-this-section"></a>Содержание  
 [Создание службы WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 Описывается, как клиенты AJAX могут использовать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], добавляя соответствующую конечную точку AJAX через конфигурацию или с помощью производства узла службы, настроенного на создание узла службы, который предназначен для автоматической настройки конечной точки AJAX.  
  
 [Создание служб WCF AJAX без использования ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 Описывается, как создать службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], не используя ASP.NET.  
  
 [Поддержка JSON и других данных форматов передачи](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX (вместо XML).  
  
 [Как: миграция с поддержкой AJAX веб-служб ASP.NET в WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 Описывается, как перенести веб-службу ASP.NET с поддержкой AJAX в веб-службу [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] .  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [Модель программирования WCF Web HTTP](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
