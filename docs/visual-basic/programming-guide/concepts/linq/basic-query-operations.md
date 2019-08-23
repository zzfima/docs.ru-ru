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
ms.openlocfilehash: 12f10f30dd767f3435044f2bbebe0eb865c29d0c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69939365"
---
# <a name="basic-query-operations-visual-basic"></a>Основные операции запроса (Visual Basic)
В этом разделе приведены краткие сведения [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] о выражениях в Visual Basic и некоторых типичных операциях, выполняемых в запросе. Дополнительные сведения см. в следующих разделах:  
  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
  
 [Запросы](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Пошаговое руководство: Создание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Указание источника данных (из)  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] В запросе первым шагом является указание источника данных, к которому необходимо выполнить запрос. Таким образом, `From` предложение в запросе всегда происходит первым. Операторы запросов выбирают и формируют результат на основе типа источника.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 Предложение задает `customers`источник данных, `cust`и *переменную диапазона*. `From` Переменная диапазона похожа на переменную итерации цикла, за исключением того, что в выражении запроса фактическая итерация не выполняется. При выполнении запроса, часто с помощью `For Each` цикла, переменная диапазона выступает в качестве ссылки на каждый последовательный элемент в. `customers` Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде. Примеры запросов, написанных с неявной типизацией и без них, см. [в разделе связи типов в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Дополнительные сведения об использовании `From` предложения в Visual Basic см. в разделе [предложение from](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Фильтрация данных (где)  
 Возможно, наиболее распространенной операцией запроса является применение фильтра в виде логического выражения. Затем запрос возвращает только те элементы, для которых выражение имеет значение true. Для выполнения фильтрации используется предложение.`Where` Фильтр указывает, какие элементы в источнике данных включить в результирующую последовательность. В следующем примере включаются только клиенты, имеющие адрес в Лондоне.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Для `And` объединениявыражений`Or` фильтра в предложенииможноиспользоватьлогическиеоператоры,такиекаки.`Where` Например, чтобы возвратить только тех клиентов из Лондона, имя которых — Девон, используйте следующий код:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Чтобы вернуть клиентов из Лондона или Париж, используйте следующий код:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Дополнительные сведения об использовании `Where` предложения в Visual Basic см. в разделе [предложение WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Упорядочение данных (ORDER BY)  
 Часто бывает удобно сортировать возвращаемые данные в определенном порядке. `Order By` Предложение приведет к сортировке элементов в возвращаемой последовательности по указанному полю или полям. Например, следующий запрос сортирует результаты на основе `Name` свойства. Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке от а до я.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`. Значение по умолчанию — `Ascending` , `Descending` если не задан ни `Ascending` параметр, ни значение.  
  
 Дополнительные сведения об использовании `Order By` предложения в Visual Basic см. в разделе [ORDER BY](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Выбор данных (выбор)  
 `Select` Предложение задает форму и содержимое возвращаемых элементов. Например, можно указать, будут ли результаты состоять из полных `Customer` объектов, всего одного `Customer` свойства, подмножества свойств, сочетания свойств из различных источников данных или какого-либо нового типа результата на основе вычислений. Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.  
  
 Чтобы получить коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Если экземпляр является большим объектом, который содержит много полей, и все, что требуется получить, — это имя, можно выбрать `cust.Name`, как показано в следующем примере. `Customer` Определение локального типа распознает, что это изменяет тип результата из коллекции `Customer` объектов на коллекцию строк.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Чтобы выбрать несколько полей из источника данных, доступны два варианта:  
  
- `Select` В предложении укажите поля, которые необходимо включить в результат. Компилятор определит анонимный тип, в котором эти поля являются свойствами. Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Поскольку возвращаемые элементы в следующем примере являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в любом расположении в коде. Имя типа, назначенное компилятором, содержит символы, недопустимые в стандартном коде Visual Basic. В следующем примере элементы в коллекции, возвращаемые запросом в `londonCusts4` , являются экземплярами анонимного типа.  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     -или-  
  
- Определите именованный тип, содержащий определенные поля, которые необходимо включить в результат, и создайте и инициализируйте экземпляры типа в `Select` предложении. Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты вне коллекции, в которой они возвращаются, или если необходимо передать их в качестве параметров в вызовы метода. `londonCusts5` В следующем примере в качестве типа используется IEnumerable (Of намефоне).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Дополнительные сведения об использовании `Select` предложения в Visual Basic см. в разделе [предложение SELECT](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Соединение данных (присоединение и объединение групп)  
 В `From` предложении можно объединить более одного источника данных несколькими способами. Например, следующий код использует два источника данных и неявно объединяет свойства обоих из них в результате. Запрос выбирает учащихся, чьи фамилии начинаются с гласной.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> Этот код можно запустить со списком учащихся, созданных в [следующих руководствах: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Ключевое слово эквивалентно значению `INNER JOIN` в SQL. `Join` Он объединяет две коллекции на основе совпадающих значений ключей между элементами в двух коллекциях. Запрос возвращает все элементы коллекции, имеющие совпадающие значения ключей, или часть ее элементов. Например, следующий код дублирует действие предыдущего неявного объединения.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`объединяет коллекции в одну иерархическую коллекцию, `LEFT JOIN` как в SQL. Дополнительные сведения см. в разделе [предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Группирование данных (Group By)  
 Можно добавить `Group By` предложение для группирования элементов в результатах запроса в соответствии с одним или несколькими полями элементов. Например, следующий код группирует учащихся по классу year.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Если запустить этот код с помощью списка учащихся, созданных в [инструкции по выполнению следующих действий: Создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), выходные данные `For Each` инструкции:  
  
 Год Junior  
  
 Туккер, Майкл  
  
 Гарсиа, Хьюго  
  
 Гарсиа, Дебра  
  
 Туккер, Лэнс  
  
 Год Старше  
  
 Омелченко, Светлана  
  
 Осада, Мичико  
  
 Фахури, Фэди  
  
 Фенг, Ханинг  
  
 Адамс, Терри  
  
 Год Свежая  
  
 Мортенсен, Свен  
  
 Гарсиа, Сезар  
  
 Вариант, показанный в следующем коде, упорядочивает класс years, а затем упорядочивает учащихся в каждом году по фамилии.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Дополнительные сведения о `Group By`см. в разделе [предложение GROUP BY](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic.IEnumerable%601>
- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
