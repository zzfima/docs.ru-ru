---
title: "Как включить доступ к службе данных (службы WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Службы WCF Data Services, настройка"
ms.assetid: 3d830bcd-32b4-4f26-9287-d58a071452c6
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Как включить доступ к службе данных (службы WCF Data Services)
В службах [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] требуется явно предоставлять доступ к ресурсам, предоставляемым службой данных.  Это значит, что после создания новой службы данных все равно требуется явно предоставлять доступ к отдельным ресурсам в виде набора сущностей.  В этом разделе показано, как включить доступ на чтение и запись к пяти наборам сущностей в службе данных Борей, созданной при выполнении раздела [Краткое руководство](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md). Перечисление <xref:System.Data.Services.EntitySetRights> определено с помощью <xref:System.FlagsAttribute>, поэтому можно использовать логический оператор ИЛИ в целях задания нескольких разрешений для одного набора сущностей.  
  
> [!NOTE]
>  Любой клиент, имеющий доступ к приложению ASP.NET, имеет также доступ к ресурсам, предоставляемым службой данных.  Для предотвращения несанкционированного доступа к ресурсам производственной службы данных необходимо также установить защиту самого приложения.  Для получения дополнительной информации см. [NIB: ASP.NET Security](http://msdn.microsoft.com/ru-ru/04b37532-18d9-40b4-8e5f-ee09a70b311d).  
  
### Включение доступа к службе данных  
  
-   В коде службы данных замените код местозаполнителя в функции `InitializeService` следующим текстом:  
  
     [!code-csharp[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart service/cs/northwind.svc.cs#allreadconfig)]
     [!code-vb[Astoria Quickstart Service#AllReadConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart service/vb/northwind.svc.vb#allreadconfig)]  
  
     Это обеспечивает клиентам доступ для чтения и записи к наборам сущностей `Orders` и `Order_Details` и доступ только для чтения к наборам сущностей `Customers`.  
  
## См. также  
 [Как разработать службу данных WCF Data Service, работающую на IIS](../../../../docs/framework/data/wcf/how-to-develop-a-wcf-data-service-running-on-iis.md)   
 [Настройка службы данных](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)