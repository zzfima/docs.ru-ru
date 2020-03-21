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
ms.openlocfilehash: efae72c65ad67b4a1b157b67dcc4d4d65f31f77b
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266382"
---
# <a name="basic-query-operations-visual-basic"></a>Основные операции запроса (Visual Basic)
Эта тема содержит краткое введение в выражения Language-Integrated Query (LIN') в Visual Basic и некоторые типичные виды операций, выполняемых в запросе. Дополнительные сведения см. в следующих разделах:  
  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
  
 [Запросов](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Пошаговое руководство. Написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Определение источника данных (от)  
 В запросе LIN'а первым шагом является указание источника данных, который необходимо заказать. Таким образом, `From` пункт в запросе всегда на первом месте. Операторы запросов выбирают и формируют результат в зависимости от типа источника.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 В `From` пункте указывается источник `customers`данных и *переменная диапазона*. `cust` Переменная диапазона подобна переменной итерации цикла, за исключением того, что в выражении запроса не происходит фактической итерации. При выполнении запроса, часто с `For Each` помощью цикла, переменная диапазона служит `customers`отсылкой к каждому последующем элементу в . Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде. Для примеров запросов, написанных с [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)явным ввозами и без нее, см.  
  
 Для получения дополнительной информации `From` о том, как использовать положение в Visual Basic, см. [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md)  
  
## <a name="filtering-data-where"></a>Фильтрация данных (Где)  
 Вероятно, наиболее распространенной операцией запроса является применение фильтра в виде выражения Boolean. Затем запрос возвращает только те элементы, для которых выражение верно. Для `Where` выполнения фильтрации используется пункт. Фильтр определяет, какие элементы в источнике данных следует включить в результирующую последовательность. В следующем примере включены только те клиенты, у которых есть адрес в Лондоне.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Можно использовать логических `And` операторов, таких как `Or` `Where` и комбинировать выражения фильтра в оговорке. Например, чтобы вернуть только тех клиентов, которые из Лондона и чье имя Девон, используйте следующий код:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"
```  
  
 Чтобы вернуть клиентов из Лондона или Парижа, используйте следующий код:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"
```  
  
 Для получения дополнительной информации `Where` о том, как использовать положение в Visual Basic, см. [Where Clause](../../../../visual-basic/language-reference/queries/where-clause.md)  
  
## <a name="ordering-data-order-by"></a>Заказ данных (Заказ)  
 Часто удобно сортировать возвращенные данные в определенный заказ. Это `Order By` положение приведет к тому, что элементы в возвращенной последовательности будут сортироваться по определенному полю или полям. Например, следующий запрос сортирует `Name` результаты на основе свойства. Поскольку `Name` строка является строкой, возвращенные данные будут отсортированы в алфавитном порядке, от А до Я.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`. По `Ascending` умолчанию, `Ascending` `Descending` когда ни один и не указан.  
  
 Для получения дополнительной информации `Order By` о том, как использовать положение в Visual Basic, см. [Order By Clause](../../../../visual-basic/language-reference/queries/order-by-clause.md)  
  
## <a name="selecting-data-select"></a>Выбор данных (выбрать)  
 В `Select` этом положении оговаривается форма и содержание возвращенных элементов. Например, можно указать, будут ли `Customer` результаты `Customer` состоять из полных объектов, только одного свойства, подмноза свойств, комбинации свойств из различных источников данных или какого-либо нового типа результатов, основанного на вычислениях. Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.  
  
 Чтобы получить коллекцию, состоящую из полных `Customer` объектов, выберите сам упор диапазона:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Если `Customer` экземпляр — это большой объект, который имеет много полей, и все, что вы хотите получить, это имя, вы можете выбрать, `cust.Name`как показано в следующем примере. Вывод локального типа признает, что это изменяет `Customer` тип результата из коллекции объектов в коллекцию строк.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Чтобы выбрать несколько полей из источника данных, у вас есть два варианта:  
  
- В `Select` пункте укажите поля, которые вы хотите включить в результат. Компилятор определит анонимный тип, который имеет эти поля в качестве своих свойств. Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Поскольку возвращенные элементы в следующем примере являются экземплярами анонимного типа, вы не можете ссылаться на тип по имени в другом месте кода. Имя, обозначенное компилятором для типа, содержит символы, которые не действительны в обычном базовом коде Visual. В следующем примере элементы в коллекции, которые `londonCusts4` возвращаются запросом, являются экземплярами анонимного типа  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     -или-  
  
- Определите тип имени, содержащий определенные поля, которые необходимо включить в результат, и создайте и инициализировать экземпляры типа в предложении. `Select` Используйте эту опцию только в том случае, если вам необходимо использовать отдельные результаты за пределами коллекции, в которые они возвращаются, или если вы должны передать их в качестве параметров в вызовах метода. Тип `londonCusts5` в следующем примере IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Для получения дополнительной информации `Select` о том, как использовать положение в Visual Basic, см. [Select Clause](../../../../visual-basic/language-reference/queries/select-clause.md)  
  
## <a name="joining-data-join-and-group-join"></a>Присоединение к данным (присоединение и присоединение к группе)  
 Можно объединить несколько источников `From` данных в пункте несколькими способами. Например, в следующем коде используются два источника данных и неявно сочетается свойства из обоих. Запрос выбирает студентов, фамилии которых начинаются с гласной.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
> Вы можете запустить этот код со списком студентов, созданным в [Как: Создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Ключевое `Join` слово эквивалентно `INNER JOIN` в S'L. Он сочетает в себе две коллекции на основе сопоставления ключевых значений между элементами в двух коллекциях. Запрос возвращает все или часть элементов коллекции, которые соответствуют ключевым значениям. Например, следующий код дублирует действие предыдущего неявного соединения.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join`объединяет коллекции в единую иерархическую `LEFT JOIN` коллекцию, как и в S'L. Для получения дополнительной информации [Group Join Clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) [см.](../../../../visual-basic/language-reference/queries/join-clause.md)  
  
## <a name="grouping-data-group-by"></a>Данные по группировке (группа by)  
 Можно добавить `Group By` пункт для группы элементов в результате запроса в соответствии с одним или несколько полями элементов. Например, следующий код группирует студентов по годам занятий.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Если вы запустите этот код, используя список студентов, созданный в `For Each` [Как: Создать список элементов,](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)выход из оператора:  
  
 Год: Младший  
  
 Такер, Майкл  
  
 Гарсия, Хьюго  
  
 Гарсия, Дебра  
  
 Такер, Лэнс  
  
 Год: Старший  
  
 Омельченко, Светлана  
  
 Осада, Митико  
  
 Факхури, Фади  
  
 Фэн, Ханайинг  
  
 Адамс, Терри  
  
 Год: Первокурсник  
  
 Мортенсен, Свен  
  
 Гарсия, Сезар  
  
 Вариации, показанные в следующем коде, заказируют классные годы, а затем заказы студентов в течение каждого года по фамилии.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Для получения `Group By`дополнительной информации о , см. [Group By Clause](../../../../visual-basic/language-reference/queries/group-by-clause.md)  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Collections.Generic.IEnumerable%601>
- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Запросов](../../../../visual-basic/language-reference/queries/index.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
