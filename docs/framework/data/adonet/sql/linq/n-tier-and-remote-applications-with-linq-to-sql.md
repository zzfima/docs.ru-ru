---
title: "Многоуровневые и удаленные приложения с LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Многоуровневые и удаленные приложения с LINQ to SQL
Существует возможность создания многоуровневых приложений, использующих [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], контекст данных, классы сущностей и логики конструкций запросов обычно размещаются на среднем уровне, являющемся уровнем доступа к данным \(DAL\).  Бизнес\-логика и непостоянные данные могут быть полностью реализованы в разделяемых классах, методах сущностей, контексте данных либо в отдельных классах.  
  
 Уровень клиента или представления вызывает методы в удаленном интерфейсе среднего уровня; DAL в этом интерфейсе выполнит запросы или хранимые процедуры, сопоставленные методам <xref:System.Data.Linq.DataContext>.  Обычно средний уровень возвращает данные клиентам в виде XML\-представлений сущностей или прокси\-объектов.  
  
 На среднем уровне сущности создаются при помощи контекста данных, который отслеживает их состояние и управляет отложенной загрузкой из базы данных и передачей изменений в базу данных.  Эти сущности присоединены к `DataContext`.  Однако после отправки сущностей на другой уровень с помощью сериализации происходит их отсоединение, означающее, что `DataContext` больше не отслеживает их состояние.  Сущности, отправляемые клиентом обратно для обновлений, следует повторно присоединить к контексту данных, прежде чем [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] сможет отправить изменения в базу данных.  Если для проверок оптимистической блокировки требуются исходные значения и\/или метки времени, клиент должен предоставить их обратно на средний уровень.  
  
 В приложениях ASP.NET <xref:System.Web.UI.WebControls.LinqDataSource> управляет большей частью данного сложного процесса.  Дополнительные сведения см. в разделе [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/ru-ru/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## Дополнительные ресурсы  
 Дополнительные сведения о развертывании многоуровневого приложения, использующего [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], см. в следующих разделах.  
  
-   [N\-уровневое использование LINQ to SQL с ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [Технология LINQ to SQL в многоуровневых приложениях с веб\-службами](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [LINQ to SQL и тесно связанные клиент\-серверные приложения](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [Реализация многоуровневой бизнес\-логики](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [Получение данных и операции CUD в многоуровневых приложениях \(LINQ to SQL\)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 Дополнительные сведения о многоуровневых приложениях, использующих ADO.NET DataSets, см в разделе [Работа с наборами данных в N\-уровневых приложениях](../Topic/Work%20with%20datasets%20in%20n-tier%20applications.md).  
  
## См. также  
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)