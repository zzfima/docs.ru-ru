---
title: "Включение источника данных для LINQ Querying2 | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c412f0cf-ff0e-4993-ab3d-1b49e23f00f8
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 34bdc4e056d982799eac35eb2398dd3f23f6f351
ms.lasthandoff: 03/13/2017

---
# <a name="enabling-a-data-source-for-linq-querying"></a>Включение источника данных для запросов LINQ
Существуют различные способы расширения [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для включения любого источника данных, должны запрашиваться в [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] шаблон. Источник данных может быть, например, структурой данных, веб-службой, файловой системой или базой данных. Шаблон [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] упрощает для клиентов осуществление запросов к источникам данных, для которых задействована поддержка запросов [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)], поскольку синтаксис и шаблон запроса не меняется. Ситуации, в которых [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] может быть расширен для этих данных источники включают следующие:  
  
-   Реализация <xref:System.Collections.Generic.IEnumerable%601>интерфейс в типе, чтобы включить [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] для запросов объектов этого типа.</xref:System.Collections.Generic.IEnumerable%601>  
  
-   Создание методов операторов стандартных запросов такие как <xref:System.Linq.Enumerable.Where%2A>и <xref:System.Linq.Enumerable.Select%2A>, расширяющих тип, для поддержки пользовательских [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросов этого типа.</xref:System.Linq.Enumerable.Select%2A> </xref:System.Linq.Enumerable.Where%2A>  
  
-   Создание поставщика для источника данных, который реализует <xref:System.Linq.IQueryable%601>интерфейса.</xref:System.Linq.IQueryable%601> Поставщик, реализующий этот интерфейс, получает запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] в виде деревьев выражения, которые он может выполнять любым способом, например удаленно.  
  
-   Создание поставщика для источника данных, который использует преимущества существующей [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] технологии. Такой поставщик позволит выполнять не только запросы, но и операции вставки, обновления, удаления и сопоставления для определяемых пользователем типов.  
  
 Эти варианты рассматриваются далее.  
  
## <a name="how-to-enable-linq-querying-of-your-data-source"></a>Включение поддержки запросов LINQ к пользовательскому источнику данных  
  
### <a name="in-memory-data"></a>Данные в памяти  
 Существует два способа включения [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросы к данным в памяти. Если данные имеют тип, который реализует <xref:System.Collections.Generic.IEnumerable%601>, могут запрашивать данные с помощью [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] к объектам.</xref:System.Collections.Generic.IEnumerable%601> Если он не имеет смысла для Добавление перечисления к типу с помощью реализации <xref:System.Collections.Generic.IEnumerable%601>интерфейс, можно определить [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] стандартные методы оператора в этом типе запросов или создать [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] методы стандартных операторов запросов, расширяющих тип.</xref:System.Collections.Generic.IEnumerable%601> Пользовательские реализации стандартных операторов запроса должны использовать отложенное выполнение для возврата результатов.  
  
### <a name="remote-data"></a>Удаленные данные  
 Лучшим вариантом для поддержки [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросы к удаленному источнику данных является реализация <xref:System.Linq.IQueryable%601>интерфейса.</xref:System.Linq.IQueryable%601> Однако это отличается от расширения поставщика, например [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] для источника данных. Модели поставщика для расширения существующих [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] технологий, таких как [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], до других типов источников данных, доступных в [!INCLUDE[vs_orcas_long](../../../../csharp/misc/includes/vs_orcas_long_md.md)].  
  
## <a name="iqueryable-linq-providers"></a>Поставщики IQueryable LINQ  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]Поставщики, реализующие <xref:System.Linq.IQueryable%601>могут существенно различаться по сложности.</xref:System.Linq.IQueryable%601> В этом разделе рассматриваются различные уровни сложности.  
  
 Менее сложные поставщики `IQueryable` могут взаимодействовать с одним методом веб-службы. Этот тип поставщиков является очень специализированным, так как он требует наличия определенных сведений в обрабатываемых запросах. Он имеет закрытую систему типов, возможно, предоставляя один тип результата. Большая часть выполнения запроса происходит локально, например с помощью <xref:System.Linq.Enumerable>реализации стандартных операторов запроса.</xref:System.Linq.Enumerable> Менее сложный поставщик может проверять только одно выражение вызова метода в дереве выражений, которое представляет запрос, и оставляет оставшуюся логику запроса обрабатываться в другом месте.  
  
 Поставщик `IQueryable` средней сложности может использовать источник данных, который имеет ограниченно выразительный язык запросов. Если он предназначен для веб-службы, он может взаимодействовать с несколькими методами веб-службы и выбирать метод для вызова на основании вопроса, содержащегося в запросе. Поставщик средней сложности будет иметь более богатую систему типов, чем простой поставщик, но она по-прежнему будет фиксированной. Например, поставщик может предоставлять типы, имеющие связи "один ко многим", которые можно обойти, но он не предоставляет технологии отображения для определяемых пользователем типов.  
  
 Сложный поставщик `IQueryable`, например поставщик [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)], может переводить завершенные запросы [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] на выразительный язык запросов, например SQL. Сложные поставщики более общие, чем менее сложные, поскольку они могут обрабатывать более широкий диапазон вопросов в запросе. Он также имеет открытую систему типов и поэтому должен содержать расширяемую инфраструктуру для сопоставления определяемых пользователем типов. Разработка сложного поставщика требует значительных усилий.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq.IQueryable%601></xref:System.Linq.IQueryable%601>   
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 <xref:System.Linq.Enumerable></xref:System.Linq.Enumerable>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
