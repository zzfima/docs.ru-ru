---
title: "Начало работы [LINQ to SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: db8a557a-fef8-4f4f-bb91-8cff7250ee25
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Начало работы [LINQ to SQL)
С помощью [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] можно использовать технологию [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] для доступа к базам данных SQL тем же образом, что и к коллекции в памяти.  
  
 В следующем примере кода создается объект `nw` для представления базы данных `Northwind`, выполняется запрос к таблице `Customers`, фильтруются строки для поиска клиентов \(`Customers`\) из Лондона \(`London`\) и выбирается строка `CompanyName` для извлечения.  
  
 При выполнении цикла извлекается коллекция значений `CompanyName`.  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## Следующие шаги  
 Дополнительные примеры, касающиеся, в частности, операций вставки и обновления, см. в разделе [Возможности LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/what-you-can-do-with-linq-to-sql.md).  
  
 Далее ознакомьтесь с некоторыми пошаговыми руководствами и учебниками, чтобы получить практический навык работы с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  См. раздел [Обучение с помощью пошаговых руководств](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).  
  
 И наконец, узнайте, как приступить к разработке собственного проекта [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], прочитав раздел [Типичные действия по использованию LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/typical-steps-for-using-linq-to-sql.md).  
  
## См. также  
 [LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/index.md)   
 [Introduction to LINQ](../../../../../../ocs/visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Модель объектов LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)