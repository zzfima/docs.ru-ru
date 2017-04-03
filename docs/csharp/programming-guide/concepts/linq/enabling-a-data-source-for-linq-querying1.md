---
title: "Включение источника данных для запросов LINQ 1 | Документы Майкрософт"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: d2ef04a5-31a6-45cb-af9a-a5ce7732662c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a5eaa6472c5fd7942f345dc5b4401b85c33504c9
ms.lasthandoff: 03/13/2017

---
# <a name="enabling-a-data-source-for-linq-querying"></a>Включение источника данных для запросов LINQ
Существуют различные способы расширения [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для поддержки запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] к любому источнику данных. Источник данных может быть, например, структурой данных, веб-службой, файловой системой или базой данных. Шаблон [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] упрощает для клиентов осуществление запросов к источникам данных, для которых задействована поддержка запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], поскольку синтаксис и шаблон запроса не меняется. Далее перечислены способы, с помощью которых [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] может быть расширен для этих источников данных.  
  
-   Реализация интерфейса <xref:System.Collections.Generic.IEnumerable%601> в типе для выполнения запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to Objects этого типа.  
  
-   Создание методов стандартных операторов запроса, таких как <xref:System.Linq.Enumerable.Where%2A> и <xref:System.Linq.Enumerable.Select%2A>, расширяющих тип, для поддержки пользовательских запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] этого типа.  
  
-   Создание поставщика для источника данных, который реализует интерфейс <xref:System.Linq.IQueryable%601>. Поставщик, реализующий этот интерфейс, получает запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] в виде деревьев выражения, которые он может выполнять любым способом, например удаленно.  
  
-   Создание поставщика для источника данных, который использует преимущества существующей технологии [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]. Такой поставщик позволит выполнять не только запросы, но и операции вставки, обновления, удаления и сопоставления для определяемых пользователем типов.  
  
 Эти варианты рассматриваются далее.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Включение поддержки запросов LINQ к пользовательскому источнику данных  
  
### <a name="in-memory-data"></a>Данные в памяти  
 Существует два способа включения поддержки запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] к данным, находящимся в памяти. Если данные имеют тип, который реализует <xref:System.Collections.Generic.IEnumerable%601>, можно выполнить запрос данных с помощью [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to Objects. Если добавление перечисления к типу с помощью реализации интерфейса <xref:System.Collections.Generic.IEnumerable%601> не имеет смысла, можно определить методы стандартных операторов запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] в типе, или создать методы стандартных операторов запроса [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], которые расширяют тип. Пользовательские реализации стандартных операторов запроса должны использовать отложенное выполнение для возврата результатов.  
  
### <a name="remote-data"></a>Удаленные данные  
 Лучшим вариантом для поддержки запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] к удаленному источнику данных является реализация интерфейса <xref:System.Linq.IQueryable%601>. Однако это отличается от расширения поставщика, например [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] для источника данных. Модели поставщика для расширения существующих технологий [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], таких как [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], до других типов источников данных, доступных в [!INCLUDE[vs_orcas_long](../../../../csharp/misc/includes/vs_orcas_long_md.md)], отсутствуют.  
  
## <a name="iqueryable-linq-providers"></a>Поставщики IQueryable LINQ  
 Поставщики [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], реализующие <xref:System.Linq.IQueryable%601>, могут существенно различаться по сложности. В этом разделе рассматриваются различные уровни сложности.  
  
 Менее сложные поставщики `IQueryable` могут взаимодействовать с одним методом веб-службы. Этот тип поставщиков является очень специализированным, так как он требует наличия определенных сведений в обрабатываемых запросах. Он имеет закрытую систему типов, возможно, предоставляя один тип результата. Большая часть выполнения запроса происходит локально, например с помощью реализации <xref:System.Linq.Enumerable> стандартных операторов запроса. Менее сложный поставщик может проверять только одно выражение вызова метода в дереве выражений, которое представляет запрос, и оставляет оставшуюся логику запроса обрабатываться в другом месте.  
  
 Поставщик `IQueryable` средней сложности может использовать источник данных, который имеет ограниченно выразительный язык запросов. Если он предназначен для веб-службы, он может взаимодействовать с несколькими методами веб-службы и выбирать метод для вызова на основании вопроса, содержащегося в запросе. Поставщик средней сложности будет иметь более богатую систему типов, чем простой поставщик, но она по-прежнему будет фиксированной. Например, поставщик может предоставлять типы, имеющие связи "один ко многим", которые можно обойти, но он не предоставляет технологии отображения для определяемых пользователем типов.  
  
 Сложный поставщик `IQueryable`, например поставщик [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], может переводить завершенные запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] на выразительный язык запросов, например SQL. Сложные поставщики более общие, чем менее сложные, поскольку они могут обрабатывать более широкий диапазон вопросов в запросе. Он также имеет открытую систему типов и поэтому должен содержать расширяемую инфраструктуру для сопоставления определяемых пользователем типов. Разработка сложного поставщика требует значительных усилий.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.IQueryable%601>   
 <xref:System.Collections.Generic.IEnumerable%601>   
 <xref:System.Linq.Enumerable>   
 [Общие сведения о стандартных операторах запроса (C#)](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
