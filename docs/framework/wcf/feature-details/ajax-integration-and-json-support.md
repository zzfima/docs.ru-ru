---
title: Интеграция с AJAX и поддержка JSON
ms.date: 03/30/2017
helpviewer_keywords:
- AJAX integration and JSON support [WCF]
ms.assetid: 3851a8fc-d861-4ac1-873c-96af0343d3a7
ms.openlocfilehash: 0b392044db3fbc926bf77ac305ece294880216d9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ajax-integration-and-json-support"></a>Интеграция с AJAX и поддержка JSON
Поддержка Windows Communication Foundation (WCF) для ASP.NET асинхронных скриптов JavaScript и XML (AJAX) и формат JavaScript Object Notation (JSON) данных позволяют службам WCF предоставлять операции клиентам AJAX. Клиенты AJAX представляют собой веб-страницы которых выполняется код JavaScript и доступ к этих служб WCF, с помощью HTTP-запросов. В этом разделе приведены сведения о такой поддержке и способах ее реализации.  
  
 Дополнительные сведения о ASP.NET AJAX и интеграции с ASP.NET 2.0 см. в разделе [Общие сведения о ASP.NET AJAX](http://go.microsoft.com/fwlink/?LinkId=96725).  
  
## <a name="in-this-section"></a>В этом разделе  
 [Создание служб WCF для ASP.NET AJAX](../../../../docs/framework/wcf/feature-details/creating-wcf-services-for-aspnet-ajax.md)  
 Описывает, как службы WCF в доступные клиентам AJAX, добавив соответствующую конечную точку AJAX, либо через конфигурацию или с помощью фабрики узла службы, настроенного на создание узла службы, который автоматически настраивает конечную точку AJAX.  
  
 [Создание служб WCF AJAX без использования ASP.NET](../../../../docs/framework/wcf/feature-details/creating-wcf-ajax-services-without-aspnet.md)  
 Описывает, как создать службу WCF без использования ASP.NET.  
  
 [Поддержка JSON и других форматов передачи данных](../../../../docs/framework/wcf/feature-details/support-for-json-and-other-data-transfer-formats.md)  
 Описывается поддержка формата JSON, который обычно используется для обмена сообщениями со службами ASP.NET AJAX (вместо XML).  
  
 [Практическое руководство. Миграция веб-служб ASP.NET с поддержкой AJAX на платформу WCF](../../../../docs/framework/wcf/feature-details/how-to-migrate-ajax-enabled-aspnet-web-services-to-wcf.md)  
 Описывает, как перейти на веб-службы WCF с поддержкой AJAX ASP.NET веб-службой.  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Activation.WebScriptServiceHostFactory>  
 [Модель веб-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
