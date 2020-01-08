---
title: Основные операции запроса
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
ms.openlocfilehash: b9216dba23f49e4d9fd99687e38f5c13addde8fb
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636878"
---
# <a name="basic-query-operations-visual-basic"></a>Основные операции запроса (Visual Basic)
В этом разделе приведены краткие сведения о выражениях LINQ в Visual Basic и некоторых типичных операциях, выполняемых в запросе. Дополнительные сведения см. в следующих разделах:  
  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
  
 [Запросы](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Пошаговое руководство. Написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Указание источника данных (из)  
 В запросе LINQ первым шагом является указание источника данных, к которому необходимо выполнить запрос. Таким образом, предложение `From` в запросе всегда происходит первым. Операторы запросов выбирают и формируют результат на основе типа источника.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 В предложении `From` указываются источник данных, `customers`и *переменная диапазона*`cust`. Переменная диапазона похожа на переменную итерации цикла, за исключением того, что в выражении запроса фактическая итерация не выполняется. При выполнении запроса, часто с помощью цикла `For Each`, переменная диапазона служит ссылкой на каждый последовательный элемент в `customers`. Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде. Примеры запросов, написанных с неявной типизацией и без них, см. [в разделе связи типов в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Дополнительные сведения об использовании предложения `From` в Visual Basic см. в разделе [предложение from](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Фильтрация данных (где)  
 Возможно, наиболее распространенной операцией запроса является применение фильтра в виде логического выражения. Затем запрос возвращает только те элементы, для которых выражение имеет значение true. Для выполнения фильтрации используется предложение `Where`. Фильтр указывает, какие элементы в источнике данных включить в результирующую последовательность. В следующем примере включаются только клиенты, имеющие адрес в Лондоне.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Для объединения выражений фильтра в предложении `Where` можно использовать логические операторы, такие как `And` и `Or`. Например, чтобы возвратить только тех клиентов из Лондона, имя которых — Девон, используйте следующий код:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Чтобы вернуть клиентов из Лондона или Париж, используйте следующий код:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Дополнительные сведения об использовании предложения `Where` в Visual Basic см. в разделе [предложение WHERE](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Упорядочение данных (ORDER BY)  
 Часто бывает удобно сортировать возвращаемые данные в определенном порядке. Предложение `Order By` приведет к сортировке элементов в возвращаемой последовательности по указанному полю или полям. Например, следующий запрос сортирует результаты на основе свойства `Name`. Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке от а до я.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`. Значение по умолчанию — `Ascending`, если не указано ни `Ascending`, ни `Descending`.  
  
 Дополнительные сведения об использовании предложения `Order By` в Visual Basic см. в разделе [предложение ORDER BY](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Выбор данных (выбор)  
 Предложение `Select` задает форму и содержимое возвращаемых элементов. Например, можно указать, будут ли результаты состоять из полных `Customer` объектов, всего одного `Customer` свойства, подмножества свойств, сочетания свойств из различных источников данных или какого-либо нового типа результата на основе вычислений. Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.  
  
 Чтобы получить коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Если `Customer` экземпляр представляет собой большой объект, который содержит много полей, и все, что требуется получить, — это имя, можно выбрать `cust.Name`, как показано в следующем примере. Определение локального типа распознает, что это изменяет тип результата из коллекции `Customer` объектов на коллекцию строк.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Чтобы выбрать несколько полей из источника данных, доступны два варианта:  
  
- В предложении `Select` укажите поля, которые необходимо включить в результат. Компилятор определит анонимный тип, в котором эти поля являются свойствами. Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Поскольку возвращаемые элементы в следующем примере являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в любом расположении в коде. Имя типа, назначенное компилятором, содержит символы, недопустимые в стандартном коде Visual Basic. В следующем примере элементы в коллекции, возвращаемые запросом в `londonCusts4`, являются экземплярами анонимного типа.  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     \- или -  
  
- Определите именованный тип, содержащий определенные поля, которые необходимо включить в результат, и создайте и инициализируйте экземпляры типа в предложении `Select`. Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты вне коллекции, в которой они возвращаются, или если необходимо передать их в качестве параметров в вызовы метода. Тип `londonCusts5` в следующем примере — IEnumerable (Of Намефоне).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Дополнительные сведения об использовании предложения `Select` в Visual Basic см. в разделе [предложение SELECT](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Соединение данных (присоединение и объединение групп)  
 В предложении `From` можно объединить более одного источника данных несколькими способами. Например, следующий код использует два источника данных и неявно объединяет свойства обоих из них в результате. Запрос выбирает учащихся, чьи фамилии начинаются с гласной.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> Этот код можно запустить со списком учащихся, созданных в ходе [создания списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Ключевое слово `Join` эквивалентно `INNER JOIN` в SQL. Он объединяет две коллекции на основе совпадающих значений ключей между элементами в двух коллекциях. Запрос возвращает все элементы коллекции, имеющие совпадающие значения ключей, или часть ее элементов. Например, следующий код дублирует действие предыдущего неявного объединения.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` объединяет коллекции в одну иерархическую коллекцию, как и `LEFT JOIN` в SQL. Дополнительные сведения см. в разделе [предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Группирование данных (Group By)  
 Можно добавить предложение `Group By`, чтобы сгруппировать элементы в результатах запроса в соответствии с одним или несколькими полями элементов. Например, следующий код группирует учащихся по классу year.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Если запустить этот код с помощью списка учащихся, созданных в [инструкции по созданию списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), выходные данные инструкции `For Each` будут:  
  
 Год: младшие  
  
 Туккер, Майкл  
  
 Гарсиа, Хьюго  
  
 Garcia, Debra  
  
 Туккер, Лэнс  
  
 Год: старший  
  
 Омелченко, Светлана  
  
 Осада, Мичико  
  
 Фахури, Фэди  
  
 Фенг, Ханинг  
  
 Адамс, Терри  
  
 Year: свежая  
  
 Мортенсен, Свен  
  
 Гарсиа, Сезар  
  
 Вариант, показанный в следующем коде, упорядочивает класс years, а затем упорядочивает учащихся в каждом году по фамилии.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Дополнительные сведения о `Group By`см. в разделе [предложение GROUP BY](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>См. также:

- <xref:System.Collections.Generic.IEnumerable%601>
- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
