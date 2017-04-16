---
title: "Сравнение удаленного и локального выполнения | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee50e943-9349-4c84-ab1c-c35d3ada1a9c
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Сравнение удаленного и локального выполнения
Запросы можно выполнять либо удаленно \(то есть ядро базы данных выполняет запрос в базе данных\) или локально \([!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] выполняет запрос в локальном кэше\).  
  
## Удаленное выполнение  
 Рассмотрим следующий запрос:  
  
 [!code-csharp[DLinqQueryConcepts#7](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#7)]
 [!code-vb[DLinqQueryConcepts#7](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#7)]  
  
 Если база данных содержит тысячи строк заказов, для обработки небольшого подмножества совсем не обязательно извлекать все строки.  В [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] класс <xref:System.Data.Linq.EntitySet%601> реализует интерфейс <xref:System.Linq.IQueryable>.  Этот метод гарантирует удаленное выполнение подобных запросов.  Благодаря этому методу пользователь получает два существенных преимущества.  
  
-   Извлекаются только необходимые данные.  
  
-   Запросы, выполняемые ядром базы данных зачастую более эффективны благодаря индексам базы данных.  
  
## локальное выполнение  
 В других случаях бывает необходимо иметь полный набор связанных записей в локальном кэше.  Для этой цели класс <xref:System.Data.Linq.EntitySet%601> предоставляет метод <xref:System.Data.Linq.EntitySet%601.Load%2A> для явной загрузки всех членов класса <xref:System.Data.Linq.EntitySet%601>.  
  
 Если класс <xref:System.Data.Linq.EntitySet%601> уже загружен, последующие запросы выполняются локально.  Этот метод полезен с двух точек зрения.  
  
-   Если полный набор необходимо использовать локально или несколько раз, можно избежать удаленных запросов и связанных с ними задержек.  
  
-   Сущность можно сериализовать как полную сущность.  
  
 В следующем фрагменте кода показывается, как добиться локального выполнения.  
  
 [!code-csharp[DLinqQueryConcepts#8](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryConcepts/cs/Program.cs#8)]
 [!code-vb[DLinqQueryConcepts#8](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryConcepts/vb/Module1.vb#8)]  
  
## Сравнение  
 Эти две возможности предоставляют мощное сочетание параметров: удаленное выполнение для больших коллекций и локальное выполнение для малых коллекций или в тех случаях, когда требуется вся коллекция.  Удаленное выполнение реализуется с помощью интерфейса <xref:System.Linq.IQueryable>, а локальное выполнение \- посредством хранящейся в памяти коллекции <xref:System.Collections.Generic.IEnumerable%601>.  Инструкции по принудительному локальному выполнению \(то есть использованию коллекции <xref:System.Collections.Generic.IEnumerable%601>\), см. в разделе [Преобразование последовательности в общий интерфейс IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md).  
  
### Запросы к неупорядоченным наборам  
 Обратите внимание на важное отличие между локальной коллекцией, которая реализует метод <xref:System.Collections.Generic.List%601>, и коллекцией, предоставляющей удаленное выполнение запросов к *неупорядоченным наборам* в реляционной базе данных.  Для методов <xref:System.Collections.Generic.List%601>, например при использовании значений индексов, требуется семантика списка, которая, как правило, не реализуется посредством удаленного запроса к неупорядоченному набору.  По этой причине подобные методы неявно загружают класс <xref:System.Data.Linq.EntitySet%601>, чтобы получить возможность локального выполнения.  
  
## См. также  
 [Основные понятия о запросах](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)