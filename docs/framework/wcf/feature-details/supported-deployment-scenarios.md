---
title: "Поддерживаемые сценарии развертывания | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3399f208-3504-4c70-a22e-a7c02a8b94a6
caps.latest.revision: 20
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 20
---
# Поддерживаемые сценарии развертывания
Подмножество функций [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], которые поддерживаются для использования в частично доверенных приложениях, предназначено для обеспечения соответствия требованиям некоторых \(но не всех\) сценариев использования [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. На сервере [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] соответствует требованиям поставщиков услуг совместного размещения в сети Интернет, выполняющих сторонние приложения с наборами разрешений среднего уровня доверия [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] в целях безопасности. На клиенте поддержка частичного доверия [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] реализуется с целью обеспечения соответствия требованиям таких технологий развертывания, как [развертывание ClickOnce](http://go.microsoft.com/fwlink/?LinkId=83712) или технология приложения браузера XAML [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)], обеспечивающих беспрепятственное и безопасное развертывание классических приложений с ненадежных узлов.  
  
## Минимальные требования к разрешениям  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает подмножество функций в приложениях, выполняемых в рамках одного из следующих наборов разрешений со стандартными именами:  
  
-   Разрешения среднего уровня доверия;  
  
-   Набор разрешений зоны Интернета.  
  
 Попытка использовать [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в частично доверенных приложениях с более строгими разрешениями может привести к возникновению исключений безопасности во время выполнения.  
  
 Дополнительные сведения о различных функциях, поддерживаемых в этих наборах разрешений, см. в разделе [Совместимость возможностей частичного доверия](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## Частичное доверие на сервере  
 Многие коммерческие поставщики услуг размещения веб\-приложений [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] требуют, чтобы выполняемые на их серверах приложения запускались с набором разрешений среднего уровня доверия [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)]. Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут работать в таких средах, если они используют привязку <xref:System.ServiceModel.BasicHttpBinding>, <xref:System.ServiceModel.WebHttpBinding> или <xref:System.ServiceModel.WsHttpBinding> с безопасностью на уровне транспорта.  
  
 Службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], выполняемые в средах размещения со средним уровнем доверия, могут действовать как службы промежуточного уровня, отправляя сообщения на другие серверы в ответ на запросы клиента. На сервере поддерживаются промежуточные сценарии, если среда размещения предоставила приложению соответствующее разрешение <xref:System.Net.WebPermission> на отправку исходящих запросов на требуемый сервер.  
  
 Помимо обмена сообщениями по протоколу SOAP с использованием одной из поддерживаемых протоколом SOAP привязок [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает также привязку <xref:System.ServiceModel.WebHttpBinding> для создания веб\-служб в частично доверенных приложениях. При работе с частичным доверием поддерживаются следующие функции [Модель веб\-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md): [Синдикация WCF](../../../../docs/framework/wcf/feature-details/wcf-syndication.md), [Интеграция с AJAX и поддержка JSON](../../../../docs/framework/wcf/feature-details/ajax-integration-and-json-support.md) и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Службы рабочего процесса требуют наличия разрешений полного доверия, их невозможно использовать в частично доверенных приложениях.  
  
 [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] [How to: Use Medium Trust in ASP.NET 2.0](http://go.microsoft.com/fwlink/?LinkId=84603) \(Практическое руководство. Использование среднего уровня доверия в ASP.NET 2.0\).  
  
## Частичное доверие на клиенте  
 Необходимо предпринять определенные дополнительные меры безопасности при загрузке и запуске кода с ненадежных веб\-сайтов Интернета. Технология [развертывания ClickOnce](http://go.microsoft.com/fwlink/?LinkId=83712) и технология приложения браузера XAML [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] \(XBAP\) используют частичное доверие для предоставления ограниченных разрешений \(в зоне Интернета\) ненадежному коду.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] может использоваться для взаимодействия с удаленными серверами из частично доверенных приложений, развернутых с использованием технологии [развертывания ClickOnce](http://go.microsoft.com/fwlink/?LinkId=83712) или XBAP. Набор разрешений для зоны Интернета включает разрешение <xref:System.Net.WebPermission> для исходного узла, которое позволяет этим приложениям взаимодействовать с исходным сервером с помощью любой из поддерживаемых привязок [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], описанных в статье [Совместимость возможностей частичного доверия](../../../../docs/framework/wcf/feature-details/partial-trust-feature-compatibility.md).  
  
## См. также  
 [Управление доступом для кода](http://go.microsoft.com/fwlink/?LinkId=83717)   
 [Обзор размещенных в веб\-браузере приложений Windows Presentation Foundation](http://go.microsoft.com/fwlink/?LinkId=98397)   
 [Частичный уровень доверия](../../../../docs/framework/wcf/feature-details/partial-trust.md)   
 [Средний уровень доверия ASP.NET](http://go.microsoft.com/fwlink/?LinkId=69328)