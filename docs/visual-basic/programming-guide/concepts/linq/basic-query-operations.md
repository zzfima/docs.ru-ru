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
ms.openlocfilehash: ed5ed56366911c3676c4413711207ac0a8f85765
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61925652"
---
# <a name="basic-query-operations-visual-basic"></a>Основные операции запроса (Visual Basic)
Этот раздел содержит краткое введение в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] выражений в Visual Basic и некоторых типичных операций, выполняемых в запросе. Дополнительные сведения см. в следующих разделах:  
  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
  
 [Запросы](../../../../visual-basic/language-reference/queries/index.md)  
  
 [Пошаговое руководство: Написание запросов в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/walkthrough-writing-queries.md)  
  
## <a name="specifying-the-data-source-from"></a>Указание источника данных (от)  
 В [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса, первым шагом является указание источника данных, необходимо выполнить запрос. Таким образом `From` предложения в запросе всегда располагается первым. Операторы запросов, выберите и формирование результатов в зависимости от типа источника.  
  
 [!code-vb[VbLINQBasicOps#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#1)]  
  
 `From` Предложение указывает источник данных, `customers`и *переменная диапазона*, `cust`. Переменная диапазона находится как переменная итерации цикла, за исключением того, что в выражении запроса не происходит фактической итерации. При выполнении запроса, обычно с помощью `For Each` цикла, переменная диапазона используется как ссылка на каждый последующий элемент в `customers`. Так как компилятор может определить тип `cust`, нет необходимости указывать его в явном виде. Примеры запросов, написанных с использованием и без явную типизацию, см. в разделе [связи типов в операциях запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
 Дополнительные сведения об использовании `From` предложение в Visual Basic, см. в разделе [предложение From](../../../../visual-basic/language-reference/queries/from-clause.md).  
  
## <a name="filtering-data-where"></a>Фильтрация данных (где)  
 Возможно, наиболее распространенной операцией запроса является применение фильтра в форме логического выражения. Запрос возвращает только те элементы, для которых выражение является истинным. Объект `Where` предложение используется для выполнения фильтрации. Фильтр указывает элементы в источнике данных для включения в результирующей последовательности. В следующем примере включаются только клиенты, находящиеся в Лондоне.  
  
 [!code-vb[VbLINQBasicOps#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#2)]  
  
 Можно использовать логические операторы, такие как `And` и `Or` для объединения критериев фильтров в `Where` предложение. Например для получения только заказчиков из Лондона с именем Devon, используйте следующий код:  
  
```vb  
Where cust.City = "London" And cust.Name = "Devon"   
```  
  
 Для получения заказчиков из Лондона или Парижа, используйте следующий код:  
  
```vb  
Where cust.City = "London" Or cust.City = "Paris"   
```  
  
 Дополнительные сведения об использовании `Where` предложение в Visual Basic, см. в разделе [предложение Where](../../../../visual-basic/language-reference/queries/where-clause.md).  
  
## <a name="ordering-data-order-by"></a>Упорядочение данных (Order By)  
 Часто бывает удобно упорядочить возвращенные данные в определенном порядке. `Order By` Предложение сортирует элементы возвращаемой последовательности по по указанному полю или полям. Например, следующий запрос сортирует результаты на основе `Name` свойство. Поскольку `Name` является строкой, возвращаемые данные будут отсортированы в алфавитном порядке, от A до Z.  
  
 [!code-vb[VbLINQBasicOps#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#3)]  
  
 Для упорядочения результатов в обратном порядке от Я до А используется предложение `Order By...Descending`. По умолчанию используется `Ascending` когда ни одно `Ascending` , ни `Descending` указан.  
  
 Дополнительные сведения об использовании `Order By` предложение в Visual Basic, см. в разделе [предложение Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md).  
  
## <a name="selecting-data-select"></a>Выбор данных (Select)  
 `Select` Предложение определяет форму и содержимое возвращаемых элементов. Например, можно указать, будут ли результаты состоять из полных `Customer` объектов, лишь один `Customer` свойство, подмножество свойств, сочетания свойств из различных источников данных или некоторых новых типов в зависимости от вычислений. Когда предложение `Select` создает что-либо отличное от копии исходного элемента, операция называется *проекцией*.  
  
 Чтобы извлечь коллекцию, состоящую из полных `Customer` объектов, выберите саму переменную диапазона:  
  
 [!code-vb[VbLINQBasicOps#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#4)]  
  
 Если `Customer` экземпляр больших объектов, содержит много полей, и все, что вы хотите получить — это имя, можно выбрать `cust.Name`, как показано в следующем примере. Вывод локального типа распознает и изменит тип результата из коллекции `Customer` объектов в коллекции строк.  
  
 [!code-vb[VbLINQBasicOps#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#5)]  
  
 Чтобы выбрать несколько полей из источника данных, у вас есть два варианта:  
  
- В `Select` предложение, укажите поля, необходимо включить в результат. Компилятор определит анонимный тип, имеющий эти поля, как его свойства. Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
     Так как в следующем примере возвращенные элементы являются экземплярами анонимного типа, нельзя ссылаться на тип по имени в другом месте в коде. Имя компилятором для типа содержит символы, недопустимые в обычном коде Visual Basic. В следующем примере элементы в коллекции, который возвращается запросом в `londonCusts4` экземпляров анонимного типа  
  
     [!code-vb[VbLINQBasicOps#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#6)]  
  
     -или-  
  
- Определите именованный тип, содержащий конкретные поля, которые вы хотите включить в результат и создание и инициализация экземпляров типа в `Select` предложение. Используйте этот параметр только в том случае, если необходимо использовать отдельные результаты за пределами коллекции, в котором они будут возвращены, или в том случае, если необходимо передать их в качестве параметров в вызовах методов. Тип `londonCusts5` в следующем примере является IEnumerable (Of NamePhone).  
  
     [!code-vb[VbLINQBasicOps#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#7)]  
  
     [!code-vb[VbLINQBasicOps#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#8)]  
  
 Дополнительные сведения об использовании `Select` предложение в Visual Basic, см. в разделе [предложение Select](../../../../visual-basic/language-reference/queries/select-clause.md).  
  
## <a name="joining-data-join-and-group-join"></a>Данные соединения (Join и групповое соединение)  
 Вы можете объединить несколько источников данных в `From` предложение несколькими способами. Например следующий код использует два источника данных и неявно объединяет свойства из каждого из них в результат. Запрос выбирает студентов, чьи фамилии начинаются с гласных.  
  
 [!code-vb[VbLINQBasicOps#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#9)]  
  
> [!NOTE]
>  Этот код можно выполнить с помощью списка студентов, созданный в [как: Создание списка элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md).  
  
 `Join` Ключевое слово эквивалентно `INNER JOIN` в SQL. Он объединяет две коллекции, на основе сопоставления значений ключа между элементами двух коллекций. Запрос возвращает все или часть элементов коллекции с совпадающими значениями ключей. Например следующий код дублирует действие предыдущего неявного объединения.  
  
 [!code-vb[VbLINQBasicOps#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#10)]  
  
 `Group Join` объединяет коллекции в одну иерархическую коллекцию, так же, как `LEFT JOIN` в SQL. Дополнительные сведения см. в разделе [предложение Join](../../../../visual-basic/language-reference/queries/join-clause.md) и [предложение Join группы](../../../../visual-basic/language-reference/queries/group-join-clause.md).  
  
## <a name="grouping-data-group-by"></a>Группирование данных (Группировать по)  
 Вы можете добавить `Group By` предложение для группирования элементов в результатах запроса, в соответствии с одного или нескольких полей элементов. Например следующий код группирует студентов по курсам.  
  
 [!code-vb[VbLINQBasicOps#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#11)]  
  
 Если вы запустите этот код, используя список учащихся, созданные в [как: Создать список элементов](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md), выходные данные `For Each` инструкция является:  
  
 Год: "Junior"  
  
 Такер, Майкл  
  
 Орехов, Алексей  
  
 Орехов, Дебра  
  
 Гладких, Андрей  
  
 Год: Старший  
  
 Omelchenko Svetlana  
  
 Osada Michiko  
  
 Грачев, Николай  
  
 Ожогина, Инна  
  
 Александр Шабалин  
  
 Год: Обучения  
  
 Mortensen Свен  
  
 Орехов, Владимир  
  
 Вариант, показанный в следующем коде упорядочивает класс лет и упорядочивает учащихся в течение каждого года по фамилии.  
  
 [!code-vb[VbLINQBasicOps#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQBasicOps/VB/Class1.vb#12)]  
  
 Дополнительные сведения о `Group By`, см. в разделе [предложение Group](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Collections.Generic.IEnumerable%601>
- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
- [Общие сведения о стандартных операторах запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
