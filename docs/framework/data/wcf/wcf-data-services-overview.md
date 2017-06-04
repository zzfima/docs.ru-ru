---
title: "Общие сведения о службах WCF Data Services | Microsoft Docs"
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
  - "WCF Data Services"
  - "WCF Data Services, о"
ms.assetid: 7924cf94-c9a6-4015-afc9-f5d22b1743bb
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Общие сведения о службах WCF Data Services
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют создавать и использовать службы данных для Интернета и интрасети с помощью [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)].  Службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] позволяют предоставлять данные в качестве ресурсов, доступ к которым осуществляется с помощью URI.  Это позволяет обращаться к данным и изменять данные с помощью семантики REST, особенно для таких команд стандарта HTTP, как GET, PUT, POST и DELETE. В этом разделе приведен обзор обоих шаблонов и рекомендации для [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], а также возможности [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] по использованию [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] в приложениях на базе .NET.  
  
## Адресация данных в виде ресурсов  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] предоставляет данные в качестве ресурсов, на которые могут указывать URI. Пути к ресурсам составляются на основе соглашений о связях сущностей модели EDM.  Сущности в этой модели представляют операционные единицы данных в домене приложения, таких как клиенты, заказы, элементы и продукты.  Для получения дополнительной информации см. [Модель EDM](../../../../docs/framework/data/adonet/entity-data-model.md).  
  
 Адресация ресурсов сущностей в службах [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] осуществляется в виде набора сущностей, содержащего экземпляры типов сущностей.  Например, следующий URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders` возвращает все заказы из службы данных `Northwind`, связанной с клиентом, параметру `CustomerID` которого задано значение `ALFKI.`.  
  
 Выражения запросов позволяют выполнять традиционные операции с запросами к ресурсам, такие как фильтрация, сортировка и подкачка страниц.  Например, URI `http://services.odata.org/Northwind/Northwind.svc/Customers('ALFKI')/Orders?$filter=Freight gt 50` фильтрует ресурсы, возвращая только заказы со стоимостью транспортировки, превышающей 50 долларов.  Для получения дополнительной информации см. [Доступ к ресурсам службы данных](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md).  
  
## Доступ к данным с возможностью взаимодействия  
 В сборках [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] для обеспечения взаимодействия службы данных с приложениями, которые не используют платформу .NET Framework, используются стандартные протоколы Интернета.  Возможность использования стандартных URI для адресации данных позволяет приложению обращаться к данным и изменять их с использованием семантики REST, в частности стандартных команд HTTP, таких как GET, PUT, POST и DELETE.  Это позволяет обращаться к службам из любого клиента, поддерживающего синтаксический анализ и доступ к данным, передаваемым по стандартным протоколам HTTP.  
  
 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] определяет набор расширений для протокола публикации Atom \(AtomPub\). Он поддерживает запросы и ответы HTTP в нескольких форматах данных, что позволяет использовать различные клиентские приложения и платформы.  Канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] может представлять данные в формате Atom, формате нотации объектов JavaScript \(JSON\) и в виде простого XML.  Atom является форматом по умолчанию. Формат канала указывается в заголовке HTTP\-запроса.  Дополнительные сведения см. в разделах [OData: формат Atom](http://go.microsoft.com/fwlink/?LinkID=185794) и [OData: формат JSON](http://go.microsoft.com/fwlink/?LinkID=185795).  
  
 При публикации данных в виде канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] для таких операций, как кэширование и проверка подлинности службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], используют другие существующие возможности Интернета.  Для этого службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируются с существующими ведущими приложениями и службами, например ASP.NET, Windows Communication Foundation \(WCF\) и Internet Information Services \(IIS\).  
  
## Независимость хранилища  
 Хотя ресурсы адресуются на базе модели EDM, службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляют каналы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] независимо от базового источника данных. После того как службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] принимают HTTP\-запрос на ресурс, идентифицируемый URI, этот запрос десериализуется и представление запроса передается поставщику [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].  Этот поставщик переводит запрос в формат, относящийся к конкретному источнику данных, и выполняет его в базовом источнике данных. В службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] независимость хранилища достигается путем отделения концептуальной модели, адресующей ресурсы по протоколу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], от конкретной схемы базового источника данных.  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируются со средой ADO.NET Entity Framework, позволяя создавать службы данных, предоставляющие реляционные данные.  Для создания модели данных, содержащей адресуемые ресурсы в виде сущностей и в то же время определяющей сопоставление между этой моделью и таблицами нижележащей базы данных, можно использовать программы для работы с моделью EDM.  Для получения дополнительной информации см. [Поставщик Entity Framework](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md).  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] позволяют создавать службы данных, предоставляющие любые структуры данных, которые возвращают реализацию интерфейса <xref:System.Linq.IQueryable%601>.  Это позволяет создавать службы данных, предоставляющие данные из типов .NET Framework.  Для поддержки операций создания, обновления и удаления должен быть также реализован интерфейс <xref:System.Data.Services.IUpdatable>.  Для получения дополнительной информации см. [Поставщик отражения](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md).  
  
 Интеграция [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] с этими поставщиками данных проиллюстрирована на архитектурной диаграмме далее в этом разделе.  
  
## Пользовательская бизнес\-логика  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] упрощают добавление пользовательской бизнес\-логики в службу данных с помощью перехватчиков и операций службы.  Операции службы — это методы, определенные на сервере и адресуемые с помощью URI в том же формате, что и ресурсы данных.  В работе службы также может использоваться синтаксис выражений запросов для фильтрации, упорядочения и разбивки на страницы данных, возвращенных операцией. Например, URI `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$orderby=OrderDate&$top=10&$skip=10` представляет вызов операции службы с именем `GetOrdersByCity` в службе данных Northwind, возвращающей заказы клиентов из Лондона, с разбиением результатов на страницы и сортировкой по `OrderDate`.  Для получения дополнительной информации см. [Операции служб](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).  
  
 Перехватчики позволяют разработчику интегрировать настраиваемую прикладную логику в процесс обработки запросов и ответов службы данных.  Перехватчики вызываются при выполнении операции запроса, вставки, обновления или удаления над указанным набором сущностей.  При этом перехватчик может изменить данные, применить политику проверки подлинности и даже преждевременно завершить операцию.  Методы перехватчика необходимо явно регистрировать для конкретного набора сущностей, предоставляемого службой данных.  Для получения дополнительной информации см. [Перехватчики](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md).  
  
## Клиентские библиотеки  
 Службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] определяют набор универсальных шаблонов для взаимодействия со службами данных.  Это позволяет создавать на основе этих служб повторно используемые компоненты, включая клиентские библиотеки, упрощающие использование служб данных.  
  
 Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включают клиентские библиотеки для клиентских приложений как на основе .NET Framework, так и на основе Silverlight.  Эти клиентские библиотеки позволяют взаимодействовать со службами данных с помощью объектов .NET Framework.  Кроме того, они поддерживают запросы на базе объектов и запросы LINQ, загрузку связанных объектов, отслеживание изменений и разрешение идентификаторов. Дополнительные сведения см. в разделе [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
 Помимо клиентских библиотек [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] в составе платформ .NET Framework и Silverlight, имеются также другие клиентские библиотеки, позволяющие использовать веб\-канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] в клиентских приложениях, в том числе на основе PHP, AJAX и Java.  Дополнительные сведения см. в разделе [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796).  
  
## Общие сведения об архитектуре  
 На следующей диаграмме показана архитектура [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] для предоставления веб\-каналов [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] и их использования в клиентских библиотеках, поддерживающих [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 ![Схема архитектуры служб данных WCF](../../../../docs/framework/data/wcf/media/astoriaservicearch.gif "AstoriaServiceArch")  
  
## См. также  
 [Службы WCF Data Services 4.5](../../../../docs/framework/data/wcf/index.md)   
 [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)   
 [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Accessing a Data Service \(WCF Data Services\)](http://msdn.microsoft.com/ru-ru/1e54a2b9-2ec6-4002-b8f8-c1d8df37c350)   
 [Клиентская библиотека служб WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Передача репрезентативного состояния \(REST\)](http://go.microsoft.com/fwlink/?LinkId=113919)