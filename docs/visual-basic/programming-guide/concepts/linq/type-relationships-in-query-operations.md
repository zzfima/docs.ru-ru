---
title: Отношения типов в операциях запроса (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
ms.openlocfilehash: 4851d0a74de38f0fb6b6deee34cf7b3e66eb11b4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937480"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Отношения типов в операциях запроса (Visual Basic)
Переменные, используемые [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] в операциях запроса, строго типизированы и должны быть совместимы друг с другом. Строгая типизация используется в источнике данных, в самом запросе и в выполнении запроса. На следующем рисунке показаны термины, используемые для описания [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса. Дополнительные сведения о частях запроса см. в разделе [основные операции запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Снимок экрана, показывающий запрос на псевдокод с выделенными элементами.](./media/type-relationships-in-query-operations/linq-query-description-terms.png)  
  
 Тип переменной диапазона в запросе должен быть совместим с типом элементов в источнике данных. Тип переменной запроса должен быть совместим с элементом последовательности, определенным в `Select` предложении. Наконец, тип элементов последовательности также должен быть совместим с типом управляющей переменной цикла, которая используется в `For Each` инструкции, выполняющей запрос. Эта строгая типизация облегчает идентификацию ошибок типа во время компиляции.  
  
 Visual Basic обеспечивает строгую типизацию, реализуя вывод локального типа, также называемую *неявной типизацией*. Эта функция используется в предыдущем примере, и вы увидите, что она используется во всех [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] примерах и документации. В Visual Basic вывод локального типа выполняется просто с помощью `Dim` оператора `As` без предложения. В следующем примере `city` строго типизирован как строка.  
  
 [!code-vb[VbLINQTypeRels#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#1)]  
  
> [!NOTE]
> Локальное определение типа работает только в `Option Infer` `On`том случае, если параметр имеет значение. Дополнительные сведения см. в разделе [оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Однако даже если в запросе используется определение локального типа, то одни и те же связи типов существуют между переменными в источнике данных, переменной запроса и циклом выполнения запроса. При написании [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов или работе с образцами и примерами кода в документации полезно иметь базовое понимание этих отношений типов.  
  
 Может потребоваться указать явный тип для переменной диапазона, которая не соответствует типу, возвращаемому источником данных. Тип переменной диапазона можно указать с помощью `As` предложения. Однако это приводит к ошибке, если преобразование является [узким преобразованием](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и `Option Strict` имеет значение `On`. Поэтому рекомендуется выполнить преобразование для значений, полученных из источника данных. Можно преобразовать значения из источника данных в явный тип переменной диапазона с помощью <xref:System.Linq.Enumerable.Cast%2A> метода. Можно также привести значения, выбранные в `Select` предложении, к явному типу, отличному от типа переменной диапазона. Эти моменты показаны в следующем коде.  
  
 [!code-vb[VbLINQTypeRels#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#4)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Запросы, возвращающие все элементы исходных данных  
 В следующем примере показана [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] операция запроса, возвращающая последовательность элементов, выбранных из исходных данных. Источник, `names`, содержит массив строк, а выходные данные запроса представляют собой последовательность, содержащую строки, начинающиеся с буквы M.  
  
 [!code-vb[VbLINQTypeRels#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#2)]  
  
 Это эквивалентно следующему коду, но гораздо короче и проще в написании. Использовать определение локального типа в запросах является предпочтительным стилем в Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQTypeRels/VB/Class1.vb#3)]  
  
 В обоих приведенных выше примерах кода существуют следующие связи, независимо от того, определены типы как неявно или явно.  
  
1. Тип элементов в источнике данных, `names`, — это тип `name`переменной диапазона в запросе.  
  
2. Тип объекта, который выбран, `name`определяет тип `mNames`переменной запроса. Ниже `name` приведена строка, поэтому переменная запроса имеет значение IEnumerable (Of String) в Visual Basic.  
  
3. Запрос, определенный в `mNames` , выполняется `For Each` в цикле. Цикл выполняет итерацию результата выполнения запроса. Поскольку `mNames`при выполнении будет возвращена последовательность строк, переменная итерации цикла, `nm`также является строкой.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Запросы, возвращающие одно поле из выбранных элементов  
 В следующем примере показана [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] операция запроса, возвращающая последовательность, содержащую только одну часть каждого элемента, выбранного из источника данных. Запрос принимает коллекцию `Customer` объектов в качестве источника данных и проецирует `Name` только свойство в результате. Поскольку имя клиента является строкой, запрос создает последовательность строк в качестве выходных данных.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim custNames = From cust In customers   
                Where cust.City = "London"   
                Select cust.Name  
  
For Each custName In custNames  
    Console.WriteLine(custName)  
Next  
```  
  
 Связи между переменными, как и в более простом примере.  
  
1. Тип элементов в источнике данных, `customers`, — это тип `cust`переменной диапазона в запросе. В этом примере это тип `Customer`.  
  
2. Оператор возвращает свойство каждого`Customer` объекта, а не весь объект. `Name` `Select` Поскольку `Name` — это строка, `custNames`переменная запроса,, опять же, будет IEnumerable (of `Customer`String), а не.  
  
3. Поскольку `custNames` представляет последовательность строк `For Each` , переменная `custName`итерации цикла должна быть строкой.  
  
 Без локального определения типа предыдущий пример был бы более громоздким для написания и понимания, как показано в следующем примере.  
  
```vb  
' Method GetTable returns a table of Customer objects.  
 Dim customers As Table(Of Customer) = db.GetTable(Of Customer)()  
 Dim custNames As IEnumerable(Of String) =  
     From cust As Customer In customers   
     Where cust.City = "London"   
     Select cust.Name  
  
 For Each custName As String In custNames  
     Console.WriteLine(custName)  
 Next  
```  
  
## <a name="queries-that-require-anonymous-types"></a>Запросы, для которых требуются анонимные типы  
 В следующем примере показана более сложная ситуация. В предыдущем примере было неудобно указывать типы для всех переменных явным образом. В этом примере это невозможно. Вместо `Customer` выбора целых элементов из источника данных или одного поля из каждого элемента `Customer` `Select` предложение в этом запросе возвращает два свойства исходного объекта: `Name` и `City`. В ответ на `Select` предложение компилятор определяет анонимный тип, содержащий эти два свойства. Результатом выполнения `nameCityQuery` `For Each` в цикле является коллекция экземпляров нового анонимного типа. Так как анонимный тип не имеет имени, его нельзя указать `nameCityQuery` `custInfo` явным образом. То есть с анонимным типом у вас нет имени типа для использования `String` вместо в. `IEnumerable(Of String)` Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
```vb  
' Method GetTable returns a table of Customer objects.  
Dim customers = db.GetTable(Of Customer)()  
Dim nameCityQuery = From cust In customers   
                    Where cust.City = "London"   
                    Select cust.Name, cust.City  
  
For Each custInfo In nameCityQuery  
    Console.WriteLine(custInfo.Name)  
Next  
```  
  
 Хотя невозможно указать типы для всех переменных в предыдущем примере, связи остаются неизменными.  
  
1. Тип элементов в источнике данных опять является типом переменной диапазона в запросе. В этом примере `cust` — это `Customer`экземпляр.  
  
2. Так как `nameCityQuery`инструкция создает анонимный тип, переменная запроса, должна быть неявно типизирована как анонимный тип. `Select` Анонимный тип не имеет имени и поэтому не может быть указан явным образом.  
  
3. Тип переменной итерации в `For Each` цикле — это анонимный тип, созданный на шаге 2. Поскольку тип не имеет пригодного для использования имени, тип переменной итерации цикла должен быть определен неявно.  
  
## <a name="see-also"></a>См. также

- [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Запросы](../../../../visual-basic/language-reference/queries/index.md)
