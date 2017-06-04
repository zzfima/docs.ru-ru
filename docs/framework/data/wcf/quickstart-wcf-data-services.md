---
title: "Краткое руководство (службы данных WCF) | Microsoft Docs"
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
  - "службы данных WCF, пример краткого руководства"
  - "службы данных WCF, служба EDM"
ms.assetid: 7b18ca1e-d4d6-4c7a-afb9-ce3cebb98a8d
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Краткое руководство (службы данных WCF)
Это краткое руководство позволяет ознакомиться со службами [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] и [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] с помощью ряда задач, дополняющих содержимое разделов в [Приступая к работе](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md).  
  
## Новые знания  
 Первая задача краткого руководства показывает, как создать службу данных для предоставления канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] из образца базы данных Northwind. В последующих разделах будет открыт доступ к каналу [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] с помощью веб\-браузера и создано клиентское приложение [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)], использующее канал [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] посредством клиентских библиотек.  
  
## Предварительные требования  
 Чтобы выполнить задания данного краткого руководства, установите следующие компоненты:  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
-   Экземпляр [!INCLUDE[msCoName](../../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../../includes/ssnoversion-md.md)]. В том числе SQL Server Express, входящий в установку по умолчанию [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)].  
  
-   Наличие учебной базы данных Northwind. Чтобы скачать этот образец базы данных, см. страницу скачивания [Sample Databases for SQL Server](http://go.microsoft.com/fwlink/?linkid=24758) \(Образцы баз данных для SQL Server\).  
  
## Задачи краткого руководства по службам WCF Data Services  
 [Создание службы данных](../../../../docs/framework/data/wcf/creating-the-data-service.md)  
 Определите приложение [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], определите модель данных, создайте службу данных и включите доступ к ресурсам.  
  
 [Доступ к службе из веб\-браузера](../../../../docs/framework/data/wcf/accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md)  
 Запустите службу из среды [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)] и обратитесь к ней с помощью запросов HTTP GET через веб\-браузер для получения доступа к предоставляемым каналам.  
  
 [Создание клиентского приложения .NET Framework](../../../../docs/framework/data/wcf/creating-the-dotnet-client-application-wcf-data-services-quickstart.md)  
 Создайте клиентское приложение [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] для использования канала [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], свяжите данные с элементами управления Windows, измените данные в связанных элементах управления и отправьте изменения обратно в службу данных.  
  
> [!NOTE]
>  Файлы проекта, создаваемого при изучении краткого руководства, можно скачать на странице [WCF Data Services Documentation Samples](http://go.microsoft.com/fwlink/?LinkId=179994) \(Образцы из документации по службам данных WCF\).  
  
## Следующие шаги  
 [Начало выполнения краткого руководства](../../../../docs/framework/data/wcf/creating-the-data-service.md).  
  
## См. также  
 [Платформа ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md)