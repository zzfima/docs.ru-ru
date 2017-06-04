---
title: "Как определить операцию службы (службы WCF Data Services) | Microsoft Docs"
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
  - "операции службы [службы WCF Data Services]"
  - "Службы WCF Data Services, операции службы"
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Как определить операцию службы (службы WCF Data Services)
Службы [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] предоставляют методы, определенные на сервере, в качестве операций службы.  Операции службы позволяют службе данных предоставить доступ через URI к методу, определенному на сервере.  Для определения операции службы применить к методу атрибут \[`WebGet]` или `[WebInvoke]`.  Для поддержки операторов запросов операция службы должна возвращать экземпляр <xref:System.Linq.IQueryable%601>.  Операции службы могут получить доступ к базовому источнику данных через свойство <xref:System.Data.Services.DataService%601.CurrentDataSource%2A> службы <xref:System.Data.Services.DataService%601>. Дополнительные сведения см. в разделе [Операции служб](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).  
  
 Пример в этом разделе определяет операцию службы с именем `GetOrdersByCity`, возвращающую фильтрованный экземпляр <xref:System.Linq.IQueryable%601> `Orders` и связанные объекты `Order_Details`.  Пример обращается к экземпляру <xref:System.Data.Objects.ObjectContext>, являющемуся источником данных для образца службы данных Northwind.  Эта служба создается после выполнения действий, описанных в разделе [Краткое руководство по службам WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### Определение операции службы в службе данных Northwind  
  
1.  Откройте в проекте службы данных Northwind файл Northwind.svc.  
  
2.  Определите в классе `Northwind` метод операции службы с именем `GetOrdersByCity`, как показано дальше:  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  Добавьте в метод `InitializeService` класса `Northwind` следующий код, разрешающий доступ к операции службы:  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### Запрос к операции службы GetOrdersByCity  
  
-   Введите в веб\-браузере один из следующих URI для вызова операции службы, определенной в следующем примере:  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## Пример  
 В следующем примере реализована операция службы с именем `GetOrderByCity` в службе данных Northwind.  Эта операция использует ADO.NET Entity Framework для возвращения набора сущностей `Orders` и связанных объектов `Order_Details` в виде экземпляра <xref:System.Linq.IQueryable%601> на основе переданного названия города.  
  
> [!NOTE]
>  Операторы запросов поддерживаются для этой конечной точки операции службы, потому что метод возвращает экземпляр <xref:System.Linq.IQueryable%601>.  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## См. также  
 [Определение службы WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)