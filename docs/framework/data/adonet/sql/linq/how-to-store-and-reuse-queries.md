---
title: "Как сохранять и повторно использовать запросы | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a012bd79-1809-45e3-adea-0229532396cc
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Как сохранять и повторно использовать запросы
При наличии приложения, которое неоднократно выполняет схожие по структуре запросы, можно существенно увеличить производительность, если скомпилировать запрос один раз и затем выполнить его несколько раз с различными параметрами.  Например, приложению может потребоваться получение всех клиентов из определенного города; название города указывается пользователем в форме во время выполнения.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] поддерживает использование для этой цели *скомпилированных запросов*.  
  
> [!NOTE]
>  Данный метод использования удобен для большинства случаев применения скомпилированных запросов.  Возможны и другие методы.  Например, скомпилированные запросы можно сохранить в качестве статических членов разделяемого класса, который расширяет код, созданный конструктором.  
  
## Пример  
 Во многих сценариях может потребоваться повторно использовать запросы в разных потоках.  В таких случаях особенно эффективным становится метод сохранения скомпилированных запросов в статических переменных.  В следующем примере кода предполагается, что класс `Queries` предназначен для хранения скомпилированных запросов, а класс "Northwind" представляет строго типизированный класс <xref:System.Data.Linq.DataContext>.  
  
 [!code-csharp[DLinqQuerying#6](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#6)]
 [!code-vb[DLinqQuerying#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#6)]  
  
 [!code-csharp[DLinqQuerying#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#7)]
 [!code-vb[DLinqQuerying#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#7)]  
  
## Пример  
 В настоящий момент невозможно сохранить \(в статических переменных\) запросы, которые возвращают *анонимный тип*, так как у типа нет имени и его нельзя использовать как универсальный аргумент.  В следующем примере демонстрируется, как можно решить эту проблему, создавая тип, представляющий результат, а затем используя его как универсальный аргумент.  
  
 [!code-csharp[DLinqQuerying#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#8)]
 [!code-vb[DLinqQuerying#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#8)]  
  
## См. также  
 <xref:System.Data.Linq.CompiledQuery>   
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)   
 [Выполнение запросов к базе данных](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)