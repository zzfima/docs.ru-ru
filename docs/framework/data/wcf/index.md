---
title: "Службы WCF Data Services 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "HTML"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "Astoria"
  - "Службы WCF Data Services, начало работы"
ms.assetid: 73d2bec3-7c92-4110-b905-11bb0462357a
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Службы WCF Data Services 4.5
Компонент платформы .NET Framework [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] \(известный ранее как службы данных ADO.NET\) позволяет создавать службы, использующие [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] для представления и получения данных по сети или интранету с помощью семантики протокола [REST](http://go.microsoft.com/fwlink/?LinkId=113919). [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] представляет данные в качестве источников, к которым можно обращаться по URI.  Обращаться к данным и изменять их можно с помощью стандартных HTTP\-заголовков GET, PUT, POST и DELETE. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] использует связи и сущности [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md) для представления источников в качестве наборов сущностей, связанных с помощью ассоциаций.  
  
 При адресации и обновлении ресурсов службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] используют протокол [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  В результате доступ к этим службам можно получить из любого клиента, который поддерживает [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] позволяет осуществлять запросы и запись данных в ресурсы с использованием традиционных форматов передачи: Atom, набора стандартов обмена и обновления данных на основе XML, и нотации объектов JavaScript \(JSON\), текстового формата обмена данными, широко применяемого в приложениях AJAX.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяет предоставлять данные, поступающие из различных источников, в виде каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Средства Visual Studio упрощают создание служб на основе [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с использованием модели данных ADO.NET платформы Entity Framework. Можно также создать каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] на основе классов среды CLR и даже данных с поздним связыванием или нетипизированных данных.  
  
 В состав служб [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] также включен набор клиентских библиотек: одна для типовых клиентских приложений .NET Framework, а другая специально для приложений на основе Silverlight.  Данные клиентские библиотеки предоставляют возможности объектно ориентированного программирования для доступа к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из таких платформ, как .NET Framework и Silverlight.  
  
## Подготовка к изучению темы  
 В зависимости от потребностей, ознакомьтесь с началом работы со службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] в одном из следующих разделов.  
  
 Необходимо перейти непосредственно к…  
 -   [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
  
-   [Краткое руководство по Silverlight](http://go.microsoft.com/fwlink/?LinkId=192782)  
  
-   [Краткое руководство по Silverlight для разработчиков Windows Phone](http://go.microsoft.com/fwlink/?LinkId=214535)  
  
 Просто ознакомьте меня с примерами кода…  
 -   [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)  
  
-   [Как выполнять запросы к службе данных](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
-   [Как привязать данные к элементам Windows Presentation Foundation](../../../../docs/framework/data/wcf/bind-data-to-wpf-elements-wcf-data-services.md)  
  
 Требуются дополнительные сведения о [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]…  
 -   [Технический документ. Введение в OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Веб\-сайт протокола Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
-   [OData: часто задаваемые вопросы](http://go.microsoft.com/fwlink/?LinkID=185867)  
  
 Хочу посмотреть некоторые видеоматериалы…  
 -   [Руководство для начинающих по службам WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=220864)  
  
-   [Видеофильмы о службах данных WCF для разработчиков](http://go.microsoft.com/fwlink/?LinkId=220861)  
  
-   [OData: веб\-узел разработчиков](http://go.microsoft.com/fwlink/?LinkID=185866)  
  
 Требуются комплексные образцы  
 -   [Образцы документации по службам WCF Data Services в коллекции образцов MSDN](http://go.microsoft.com/fwlink/?LinkID=220865)  
  
-   [Другие образцы служб WCF Data Services в коллекции образцов MSDN](http://go.microsoft.com/fwlink/?LinkId=220866)  
  
-   [OData: SDK](http://go.microsoft.com/fwlink/?LinkID=185248)  
  
 Как происходит интеграция со средствами Visual Studio  
 -   [Формирование клиентской библиотеки службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
  
-   [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
  
-   [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
  
 Рекомендуемые действия в этой ситуации  
 -   [Общие сведения](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
  
-   [Технический документ. Введение в OData](http://go.microsoft.com/fwlink/?LinkId=220867)  
  
-   [Сценарии приложений](../../../../docs/framework/data/wcf/application-scenarios-wcf-data-services.md)  
  
 Необходима информация об использовании Silverlight…  
 -   [Краткое руководство по Silverlight](http://go.microsoft.com/fwlink/?LinkId=192782)  
  
-   [Службы WCF Data Services \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=143149)  
  
-   [Начало работы с Silverlight](http://go.microsoft.com/fwlink/?LinkId=148366)  
  
 Я хочу создать приложение Windows Phone…  
 -   [Краткое руководство по Silverlight для разработчиков Windows Phone](http://go.microsoft.com/fwlink/?LinkId=214535)  
  
-   [Клиент протокола OData для Windows Phone](http://go.microsoft.com/fwlink/?LinkID=208749)  
  
 Сведения об использовании LINQ…  
 -   [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
  
-   [Рекомендации по LINQ](../../../../docs/framework/data/wcf/linq-considerations-wcf-data-services.md)  
  
-   [Как выполнять запросы к службе данных](../../../../docs/framework/data/wcf/how-to-execute-data-service-queries-wcf-data-services.md)  
  
 Необходимы дополнительные сведения...  
 -   [Блог группы служб WCF Data Services](http://go.microsoft.com/fwlink/?LinkID=150511)  
  
-   [Ресурсы](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)  
  
-   [Центр разработчиков WCF Data Services](http://go.microsoft.com/fwlink/?LinkId=220868)  
  
-   [Веб\-сайт протокола Open Data Protocol](http://go.microsoft.com/fwlink/?LinkID=184554)  
  
## Содержание  
 [Общие сведения](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)  
 Содержит общие сведения о функциях и возможностях, доступных в службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  
  
 [What's New in WCF Data Services](http://msdn.microsoft.com/ru-ru/cf22cad5-b8d9-472b-8d7c-b863b64eaae8)  
 Описывает новые функции в службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] и поддержку новых функций [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 Описывает предоставление и получение каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  
  
 [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 Описывает создание и настройку службы данных, предоставляющей каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 Описывает использование клиентских библиотек для использования канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из клиентского приложения .NET Framework.  
  
## См. также  
 [Передача репрезентативного состояния \(REST\)](http://go.microsoft.com/fwlink/?LinkId=113919)