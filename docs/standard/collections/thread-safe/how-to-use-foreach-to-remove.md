---
title: "Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- thread-safe collections, how to enumerate blocking collectoin
ms.assetid: 2096103c-22f7-420d-b631-f102bc33a6dd
caps.latest.revision: 13
author: mairaw
ms.author: mairaw
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b0f0ed30ae5192ed8a8f069d591855857bd2fa49
ms.contentlocale: ru-ru
ms.lasthandoff: 09/19/2017

---
# <a name="how-to-use-foreach-to-remove-items-in-a-blockingcollection"></a>Практическое руководство. Использование оператора ForEach для удаления элементов в коллекции BlockingCollection
Помимо извлечения элементов из коллекции <xref:System.Collections.Concurrent.BlockingCollection%601> с помощью методов <xref:System.Collections.Concurrent.BlockingCollection%601.Take%2A> и <xref:System.Collections.Concurrent.BlockingCollection%601.TryTake%2A>, можно использовать цикл [foreach](~/docs/csharp/language-reference/keywords/foreach-in.md) ([For Each](~/docs/visual-basic/language-reference/statements/for-each-next-statement.md) в Visual Basic) для удаления элементов до тех пор, пока добавление не будет завершено и коллекция не станет пустой. Это называется *изменяющим перечислением* или *поглощающим перечислением*, поскольку, в отличие от типичного цикла `foreach` (`For Each`), этот перечислитель изменяет исходную коллекцию путем удаления элементов.  
  
## <a name="example"></a>Пример  
 В приведенном ниже примере показано, как удалить все элементы в классе <xref:System.Collections.Concurrent.BlockingCollection%601>, используя цикл `foreach` (`For Each`).  
  
 [!code-csharp[CDS_BlockingCollection#03](../../../../samples/snippets/csharp/VS_Snippets_Misc/cds_blockingcollection/cs/example03.cs#03)]
 [!code-vb[CDS_BlockingCollection#03](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_blockingcollection/vb/enumeratebc.vb#03)]  
  
 Этот пример использует цикл `foreach` совместно с методом <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A?displayProperty=fullName> в потоке-потребителе, что приводит к удалению каждого элемента из коллекции, как только он перечислен. <xref:System.Collections.Concurrent.BlockingCollection%601?displayProperty=fullName> ограничивает максимальное количество элементов, находящихся в коллекции в любой момент времени. Выполнение перечисления коллекции подобным образом блокирует поток-потребитель, если доступные элементы отсутствуют или коллекция является пустой. В этом примере блокировка не имеет значения, так как поток-производитель добавляет элементы быстрее, чем их может использовать потребитель.  
  
 Невозможно гарантировать перечисление элементов в том же порядке, в котором они добавляются потоками-производителями.  
  
 Для перечисления коллекции без ее изменения просто используйте оператор `foreach` (`For Each`) без использования метода <xref:System.Collections.Concurrent.BlockingCollection%601.GetConsumingEnumerable%2A>. Тем не менее важно понимать, что такой тип перечисления представляет снимок коллекции в конкретный момент времени. Если другие потоки добавят или удалят элементы параллельно с выполнением цикла, цикл может не отобразить фактическое состояние коллекции.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Concurrent?displayProperty=fullName>   
 [Параллельное программирование](../../../../docs/standard/parallel-programming/index.md)

