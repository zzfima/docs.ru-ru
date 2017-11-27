---
title: "Отношения типов в операциях запроса (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 1b93188475dd2bb00aea044ff178028eb87e00d4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Отношения типов в операциях запроса (Visual Basic)
Переменные, используемые в [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] запроса операции являются строго типизированными и должны быть совместимы друг с другом. Строгая типизация используется в источнике данных, в самом запросе и при выполнении запроса. На следующем рисунке показаны термины, используемые для описания [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запроса. Дополнительные сведения о частях запроса см. в разделе [основные операции запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Запрос символического кода с маркированными элементами. ] (../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Части запроса LINQ  
  
 Тип переменной диапазона в запросе должен быть совместим с типом элементов в источнике данных. Тип переменной запроса должен быть совместим с последовательностью элемента, определенной в `Select` предложения. Наконец, тип элементов последовательности также должен быть совместим с типом переменной цикла, которая используется в `For Each` инструкцию, которая выполняет запрос. Строгая типизация упрощает идентификацию ошибок типов во время компиляции.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]делает строгую типизацию удобной за счет реализации локального определения типа, также известный как *неявное типизирование*. Функция используется в предыдущем примере, что вы увидите применяется [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] примеров и документации. В Visual Basic, определение локального типа осуществляется просто с помощью `Dim` оператор без `As` предложения. В следующем примере `city` , строго типизируется как строка.  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  Вывод локального типа работает только тогда, когда `Option Infer` равно `On`. Дополнительные сведения см. в разделе [Option Infer-оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Тем не менее даже если локальное определение типа используется в запросе, отношение типов присутствуют между переменными в источнике данных, переменная запроса и цикла выполнения запроса. Полезно иметь базовое понимание отношений типов при создании [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] запросов или работы с примерами кода в документации.  
  
 Необходимо указать явный тип для переменной диапазона, который не соответствует типу, возвращенные из источника данных. Можно указать тип переменной диапазона с помощью `As` предложения. Тем не менее, это приводит к ошибке, если преобразование прошло [сужающее преобразование](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и `Option Strict` равно `On`. Таким образом рекомендуется выполнить преобразование в значения, полученные из источника данных. Можно преобразовать значения из источника данных типа переменной диапазона явной, используя <xref:System.Linq.Enumerable.Cast%2A> метод. Также можно приводить значения, выбранные в `Select` предложения явный тип, отличный от типа переменной диапазона. В следующем коде показаны эти точки.  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Запросы, которые возвращают целые элементы из источника данных  
 В следующем примере показан [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] операция, которая возвращает последовательность элементов, выбранных из источника данных запроса. Источник, `names`, содержит массив строк, а результат запроса представляет собой последовательность, содержащую строки, которые начинаются на букву M.  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Это эквивалентно следующему коду, но намного короче и проще написать. Зависимость от локального определения типов в запросах является предпочтительным для Visual Basic.  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 Следующие отношения существуют в обоих приведенных выше примерах кода ли типы определяются явно или неявно.  
  
1.  Тип элементов в источнике данных `names`, тип переменной диапазона `name`, в запросе.  
  
2.  Тип объекта, который выбран, `name`, определяет тип переменной запроса `mNames`. Здесь `name` представляет собой строку, поэтому переменная запроса является IEnumerable (Of String) в Visual Basic.  
  
3.  Запрос, определенный в `mNames` выполняется в `For Each` цикла. Цикл выполняет итерацию в результате выполнения запроса. Поскольку `mNames`, при ее выполнении вернет последовательность строк, переменная итерации цикла `nm`, также является строкой.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Запросы, возвращающие одно поле из выбранных элементов  
 В следующем примере показан [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] операция, которая возвращает последовательность, содержащую только одну часть каждого элемента, выбранного из источника данных запроса. Запрос принимает коллекцию `Customer` объектов в качестве источника данных и только проекты `Name` свойства в результате. Поскольку имя клиента является строкой, запрос создает последовательность строк в качестве выходных данных.  
  
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
  
 Связи между переменными аналогичны простой пример.  
  
1.  Тип элементов в источнике данных `customers`, тип переменной диапазона `cust`, в запросе. В этом примере этот тип является `Customer`.  
  
2.  `Select` Инструкция возвращает `Name` каждого экземпляра `Customer` объект, а не весь объект. Поскольку `Name` является строкой, переменной запроса `custNames`, снова будет IEnumerable (Of String), не `Customer`.  
  
3.  Поскольку `custNames` представляет собой последовательность строк, `For Each` переменная итерации цикла, `custName`, должно быть строкой.  
  
 Без локального определения типов предыдущий пример может занимать более громоздким для записи и для понимания, как показано в следующем примере.  
  
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
 В следующем примере показано более сложная ситуация. В предыдущем примере был неудобен для указания типов для всех переменных явным образом. В этом примере это невозможно. Вместо выбора всей `Customer` элементы из источника данных или одного поля из каждого элемента `Select` предложение в этом запросе возвращает два свойства исходного `Customer` объект: `Name` и `City`. В ответ на `Select` предложение, компилятор определяет анонимный тип, содержащий эти два свойства. В результате выполнения `nameCityQuery` в `For Each` цикла — это коллекция экземпляров нового анонимного типа. Так как анонимный тип не имеет имени, нельзя указать тип `nameCityQuery` или `custInfo` явным образом. То есть, анонимный тип, у вас есть отсутствует имя типа для использования вместо `String` в `IEnumerable(Of String)`. Дополнительные сведения см. в статье [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
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
  
1.  Тип элементов в источнике данных снова — тип переменной диапазона в запросе. В этом примере `cust` является экземпляром класса `Customer`.  
  
2.  Поскольку `Select` оператор создает анонимный тип, переменная запроса `nameCityQuery`, неявно типизируется как анонимный тип. Анонимный тип не имеет имени и поэтому не может быть указана явно.  
  
3.  Тип переменной итерации в `For Each` цикла является анонимным типом, созданным на шаге 2. Так как тип не имеет имени, неявно необходимо определить тип переменной итерации цикла.  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md) (Знакомство с LINQ в Visual Basic)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)
