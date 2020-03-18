---
title: Операции Join (C#)
ms.date: 07/20/2015
ms.assetid: 5105e0da-1267-4c00-837a-f0e9602279b8
no-loc:
- Join
- GroupJoin
ms.openlocfilehash: 6e2ec1a0c8120f6869b7c0a196b77d118762a8dd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "76868009"
---
# <a name="join-operations-c"></a>Операции соединения (C#)

*Соединение* двух источников данных — это связь объектов в одном источнике данных с объектами, которые имеют общий атрибут в другом источнике данных.  
  
 Соединение является важной операцией в запросах, направленных на источники данных, отношения которых друг к другу нельзя отследить напрямую. В объектно-ориентированном программировании оно может означать корреляцию между немоделируемыми объектами, например такими, как обратное направление одностороннего отношения. Примером одностороннего отношения является класс Customer, имеющий свойство типа City (город), в то время как класс City не имеет свойства, которое является коллекцией объектов Customer (клиент). В случае наличия списка объектов City для поиска всех клиентов в каждом городе можно использовать операцию соединения.  
  
 На платформе LINQ представлены методы объединения <xref:System.Linq.Enumerable.Join%2A> и <xref:System.Linq.Enumerable.GroupJoin%2A>. Они выполняют эквисоединения, или соединения, которые сопоставляют два источника данных на основе равенства их ключей. (Для сравнения, Transact-SQL поддерживает операции соединения, отличные от оператора "равно", например оператор "меньше, чем".) В терминах реляционных баз данных <xref:System.Linq.Enumerable.Join%2A> реализует внутреннее соединение — тип соединения, в котором возвращаются только те объекты, у которых есть совпадения в другом наборе данных. Метод <xref:System.Linq.Enumerable.GroupJoin%2A> не имеет прямого эквивалента в терминах реляционных баз данных, но реализует надмножество внутренних соединений и левых внешних соединений. Левое внешнее соединение — это соединение, которое возвращает каждый элемент первого (левого) источника данных, даже если в другом источнике данных не имеется соответствующих элементов.  
  
 На следующем рисунке показано концептуальное представление из двух наборов и элементов, входящих в эти наборы, которые включены либо во внутреннее соединение, либо в левое внешнее соединение.  
  
 ![Два перекрывающихся кольца, отображающие внешнее&#47;внутреннее соединение.](./media/join-operations/join-method-overlapping-circles.png)  
  
## <a name="methods"></a>Методы  
  
|Имя метода|Описание|Синтаксис выражения запроса C#|Дополнительные сведения|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Join|Соединяет две последовательности на основании функций селектора ключа и извлекает пары значений.|`join … in … on … equals …`|<xref:System.Linq.Enumerable.Join%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Join%2A?displayProperty=nameWithType>|  
|GroupJoin|Соединяет две последовательности на основании функций селектора ключа и группирует полученные при сопоставлении данные для каждого элемента.|`join … in … on … equals … into …`|<xref:System.Linq.Enumerable.GroupJoin%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.GroupJoin%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Примеры синтаксиса выражений запросов
  
### Join  
  
В следующем примере предложение `join … in … on … equals …` используется для объединения двух последовательностей на основе конкретного значения.
  
[!code-csharp[Join](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#Join)]  

### GroupJoin  

В следующем примере используется предложение `join … in … on … equals … into …` для объединения двух последовательностей на основе конкретного значения, а полученные совпадения для каждого элемента группируются.
  
[!code-csharp[GroupJoin](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csLINQJoinOperation/CS/JoinOperation.cs#GroupJoin)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq>
- [Общие сведения о стандартных операторах запроса (C#)](./standard-query-operators-overview.md)
- [Анонимные типы](../../classes-and-structs/anonymous-types.md)
- [Формулировка запросов-объединений и запросов векторного произведения](../../../../framework/data/adonet/sql/linq/formulate-joins-and-cross-product-queries.md)
- [предложение join](../../../language-reference/keywords/join-clause.md)
- [Join с помощью составных ключей](../../../linq/join-by-using-composite-keys.md)
- [Объединение содержимого из файлов разных форматов (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md)
- [Упорядочение результатов предложения соединения](../../../linq/order-the-results-of-a-join-clause.md)
- [Выполнение пользовательских операций соединения](../../../linq/perform-custom-join-operations.md)
- [Выполнение групповых соединений](../../../linq/perform-grouped-joins.md)
- [Выполнение внутренних соединений](../../../linq/perform-inner-joins.md)
- [Выполнение левых внешних соединений](../../../linq/perform-left-outer-joins.md)
- [Заполнение коллекций объектов из нескольких источников (LINQ) (C#)](./how-to-populate-object-collections-from-multiple-sources-linq.md)
