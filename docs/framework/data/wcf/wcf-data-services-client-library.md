---
title: "Клиентская библиотека служб WCF Data Services | Microsoft Docs"
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
  - "DataServiceContext, класс, о классе DataServiceContext"
  - "DataServiceQuery, класс, о классе DataServiceQuery"
  - "Службы WCF Data Services, клиентская библиотека"
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Клиентская библиотека служб WCF Data Services
Любое приложение сможет взаимодействовать со службами данных на основе [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)], если оно может отправить HTTP\-запрос и обработать канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], возвращенный службой данных. Эта совместимость позволяет получить доступ к службам [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из многих типов приложений на основе веб\-технологий.  Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] включают в себя клиентские библиотеки, предоставляющие более широкие программные возможности для доступа к каналам [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из приложений на базе .NET Framework или Silverlight.  
  
 Клиентская библиотека содержит два основных класса: <xref:System.Data.Services.Client.DataServiceContext> и <xref:System.Data.Services.Client.DataServiceQuery%601>.  Класс <xref:System.Data.Services.Client.DataServiceContext> инкапсулирует операции, поддерживающие работу с конкретной службой данных.  Хотя службы [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] не сохраняют состояние, контекст его сохраняет.  В связи с этим класс <xref:System.Data.Services.Client.DataServiceContext> можно использовать для поддержки состояния клиента между операциями со службой данных, что позволяет реализовать такие стратегии, как управление изменениями.  Этот класс также управляет идентификаторами и отслеживает изменения.  Класс <xref:System.Data.Services.Client.DataServiceQuery%601> представляет запрос к определенному набору сущностей.  
  
 Этот раздел описывает использование клиентских библиотек для доступа и изменения данных из клиентского приложения .NET Framework.  Дополнительные сведения об использовании клиентской библиотеки [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] с приложением на основе Silverlight см. в разделе [Службы WCF Data Services \(Silverlight\)](http://go.microsoft.com/fwlink/?LinkId=186016).  Для использования канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] в приложениях других видов имеются другие клиентские библиотеки.  Дополнительные сведения см. в разделе [OData SDK](http://go.microsoft.com/fwlink/?LinkID=185796).  
  
## В этом подразделе  
 [Формирование клиентской библиотеки службы данных](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 Описывает создание клиентской библиотеки и клиентских классов службы данных, основанных на каналах [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
 [Запросы к службе данных](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 Описывает выполнение запросов к службе данных из приложения на основе .NET Framework с помощью клиентских библиотек.  
  
 [Загрузка отложенного содержимого](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 Описывает загрузку дополнительного содержимого, не включенного в первоначальный ответ на запрос.  
  
 [Обновление службы данных](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 Описывает создание, изменение и удаление сущностей и отношений с помощью клиентских библиотек.  
  
 [Асинхронные операции](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 Описывает возможности, предоставляемые клиентскими библиотеками для асинхронной работы со службой данных.  
  
 [Пакетные операции](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 Описывает отправку нескольких запросов к службе данных в одном пакете с помощью клиентских библиотек.  
  
 [Привязка данных к элементам управления](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 Описывает привязку элементов управления к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], возвращенному службой данных.  
  
 [Вызов операций служб](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 Описывает, как использовать клиентскую библиотеку для вызова операций службы.  
  
 [Управление контекстом службы данных](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 Описывает параметры управления режимом работы клиентской библиотеки.  
  
 [Работа с двоичными данными](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 Описывает доступ к двоичным данным, возвращенным службой данных в виде потока данных, и их изменение.  
  
## См. также  
 [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)