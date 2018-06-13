---
title: Основные операции запроса (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 5587a60e97464324659b325e38a18ac25488d30d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33644125"
---
# <a name="basic-query-operations-visual-basic"></a>Основные операции запроса (Visual Basic)
В этом разделе приводится краткое введение в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] выражения на языке Visual Basic и некоторых типичных операций, выполняемых в запросе. Дополнительные сведения см. в следующих разделах:  
  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [Пошаговое руководство: Написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Указание источника данных (от)  
 В [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса, первым шагом является указание источника данных, необходимо выполнить запрос. Таким образом `From` предложения в запросе всегда идет первым. Операторы запросов выберите и формирование результатов в зависимости от типа источника.  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 `From` Предложение указывает источник данных, `customers`и *переменной диапазона*, `cust`. Переменная диапазона является как переменная итерации цикла, за исключением того, что в выражении запроса не происходит фактической итерации. При выполнении запроса, обычно с помощью `For Each` цикла, переменная диапазона используется как ссылка на каждый последующий элемент в `customers`. Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде. Примеры запросов, написанные с использованием и без явную типизацию см. в разделе [связи между типами в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Дополнительные сведения об использовании `From` предложение в Visual Basic. в разделе [предложения From](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Фильтрация данных (где)  
 Возможно, наиболее распространенной операцией запроса является применение фильтра в форме логического выражения. Запрос возвращает только те элементы, для которых выражение имеет значение true. Объект `Where` предложение используется для выполнения фильтрации. Фильтр указывает элементы в источнике данных для включения в результирующей последовательности. В следующем примере включаются только клиенты, находящиеся в Лондоне.  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 Можно использовать логические операторы, такие как `And` и `Or` для объединения выражений фильтра в `Where` предложения. Например чтобы вернуть только клиентов из Лондона с именем Devon, используйте следующий код:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Чтобы вернуть клиентов из Лондона или Парижа, используйте следующий код:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Дополнительные сведения об использовании `Where` предложение в Visual Basic. в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Упорядочение данных (Order By)  
 Часто бывает удобно упорядочить возвращенные данные в определенном порядке. `Order By` Предложение сортирует элементы в возвращаемой последовательности должны быть отсортированы в указанном поле или поля. Например, следующий запрос сортирует результаты на основе `Name` свойство. Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке, от A до Z.  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`. Значение по умолчанию — `Ascending` при ни `Ascending` , ни `Descending` указано.  
  
 Дополнительные сведения об использовании `Order By` предложение в Visual Basic. в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Выбор данных (Выбор)  
 `Select` Предложение определяет форму и содержимое возвращаемых элементов. Например, можно указать, будут ли результаты состоять из полных `Customer` объектов только один `Customer` свойство, подмножество свойств, сочетания свойств из различных источников данных или некоторых новых типов в соответствии с вычисленными. Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.  
  
 Чтобы получить коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Если `Customer` экземпляра является большим объектом и содержит много полей и все, что требуется извлечь имя, можно выбрать `cust.Name`, как показано в следующем примере. Вывод локального типа распознает и изменит тип результата из коллекции `Customer` объекты в коллекцию строк.  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Чтобы выбрать несколько полей из источника данных, есть два варианта:  
  
-   В `Select` предложение, укажите поля, которые необходимо включить в результат. Компилятор будет определить анонимный тип, имеющий эти поля как свойства. Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Поскольку возвращенные элементы в следующем примере являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в другом месте в коде. Имя компилятором для типа содержит символы, которые являются недопустимыми в обычном коде Visual Basic. В следующем примере элементы в коллекции, возвращенные запросом в `londonCusts4` являются экземплярами анонимного типа  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     - или -  
  
-   Определите именованный тип, содержащий конкретные поля, которые требуется включить в результат, создайте и инициализируйте экземпляры типа в `Select` предложения. Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты за пределами коллекции, в котором они возвращаются, или если нужно передать их в качестве параметров при вызове метода. Тип `londonCusts5` в следующем примере является IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Дополнительные сведения об использовании `Select` предложение в Visual Basic. в разделе [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Присоединяемый данных (соединения и соединения)  
 Можно объединить несколько источников данных, в `From` предложение несколькими способами. Например следующий код использует два источника данных и неявно объединяет свойства их в результат. Запрос выбирает студентов, чьи фамилии начинаются с гласные.  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Этот код можно выполнить со списком студентов, созданным в [как: создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 `Join` Ключевое слово является эквивалентом `INNER JOIN` в SQL. Он объединяет две коллекции на основании совпадающих значений ключей между элементами в двух коллекциях. Запрос возвращает все или часть элементов коллекции с совпадающими значениями ключей. Например следующий код дублирует действие предыдущего неявного объединения.  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 `Group Join` объединяет коллекции в одну иерархическую коллекцию, так же, как `LEFT JOIN` в SQL. Дополнительные сведения см. в разделе [предложения Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложения Join группы](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Группирование данных (Group By)  
 Можно добавить `Group By` предложение для группировки элементов в результатах запроса по полям один или несколько элементов. Например следующий код группирует студентов по годам класса.  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 При выполнении этого кода, используя список студентов, созданный в [как: создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), выходные данные `For Each` инструкции:  
  
 Год: молодых  
  
 Гладких, Майкл  
  
 Орехов, Алексей  
  
 Орехов, Дина  
  
 Гладких, Андрей  
  
 Год: старший  
  
 Omelchenko Svetlana  
  
 Osada Michiko  
  
 Грачев, Николай  
  
 Ожогина, Инна  
  
 Шабалин, Александр  
  
 Год: обучения  
  
 Mortensen Свен  
  
 Орехов, Владимир  
  
 Вариант, показанный в следующем коде упорядочивает годы обучения и упорядочивает учащихся в течение каждого года по фамилии.  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Дополнительные сведения о `Group By`, в разделе [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>См. также  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
 [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
