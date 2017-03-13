---
title: "Основные операции запроса (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "источники данных [LINQ в Visual Basic]"
  - "Join - предложение [LINQ в Visual Basic]"
  - "упорядочение данных [LINQ в Visual Basic]"
  - "проекции [LINQ в Visual Basic]"
  - "LINQ [Visual Basic], операции запроса"
  - "Order By - предложение [LINQ в Visual Basic]"
  - "объединение данных [LINQ в Visual Basic]"
  - "запросы [LINQ в Visual Basic], основные операции"
  - "выбор данных [LINQ в Visual Basic]"
  - "Group By - предложение [LINQ в Visual Basic]"
  - "группировка данных [LINQ в Visual Basic]"
  - "Select - предложение [LINQ в Visual Basic]"
ms.assetid: 1146f6d0-fcb8-4f4d-8223-c9db52620d21
caps.latest.revision: 37
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 35
---
# Основные операции запроса (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Этот раздел содержит краткое описание выражений [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] Visual Basic и некоторых типичных операций, выполняемых в запросе.  Дополнительные сведения см. в следующих разделах:  
  
 [Знакомство с LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)  
  
 [Пошаговое руководство. Написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## Указание источника данных \(From\)  
 В первую очередь в запросе [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] нужно указать источник данных, к которому выполняется запрос.  Поэтому предложение `From` в запросе всегда поступает в первую очередь. Операторы запроса выделяют и формируют результат на основе типа источника.  
  
 [!code-vb[VbLINQBasicOps#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_1.vb)]  
  
 Предложение `From` указывает источник данных `customers` и *переменную диапазона* `cust`.  Переменная диапазона похожа на переменную итерации цикла, за исключением того, что в выражении запроса фактической итерации не происходит.  При выполнении запроса, обычно при помощи цикла `For Each`, переменная диапазона используется как ссылка на каждый последующий элемент в `customers`.  Поскольку компилятор может определить тип `cust`, нет необходимости указывать его в явном виде.  Примеры запросов, написанные с явным типизированием и без него, содержатся в разделе [Type Relationships in Query Operations \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Дополнительные сведения об использовании предложения `From` в Visual Basic см. в разделе [Предложение From](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## Фильтрация данных \(Where\)  
 Возможно, наиболее распространенной операцией запроса является применение фильтра в виде логического выражения.  Запрос в этом случае возвращает только те элементы, для которых выражение верно.  Для выполнения фильтрации используется предложение `Where`.  Фильтр определяет, какие элементы из источника данных необходимо включить в результирующую последовательность.  В следующем примере будут выбраны только заказчики, находящиеся в Лондоне.  
  
 [!code-vb[VbLINQBasicOps#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_2.vb)]  
  
 Для объединения выражений фильтра в предложении `Where` можно использовать логические операторы, такие как `And` и `Or`.  Например, для получения только заказчиков из Лондона с именем Devon используется следующий код:  
  
```vb#  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Для возвращения заказчиков из Лондона или Парижа используется следующий код.  
  
```vb#  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Дополнительные сведения об использовании предложения `Where` в Visual Basic см. в разделе [Предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## Упорядочение данных \(Order By\)  
 Часто бывает удобно упорядочить возвращенные данные в определенном порядке.  Предложение `Order By` сортирует элементы возвращаемой последовательности по одному или по нескольким полям.  Например, следующий запрос сортирует результаты на основе свойства `Name`.  Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке от А до Я.  
  
 [!code-vb[VbLINQBasicOps#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_3.vb)]  
  
 Чтобы упорядочить результаты в обратном порядке от Я до А используйте предложение `Order By...Descending`.  По умолчанию, когда не указано ни `Ascending`, ни `Descending`, используется `Ascending`.  
  
 Дополнительные сведения об использовании предложения `Order By` в Visual Basic см. в разделе [Предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## Выборка данных \(Select\)  
 Предложение `Select` определяет форму и содержимое возвращаемых элементов.  Например, можно указать будут ли результаты состоять из полных объектов `Customer`, только одного свойства `Customer`, подмножества свойств, сочетания свойств из различных источников данных или иметь некий новый результирующий вычисляемый тип.  Когда предложение `Select` создает что\-либо отличное от копии исходного элемента, операция называется *проекцией*.  
  
 Чтобы извлечь коллекцию, состоящую из полных объектов `Customer`, выберите саму переменную диапазона.  
  
 [!code-vb[VbLINQBasicOps#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_4.vb)]  
  
 Если экземпляр `Customer` является большим объектом и содержит много полей, а нужно извлечь только имя, тогда можно выбрать `cust.Name`, как показано в следующем примере.  Определение локального типа распознает и изменит тип результата с коллекции объектов `Customer` на коллекцию строк.  
  
 [!code-vb[VbLINQBasicOps#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_5.vb)]  
  
 Существует два варианта выбора нескольких полей из источника данных.  
  
-   В предложении `Select` укажите поля, которые требуется включить в результат.  Компилятор определит анонимный тип, имеющий эти поля как свойства.  Дополнительные сведения см. в разделе [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Поскольку возвращенные элементы в следующем примере являются экземплярами анонимного типа, невозможно сослаться на тип по имени из другого места в коде.  Имя типа, установленное компилятором, содержит знаки, которые являются недопустимыми в обычном коде Visual Basic.  В следующем примере элементы в коллекции, возвращенные запросом `londonCusts4`, являются экземплярами анонимного типа.  
  
     [!code-vb[VbLINQBasicOps#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_6.vb)]  
  
     \-или\-  
  
-   Определите именованный тип, содержащий конкретные поля, которые требуется включить в результат, создайте и инициализируйте экземпляры типа в предложении `Select`.  Этот вариант применим только в тех случаях, когда необходимо использовать отдельные результаты за пределами коллекции, в которой они возвращаются, или их нужно передавать в качестве параметров при вызове метода.  В следующем примере типом `londonCusts5` является IEnumerable\(Of NamePhone\).  
  
     [!code-vb[VbLINQBasicOps#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_7.vb)]  
  
     [!code-vb[VbLINQBasicOps#8](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_8.vb)]  
  
 Дополнительные сведения об использовании предложения `Select` в Visual Basic см. в разделе [Предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## Соединение данных \(Join и Group Join\)  
 В предложении `From` можно объединить несколько источников данных различными способами.  Например, следующий код использует два источника данных и неявно объединяет их свойства в результате.  Запрос выбирает студентов, фамилии которых начинаются с гласной буквы.  
  
 [!code-vb[VbLINQBasicOps#9](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_9.vb)]  
  
> [!NOTE]
>  Этот код можно выполнить со списком студентов, созданным в [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 Ключевое слово `Join` является эквивалентом `INNER JOIN` в SQL.  С его помощью объединяются две коллекции на основании совпадающих значений ключей между их элементами.  Запрос возвращает все или часть элементов коллекции с совпадающими значениями ключей.  Например, следующий код дублирует действие предыдущего неявного объединения.  
  
 [!code-vb[VbLINQBasicOps#10](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_10.vb)]  
  
 Предложение `Group Join` объединяет коллекции в одну иерархическую коллекцию аналогично предложению `LEFT JOIN` в SQL.  Дополнительные сведения см. в разделах [Предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [Предложение Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## Группировка данных \(Group By\)  
 Можно добавить предложение `Group By` для группировки элементов в результатах запроса по одному или нескольким полям элементов.  Например, следующий код группирует студентов по курсам.  
  
 [!code-vb[VbLINQBasicOps#11](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_11.vb)]  
  
 Если выполнить этот код, используя список студентов, созданный в разделе [How to: Create a List of Items](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), результатом оператора `For Each` будет следующее:  
  
 Третий год обучения  
  
 Куликов, Евгений  
  
 Орехов, Алексей  
  
 Орехова, Надежда  
  
 Гладких, Андрей  
  
 Четвертый год обучения  
  
 Омельченко, Светлана  
  
 Долгопятова, Зоя  
  
 Грачев, Николай  
  
 Ожогина, Инна  
  
 Шабалин, Александр  
  
 Первый год обучения  
  
 Голдин, Максим  
  
 Орехов, Владимир  
  
 Вариант, показанный в следующем коде, упорядочивает годы обучения, а затем — студентов каждого курса по фамилиям.  
  
 [!code-vb[VbLINQBasicOps#12](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/basic-query-operations_12.vb)]  
  
 Дополнительные сведения о `Group By` см. в разделе [Предложение Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## См. также  
 <xref:System.Collections.Generic.IEnumerable%601>   
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Basic LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)