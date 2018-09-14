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
ms.openlocfilehash: f1084ffcf0b5330185a44eda8721ef2a03413602
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2018
ms.locfileid: "45592001"
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Отношения типов в операциях запроса (Visual Basic)
Переменные, используемые в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] запроса операции являются строго типизированными и должны быть совместимы друг с другом. Строгая типизация используется в источнике данных, в самом запросе и при выполнении запроса. На следующем рисунке показаны термины, используемые для описания [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса. Дополнительные сведения о частях запроса см. в разделе [основные операции запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Запрос символического кода с маркированными элементами. ](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Части запроса LINQ  
  
 Тип переменной диапазона в запросе должен быть совместим с типом элементов в источнике данных. Тип переменной запроса должен быть совместим с элемент последовательности, определенный в `Select` предложение. Наконец, тип элементов последовательности также должен быть совместим с типом переменной цикла, который используется в `For Each` инструкции, выполняющей запрос. Строгая типизация упрощает идентификацию ошибок типов во время компиляции.  
  
 Visual Basic делает строгую типизацию удобной путем реализации вывод локального типа, также известный как *неявное типизирование*. В предыдущем примере используется функция, что вы увидите применяется [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] примеров и документации. В Visual Basic, вывод локального типа выполняется путем с помощью `Dim` инструкцию без `As` предложение. В следующем примере `city` строго типизируется как строка.  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  Вывод локального типа работает только тогда, когда `Option Infer` присваивается `On`. Дополнительные сведения см. в разделе [оператор Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Тем не менее даже если использовать вывод локального типа в запросе, отношение типов присутствуют среди переменных в источнике данных, переменная запроса и цикл выполнения запроса. Это удобно иметь базовое представление о связи типов в том случае, если вы создаете [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов или работы с примерами и примеры кода в документации.  
  
 Может потребоваться указать явный тип для переменной диапазона, который не соответствует типу, возвращаемому из источника данных. Можно указать тип переменной диапазона с помощью `As` предложение. Тем не менее, это приводит к ошибке при преобразовании [сужающее преобразование](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и `Option Strict` присваивается `On`. Поэтому рекомендуется выполнить преобразование значения, полученные из источника данных. Можно преобразовать значения из источника данных для переменной типа явные диапазона с помощью <xref:System.Linq.Enumerable.Cast%2A> метод. Можно также выполнить приведение значений, выбранных в `Select` предложение для явному типу, отличается от типа переменной диапазона. В следующем коде показаны следующие моменты.  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Запросы, которые возвращают целые элементы из источника данных  
 В следующем примере показан [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] операция, которая возвращает последовательность элементов, выбранных из источника данных запроса. Источник, `names`, содержит массив строк, и выходных данных запроса является последовательность, содержащая строки, начинающиеся на букву M.  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Это эквивалентно следующему коду, но намного короче и проще написать. Зависимость от вывод локального типа в запросах является предпочтительным в Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 Следующие отношения существуют в обоих приведенных выше примерах кода ли типы определяются явно или неявно.  
  
1.  Тип элементов в источнике данных, `names`, — это тип переменной диапазона, `name`, в запросе.  
  
2.  Тип объекта, который выбран, `name`, определяет тип переменной запроса, `mNames`. Здесь `name` представляет собой строку, поэтому переменная запроса является IEnumerable (Of String) в Visual Basic.  
  
3.  Запрос, определенный в `mNames` выполняется в `For Each` цикла. Цикл выполняет итерацию в результате выполнения запроса. Так как `mNames`, при выполнении будут возвращать последовательность строк, переменная итерации в цикле, `nm`, также является строкой.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Запросы, возвращающие одно поле из выбранных элементов  
 В следующем примере показан [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] операция, которая возвращает последовательность, содержащую только одну часть каждого элемента, выбранного из источника данных запроса. Запрос принимает коллекцию `Customer` объектов в качестве источника данных и только проекты `Name` свойство в результат. Поскольку имя клиента является строкой, запрос создает последовательность строк в качестве выходных данных.  
  
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
  
 Связи между переменными похожи на те, в более простом примере.  
  
1.  Тип элементов в источнике данных, `customers`, — это тип переменной диапазона, `cust`, в запросе. В этом примере, что тип `Customer`.  
  
2.  `Select` Инструкцией `Name` свойства каждого `Customer` объекта, а не всего объекта. Так как `Name` представляет собой строку, переменная запроса `custNames`, снова будет IEnumerable (Of String), не `Customer`.  
  
3.  Так как `custNames` представляет последовательность строк, `For Each` переменная итерации цикла, `custName`, должно быть строкой.  
  
 Без вывод локального типа предыдущего примера будет более громоздким, для записи и чтобы понять, как показано в следующем примере.  
  
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
  
## <a name="queries-that-require-anonymous-types"></a>Запросы, требующие анонимные типы  
 В следующем примере более сложная ситуация. В предыдущем примере был неудобен для указания типов для всех переменных явно. В этом примере это невозможно. Вместо выбора всей `Customer` элементы из источника данных или одно поле из каждого элемента `Select` предложение в этом запросе возвращает два свойства исходного `Customer` объект: `Name` и `City`. В ответ на `Select` предложение, компилятор определяет анонимный тип, содержащий эти два свойства. Результат выполнения `nameCityQuery` в `For Each` цикла — это коллекция экземпляров нового анонимного типа. Поскольку анонимный тип не имеет имени, нельзя указать тип `nameCityQuery` или `custInfo` явным образом. То есть с анонимного типа, у вас отсутствует имя типа для использования вместо `String` в `IEnumerable(Of String)`. Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
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
  
 Несмотря на то, что не поддерживается для указания типов для всех переменных в предыдущем примере, связи не изменяются.  
  
1.  Тип элементов в источнике данных снова станет тип переменной диапазона в запросе. В этом примере `cust` является экземпляром класса `Customer`.  
  
2.  Так как `Select` оператор создает анонимный тип, переменная запроса `nameCityQuery`, неявно типизируется как анонимный тип. Анонимный тип не имеет имени и не может быть указан явно.  
  
3.  Тип переменной итерации в `For Each` цикл имеет анонимный тип, созданный на шаге 2. Так как тип не имеет имени, неявно необходимо определить тип переменной итерации цикла.  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/index.md)
