---
title: "Основные операции запроса (Visual Basic) | Документы Microsoft"
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
helpviewer_keywords:
- data sources [LINQ in Visual Basic]
- Join clause [LINQ in Visual Basic]
- ordering data [LINQ in Visual Basic]
- projections [LINQ in Visual Basic]
- LINQ [Visual Basic], query operations
- Order By clause [LINQ in Visual Basic]
- joining data [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], basic operations
- selecting data [LINQ in Visual Basic]
- Group By clause [LINQ in Visual Basic]
- grouping data [LINQ in Visual Basic]
- Select clause [LINQ in Visual Basic]
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: 37
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87ff9173b5ff72385c8ecdc3ff13735e7be2a21d
ms.lasthandoff: 03/13/2017

---
# <a name="basic-query-operations-visual-basic"></a>Основные операции запроса (Visual Basic)
В этом разделе приводится краткое введение в [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] выражения в Visual Basic и некоторых типичных операций, выполняемых в запросе. Дополнительные сведения см. в следующих разделах:  
  
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [: Пошаговое руководство](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Указание источника данных (от)  
 В [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запрос, первым делом следует указать источник данных, который требуется запросить. Таким образом `From` предложения в запросе всегда идет первым. Операторы запросов выберите и формирование результатов в зависимости от типа источника.  
  
 [!code-vb[VbLINQBasicOps&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 `From` Предложение указывает источник данных, `customers`и *переменной диапазона*, `cust`. Переменная диапазона схожа с переменной итерации цикла, за исключением того, что в выражении запроса не происходит фактической итерации. Когда запрос выполняется часто с помощью `For Each` цикла, переменная диапазона используется как ссылка на каждый последующий элемент в `customers`. Поскольку компилятор может вывести тип `cust`, необходимо явно указать. Примеры запросов, написанные с использованием и без явного ввода см. [связи типов в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Дополнительные сведения об использовании `From` предложение в Visual Basic в разделе [предложение From](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Фильтрация данных (Where)  
 Вероятно, наиболее распространенной операцией запроса является применение фильтра в форме логического выражения. Запрос возвращает только те элементы, для которых выражение истинно. Объект `Where` для выполнения фильтрации используется предложение. Фильтр указывает элементы в источнике данных, чтобы включить в результирующую последовательность. В следующем примере включаются только заказчики, находящиеся в Лондоне.  
  
 [!code-vb[VbLINQBasicOps&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 Можно использовать логические операторы, такие как `And` и `Or` для объединения критериев фильтров в `Where` предложения. Например для получения только заказчиков из Лондона с именем Devon, используйте следующий код:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Для получения заказчиков из Лондона или Парижа, используйте следующий код:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Дополнительные сведения об использовании `Where` предложение в Visual Basic в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Упорядочение данных (Order By)  
 Часто бывает удобно упорядочить возвращенные данные в определенном порядке. `Order By` Предложение сортирует элементы в возвращаемой последовательности должны быть отсортированы по указанному полю или полям. Например, следующий запрос сортирует результаты на основе `Name` свойство. Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке от А до я.  
  
 [!code-vb[VbLINQBasicOps&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Чтобы упорядочить результаты в обратном порядке от я до А, используйте `Order By...Descending` предложения. Значение по умолчанию — `Ascending` при ни `Ascending` , ни `Descending` указано.  
  
 Дополнительные сведения об использовании `Order By` предложение в Visual Basic в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Выбор данных (Выбор)  
 `Select` Предложение определяет форму и содержимое возвращаемых элементов. Например, можно указать, будут ли результаты состоять из полных `Customer` объектов лишь один `Customer` свойство, подмножества свойств, сочетания свойств из различных источников данных или некоторых новых типов в зависимости от вычислений. Когда `Select` предложение создает нечто, отличное от копии исходного элемента, операция называется *проекции*.  
  
 Чтобы извлечь коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:  
  
 [!code-vb[VbLINQBasicOps&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Если `Customer` экземпляра является большим объектом и содержит много полей, и все, что необходимо получить имя, можно выбрать `cust.Name`, как показано в следующем примере. Вывод локального типа распознает и изменит тип результата из коллекции `Customer` объектов коллекции строк.  
  
 [!code-vb[VbLINQBasicOps&#5;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Чтобы выбрать несколько полей из источника данных, имеется два варианта:  
  
-   В `Select` предложение, укажите поля, которые нужно включить в результат. Компилятор определит анонимный тип, имеющий эти поля как свойства. Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Поскольку возвращенные элементы в следующем примере являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в другом месте в коде. Имя компилятором для типа содержит символы, которые являются недопустимыми в обычном коде Visual Basic. В следующем примере элементы в коллекции, возвращенные запросом в `londonCusts4` экземпляров анонимного типа  
  
     [!code-vb[VbLINQBasicOps №&6;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     -или-  
  
-   Определите именованный тип, содержащий конкретные поля, которые требуется включить в результат, создайте и инициализируйте экземпляры типа в `Select` предложения. Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты за пределами коллекции, в котором они возвращаются, или если необходимо передавать их в качестве параметров при вызове метода. Тип `londonCusts5` в следующем примере является IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps&#7;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps №&8;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Дополнительные сведения об использовании `Select` предложение в Visual Basic в разделе [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Данные соединения (соединения и Group Join)  
 Можно объединить несколько источников данных в `From` предложение несколькими способами. Например следующий код использует два источника данных и неявно объединяет свойства их в результат. Запрос выбирает студентов, чьи фамилии начинаются с гласной.  
  
 [!code-vb[VbLINQBasicOps №&9;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Этот код можно выполнить со списком студентов, созданным в [Практическое руководство: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 `Join` Ключевое слово является эквивалентом `INNER JOIN` в SQL. Он объединяет две коллекции на основании совпадающих значений ключей между элементами в двух коллекциях. Запрос возвращает все или часть элементов коллекции с совпадающими значениями ключей. Например следующий код дублирует действие предыдущего неявного объединения.  
  
 [!code-vb[VbLINQBasicOps&#10;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join`объединяет коллекции в одну иерархическую коллекцию аналогично `LEFT JOIN` в SQL. Дополнительные сведения см. в разделе [предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложение Join группы](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Группирование данных (Group By)  
 Можно добавить `Group By` предложение для группировки элементов в результатах запроса по полям один или несколько элементов. Например следующий код группирует студентов по курсам.  
  
 [!code-vb[VbLINQBasicOps&11;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 При выполнении этого кода, используя список студентов, созданный в [Практическое руководство: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), вывод `For Each` инструкция:  
  
 Год: молодых  
  
 Такер Майкл  
  
 Орехов, Алексей  
  
 Орехов, Дина  
  
 Гладких, Андрей  
  
 Год: старший  
  
 Omelchenko Svetlana  
  
 Osada Michiko  
  
 Грачев, Николай  
  
 Ожогина, Инна  
  
 Александр Шабалин  
  
 Год: обучения  
  
 Mortensen Свен  
  
 Орехов, Владимир  
  
 Вариант, показанный в следующем коде, упорядочивает годы обучения и упорядочивает студентов каждого курса по фамилиям.  
  
 [!code-vb[VbLINQBasicOps&#12;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Дополнительные сведения о `Group By`, в разделе [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [Общие сведения о стандартных операторах (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
