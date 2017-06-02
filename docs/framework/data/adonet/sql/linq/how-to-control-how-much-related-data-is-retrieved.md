---
title: "Как управлять объемом получаемых взаимосвязанных данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как управлять объемом получаемых взаимосвязанных данных
Используйте метод <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>, чтобы указать, какие данные, связанные с основными целевыми объектами, должны быть одновременно извлечены.  Например, если известно, что понадобятся сведения о заказах клиентов, можно использовать метод <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>, чтобы гарантировать извлечение данных о заказах одновременно с извлечением с данных о клиентах.  Благодаря такому подходу для получения обоих наборов сведений требуется одно обращение к базе данных.  
  
> [!NOTE]
>  Данные, связанные с основными целевыми объектами запроса, можно извлекать посредством извлечения перекрестного произведения объектов в виде одной большой проекции, как, например, в случае извлечения заказов одновременно с извлечением клиентов.  Однако такой подход имеет свои недостатки.  Например, результаты являются всего лишь проекциями, а не сущностями, доступными для изменения и сохранения с помощью технологии [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Кроме того, при таком способе может извлекаться большой объем ненужных данных.  
  
## Пример  
 В следующем примере при выполнении запроса извлекаются все заказы \(`Orders`\) для всех клиентов \(`Customers`\), расположенных в Лондоне.  В результате, при последующем доступе к свойству `Orders` объекта `Customer` не инициируется новый запрос базы данных.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## См. также  
 [Выполнение запросов к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)