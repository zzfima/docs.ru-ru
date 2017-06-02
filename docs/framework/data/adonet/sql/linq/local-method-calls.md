---
title: "Локальные вызовы методов | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c34b5012-aee9-4994-9364-1d99d12b7463
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Локальные вызовы методов
Локальным вызовом метода называется вызов, который выполняется в объектной модели.  Удаленный вызов метода \- это вызов, который [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] преобразует в команды SQL и передает в ядро базы данных для выполнения.  Локальные вызовы методов необходимы в том случае, если [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] не удается преобразовать вызов в команды SQL.  В противном случае возникает исключение <xref:System.InvalidOperationException>.  
  
## Пример 1  
 В следующем примере класс `Order` сопоставлен с таблицей "Orders" базы данных "Northwind".  К классу добавлен локальный экземпляр метода.  
  
 В запросе 1 конструктор для класса `Order` выполняется локально.  В запросе 2, если бы [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] попытался преобразовать метод `LocalInstanceMethod()` в команды SQL, то эта попытка завершилась бы неуспешно с вызовом исключения <xref:System.InvalidOperationException>. Но поскольку [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] обеспечивает поддержку локальных вызовов метода, исключение не выдается.  
  
 [!code-csharp[DlinqLocalMethodCall#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/Program.cs#1)]
 [!code-vb[DlinqLocalMethodCall#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/Module1.vb#1)]  
  
 [!code-csharp[DlinqLocalMethodCall#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqLocalMethodCall/cs/northwind.cs#2)]
 [!code-vb[DlinqLocalMethodCall#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqLocalMethodCall/vb/northwind.vb#2)]  
  
## См. также  
 [Дополнительные сведения](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)