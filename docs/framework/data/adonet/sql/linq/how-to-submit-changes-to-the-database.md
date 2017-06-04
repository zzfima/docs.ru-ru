---
title: "Как отправить изменения в базу данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c7cba174-9d40-491d-b32c-f2d73b7e9eab
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как отправить изменения в базу данных
Независимо от количества изменений, произведенных над объектами, эти изменения выполняются только над репликам, содержащимся в памяти.  Фактические данные в базе данных при этом не изменяются.  Изменения не передаются на сервер до тех пор, пока не будет явно вызван метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> класса <xref:System.Data.Linq.DataContext>.  
  
 При вызове этого метода класс <xref:System.Data.Linq.DataContext> пытается преобразовать сделанные изменения в эквивалентные команды SQL.  Можно создать собственную пользовательскую логику для переопределения этих действий, однако порядок отправки управляется службой класса <xref:System.Data.Linq.DataContext>, которая называется *обработчиком изменений*.  Ниже представлена последовательность событий.  
  
1.  При вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A> технология [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] просматривает набор известных объектов, чтобы определить, присоединены ли к ним новые экземпляры.  При положительном результате новые экземпляры добавляются в набор отслеживаемых объектов.  
  
2.  Все объекты, содержащие ожидающие изменения, упорядочиваются в последовательности объектов на основе зависимостей между ними.  Объекты, изменения которых зависят от других объектов, располагаются после своих зависимостей.  
  
3.  Непосредственно после передачи фактических изменений [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] начинает транзакцию для инкапсуляции ряда отдельных команд.  
  
4.  Изменения объектов последовательно преобразуются в команды SQL и отправляются на сервер.  
  
 В данный момент любые ошибки, обнаруженные базой данных, приводят к остановке процесса отправки и вызову исключения.  Выполняется откат всех изменений базы данных к состоянию до начала отправки.  Класс <xref:System.Data.Linq.DataContext> по\-прежнему содержит запись всех изменений.  Поэтому можно попытаться исправить проблему и вызвать метод <xref:System.Data.Linq.DataContext.SubmitChanges%2A> еще раз, как показано в следующем примере кода.  
  
## Пример  
 После успешного завершения транзакции, содержащей отправку, класс <xref:System.Data.Linq.DataContext> принимает изменения объектов, пропуская сведения об отслеживании изменений.  
  
 [!code-csharp[DLinqSubmittingChanges#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#1)]
 [!code-vb[DLinqSubmittingChanges#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#1)]  
  
## См. также  
 [Как обнаруживать и разрешать конфликты отправки](../../../../../../docs/framework/data/adonet/sql/linq/how-to-detect-and-resolve-conflicting-submissions.md)   
 [Как управлять конфликтами изменений](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Загрузка образцов баз данных](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Внесение и отправка изменений данных ](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)