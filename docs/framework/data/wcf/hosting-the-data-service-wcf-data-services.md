---
title: "Размещение службы данных (службы WCF Data Services) | Microsoft Docs"
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
  - "Службы WCF Data Services, настройка"
  - "Службы WCF Data Services, Windows Communication Foundation"
ms.assetid: b48f42ce-22ce-4f8d-8f0d-f7ddac9125ee
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Размещение службы данных (службы WCF Data Services)
С помощью [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] можно создать службу, предоставляющую данные в виде канала [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)].  Эта служба данных определена в качестве класса, наследуемого от <xref:System.Data.Services.DataService%601>.  Этот класс содержит функции, необходимые для обработки сообщений запроса, выполнения операций обновления в источнике данных и создания сообщений ответов, как предусмотрено в [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Однако служба данных не может выполнить привязку к сетевому сокету и прослушивать через него входящие запросы HTTP.  Реализацию этой обязательной функциональности служба данных возлагает на размещающий компонент.  
  
 Узел службы данных выполняет следующие задачи от имени источника данных:  
  
-   Прослушивает запросы и перенаправляет их службе данных.  
  
-   Создает экземпляр службы данных для каждого запроса.  
  
-   Запрашивает обработку входящего запроса службой данных.  
  
-   Отправляет ответ от имени службы данных.  
  
 Для упрощения размещения службы данных службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] интегрируются с Windows Communication Foundation \(WCF\).  Служба данных обеспечивает реализацию по умолчанию WCF, которая используется как узел службы данных в приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  Следовательно, службу данных можно разместить одним из следующих способов:  
  
-   В приложении [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].  
  
-   В управляемом приложении, которое поддерживает резидентные службы WCF.  
  
-   В других специализированных узлах службы данных.  
  
## Размещение службы данных в приложении ASP.NET  
 При использовании диалогового окна **Добавить новый элемент** в среде Visual Studio для определения службы данных в приложении ASP.NET среда создает в проекте два новых файла.  Первый файл имеет расширение `.svc` и определяет для среды выполнения WCF способ создания экземпляра службы данных.  Ниже приведен пример этого файла для образца службы данных Northwind, созданного при изучении [краткого руководства](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md):  
  
```  
<%@ ServiceHost Language="C#"   
    Factory="System.Data.Services.DataServiceHostFactory,   
            System.Data.Services, Version=4.0.0.0,   
            Culture=neutral, PublicKeyToken=b77a5c561934e089"   
    Service="NorthwindService.Northwind" %>   
```  
  
 Эта директива используется для инструкции приложения для создания узла службы для именованного класса службы данных путем использования класса <xref:System.Data.Services.DataServiceHostFactory>.  
  
 Страница с выделенным кодом для файла `.svc` содержит класс, являющийся реализацией самой службы данных, определенной следующим образом для образца службы данных Northwind:  
  
 [!code-csharp[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#servicedefinition)]
 [!code-vb[Astoria Quickstart Service#ServiceDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#servicedefinition)]  
  
 Служба данных работает как служба WCF, поэтому она интегрируется с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и следует модели веб\-программирования WCF. Дополнительные сведения см. в разделах [Службы WCF и ASP.NET](../../../../docs/framework/wcf/feature-details/wcf-services-and-aspnet.md) и [Модель веб\-программирования HTTP WCF](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md).  
  
## Резидентные службы WCF  
 Реализация интеграции с WCF позволяет службам [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] резидентно размещать службы данных в качестве службы WCF.  Служба может быть резидентно размещена в любом приложении [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], например в консольном приложении.  Класс <xref:System.Data.Services.DataServiceHost>, наследуемый от <xref:System.ServiceModel.Web.WebServiceHost>, используется для создания экземпляров службы данных по определенному адресу.  
  
 Резидентное размещение можно использовать для разработки и тестирования, поскольку оно упрощает развертывание и диагностику службы.  Однако этот вид размещения не предоставляет расширенные функции размещения и управления, предоставляемые в [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] или в службе IIS. Дополнительные сведения см. в разделе [Размещение в управляемом приложении](../../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).  
  
## Определение специализированных узлов служб данных  
 В случае если ограничения, связанные с реализацией узла WCF, неприемлемы, для службы данных можно также определить настраиваемый узел.  Любой класс, реализующий интерфейс <xref:System.Data.Services.IDataServiceHost>, можно использовать в качестве сетевого узла для службы данных.  Настраиваемый узел должен реализовать интерфейс <xref:System.Data.Services.IDataServiceHost> и поддерживать следующие основные функции узла службы данных:  
  
-   Обеспечивать службу данных корневым путем службы.  
  
-   Обрабатывать данные заголовков запроса и ответа в соответствующей реализации элемента <xref:System.Data.Services.IDataServiceHost>.  
  
-   Обрабатывать исключения, сформированные службой данных.  
  
-   Проверять параметры в строке запроса.  
  
## См. также  
 [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)   
 [Представление данных в виде службы](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)   
 [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)