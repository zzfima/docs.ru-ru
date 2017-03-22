---
title: "Объединение (Visual Basic) | Документы Microsoft"
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
ms.assetid: 39ab4854-ac84-4738-9d0b-3cb79be84db4
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
ms.openlocfilehash: dce1adb5b918674bc8ee8fc48c8ff5b3c3814a88
ms.lasthandoff: 03/13/2017

---
# <a name="join-operations-visual-basic"></a>Объединение (Visual Basic)
Объект *объединение* двух источников данных — это связь объектов в одном источнике данных с объектами, имеющими общий атрибут, в другом источнике данных.  
  
 Соединение является важной операцией в запросах, направленных на источники данных, отношения которых друг к другу нельзя отследить напрямую. В объектно-ориентированном программировании оно может означать корреляцию между немоделируемыми объектами, например такими, как обратное направление одностороннего отношения. Примером одностороннего отношения является класс Customer, имеющий свойство типа City (город), в то время как класс City не имеет свойства, которое является коллекцией объектов Customer (клиент). В случае наличия списка объектов City для поиска всех клиентов в каждом городе можно использовать операцию соединения.  
  
 Методы соединения LINQ framework являются <xref:System.Linq.Enumerable.Join%2A>и <xref:System.Linq.Enumerable.GroupJoin%2A>.</xref:System.Linq.Enumerable.GroupJoin%2A> </xref:System.Linq.Enumerable.Join%2A> Эти методы выполняют эквисоединения, или соединения, сопоставляющие два источника данных на основе равенства их ключей. (Для сравнения, Transact-SQL поддерживает операции соединения, отличные от оператора "равно", например оператор "меньше, чем".) В терминах реляционных баз данных <xref:System.Linq.Enumerable.Join%2A>реализует внутреннее соединение — тип соединения, в котором возвращаются только те объекты, которые имеют совпадение в наборе данных.</xref:System.Linq.Enumerable.Join%2A> <xref:System.Linq.Enumerable.GroupJoin%2A>Метод не имеет прямого эквивалента в терминах реляционных баз данных, но реализует надмножество внутренних соединений и левых внешних соединений.</xref:System.Linq.Enumerable.GroupJoin%2A> Левое внешнее соединение является соединением, которое возвращает каждый элемент первого (левого) источника данных, даже если он не имеет соответствующих элементов в другом источнике данных.  
  
 На следующем рисунке показано концептуальное представление из двух наборов и элементов, входящих в эти наборы, которые включены либо во внутреннее соединение, либо в левое внешнее соединение.  
  
 ![Два накладывающихся кольца, отображающие внешнее/внутреннее. ] (../../../../csharp/programming-guide/concepts/linq/media/joincircles.png "JoinCircles")  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса для Visual Basic|Дополнительные сведения|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|Join|Соединяет две последовательности на основании функций селектора ключа и извлекает пары значений.|`From x In …, y In … Where x.a = y.a`<br /><br /> -или-<br /><br /> `Join … [As …]In … On …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName></xref:System.Linq.Enumerable.Join%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=fullName></xref:System.Linq.Queryable.Join%2A?displayProperty=fullName>|  
|GroupJoin|Соединяет две последовательности на основании функций селектора ключа и группирует полученные при сопоставлении данные для каждого элемента.|`Group Join … In … On …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=fullName><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName></xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=fullName>|  
  
## <a name="see-also"></a>См. также  
 <xref:System.Linq></xref:System.Linq>   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Формировать соединения и запросы перекрестного произведения](http://msdn.microsoft.com/library/d8072ede-0521-4670-9bec-1778ceeb875b)   
 [Предложение JOIN](../../../../visual-basic/language-reference/queries/join-clause.md)   
 [Практическое руководство: объединение содержимого из файлов разных форматов (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md)   
 [Практическое руководство: заполнение коллекций объектов из нескольких источников (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-object-collections-from-multiple-sources-linq.md)
