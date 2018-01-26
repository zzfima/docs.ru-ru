---
title: "Примеры запросов"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 137f8677-494c-4d49-95ce-c17742f2d01f
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 1b3aabf5a47088fa408547527c5f18fa69a48e02
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="query-examples"></a>Примеры запросов
В этом разделе представлен ряд примеров [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] и C# стандартных запросов [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Разработчики, использующие [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)], могут просмотреть гораздо больше примеров в образце решения, представленном в разделе "Образцы". Дополнительные сведения см. в разделе [образцы](../../../../../../docs/framework/data/adonet/sql/linq/samples.md).  
  
> [!IMPORTANT]
>  *DB* часто используется в примерах кода в [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] документации. *DB* считается экземпляр *Northwind* класс, унаследованный от класса <xref:System.Data.Linq.DataContext>.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Статистические запросы](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)  
 Содержит описание использования <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A> и т. д.  
  
 [Возврат первого элемента в последовательности](../../../../../../docs/framework/data/adonet/sql/linq/return-the-first-element-in-a-sequence.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.First%2A>.  
  
 [Возврат или пропуск элементов последовательности](../../../../../../docs/framework/data/adonet/sql/linq/return-or-skip-elements-in-a-sequence.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.Take%2A> и <xref:System.Linq.Enumerable.Skip%2A>.  
  
 [Сортировка элементов последовательности](../../../../../../docs/framework/data/adonet/sql/linq/sort-elements-in-a-sequence.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.OrderBy%2A>.  
  
 [Группировка элементов последовательности](../../../../../../docs/framework/data/adonet/sql/linq/group-elements-in-a-sequence.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.GroupBy%2A>.  
  
 [Удаление дубликатов элементов из последовательности](../../../../../../docs/framework/data/adonet/sql/linq/eliminate-duplicate-elements-from-a-sequence.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.Distinct%2A>.  
  
 [Проверка соответствия условию какого-либо или всех элементов](../../../../../../docs/framework/data/adonet/sql/linq/determine-if-any-or-all-elements-in-a-sequence-satisfy-a-condition.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.All%2A> и <xref:System.Linq.Enumerable.Any%2A>.  
  
 [Сцепление двух последовательностей](../../../../../../docs/framework/data/adonet/sql/linq/concatenate-two-sequences.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.Concat%2A>.  
  
 [Возврат разности наборов между двумя последовательностями](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-difference-between-two-sequences.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.Except%2A>.  
  
 [Возврат пересечения наборов двух последовательностей](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-intersection-of-two-sequences.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.Intersect%2A>.  
  
 [Возврат объединения наборов двух последовательностей](../../../../../../docs/framework/data/adonet/sql/linq/return-the-set-union-of-two-sequences.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.Union%2A>.  
  
 [Преобразование последовательности в массив](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-an-array.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.ToArray%2A>.  
  
 [Преобразование последовательности в универсальный список](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-sequence-to-a-generic-list.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.ToList%2A>.  
  
 [Преобразование типа в универсальный интерфейс IEnumerable](../../../../../../docs/framework/data/adonet/sql/linq/convert-a-type-to-a-generic-ienumerable.md)  
 Содержит примеры использования <xref:System.Linq.Enumerable.AsEnumerable%2A>.  
  
 [Формулировка запросов-объединений и запросов векторного произведения](../../../../../../docs/framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)  
 Содержит примеры использования переходов внешнего ключа в предложениях `from`, `where` и `select`.  
  
 [Формулировка проекций](../../../../../../docs/framework/data/adonet/sql/linq/formulate-projections.md)  
 Содержит примеры сочетания `select` с другими возможностями (например, *анонимные типы*) для создания проекций запросов.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Общие сведения о стандартных операторах запроса](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2)  
 Содержит основные сведения о стандартных операторах запроса.  
  
 [Основные принципы запросов](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 Содержит описание использования [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] принципов, применимых к запросам.  
  
 [Руководство по программированию](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Предоставляет портал для тем, в которых объясняются принципы программирования, связанные с [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].
