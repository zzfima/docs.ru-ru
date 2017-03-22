---
title: "Связи между типами в операциях запроса (Visual Basic) | Документы Microsoft"
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
- variable relationships [LINQ in Visual Basic]
- type information inferred [LINQ in Visual Basic]
- type relationships [LINQ in Visual Basic]
- queries [LINQ in Visual Basic], type relationships
- data sources [LINQ in Visual Basic], type relationships
- LINQ [Visual Basic], type relationships
- inferring type information [LINQ in Visual Basic]
- relationships [LINQ in Visual Basic]
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
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
ms.openlocfilehash: a966b69feca7a7021cafbccb7971913ea781c479
ms.lasthandoff: 03/13/2017

---
# <a name="type-relationships-in-query-operations-visual-basic"></a>Отношения типов в операциях запроса (Visual Basic)
Переменные, используемые в [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] запрос операции являются строго типизированными и должны быть совместимы друг с другом. Строгая типизация используется в источнике данных, в самом запросе и при выполнении запроса. На следующем рисунке показаны термины, используемые для описания [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запроса. Дополнительные сведения о частях запроса см. в разделе [основные операции запроса (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md).  
  
 ![Запрос символического кода с маркированными элементами.](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
Части запроса LINQ  
  
 Тип переменной диапазона в запросе должен быть совместим с типом элементов в источнике данных. Тип переменной запроса должен быть совместим с последовательностью элемента, определенной в `Select` предложения. Наконец, тип элементов последовательности также должен быть совместим с типом переменной цикла, которая используется в `For Each` инструкцию, которая выполняет запрос. Строгая типизация упрощает идентификацию ошибок типов во время компиляции.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]делает строгую типизацию удобной за счет реализации локального определения типа, также известный как *неявное типизирование*. В предыдущем примере используется функция, что вы увидите применяется [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] примеров и документации. В Visual Basic, определение локального типа осуществляется просто с помощью `Dim` оператор без `As` предложения. В следующем примере `city` строго типизирован в качестве строки.  
  
 [!code-vb[VbLINQTypeRels&#1;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  Вывод локального типа работает только тогда, когда `Option Infer` равен `On`. Дополнительные сведения см. в разделе [Option Infer оператор](../../../../visual-basic/language-reference/statements/option-infer-statement.md).  
  
 Тем не менее даже если использование локального определения типов в запросе, отношение типов присутствуют между переменными в источнике данных, переменной запроса и цикл выполнения запроса. Полезно иметь базовое понимание этих связей типа при написании [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] запросов или работе с примерами кода в документации.  
  
 Возможно, потребуется указать явный тип переменной диапазона, который не соответствует типу, возвращенные из источника данных. Тип переменной диапазона можно указать с помощью `As` предложения. Однако это приведет к ошибке, если преобразование является [сужающее преобразование](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) и `Option Strict` равен `On`. Таким образом рекомендуется выполнить преобразование на значения, полученные из источника данных. Можно преобразовать значения из источника данных тип переменной диапазона явные с помощью <xref:System.Linq.Enumerable.Cast%2A>метод.</xref:System.Linq.Enumerable.Cast%2A> Также можно приводить значения, выбранные в `Select` предложение явный тип, отличный от типа переменной диапазона. Эти варианты демонстрируются в следующем коде.  
  
 [!code-vb[VbLINQTypeRels&#4;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## <a name="queries-that-return-entire-elements-of-the-source-data"></a>Запросы, которые возвращают целые элементы из источника данных  
 В следующем примере показан [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] операцию, которая возвращает последовательность элементов, выбранных из источника данных запроса. Источник, `names`, содержит массив строк, а результат запроса представляет собой последовательность, содержащую строки, которые начинаются с буквы M.  
  
 [!code-vb[VbLINQTypeRels&#2;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 Это эквивалентно следующему коду, но намного короче и проще написать. Зависимость от локального определения типов в запросах является предпочтительным для Visual Basic.  
  
 [!code-vb[VbLINQTypeRels&#3;](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 Следующие отношения существуют в обоих предыдущих примерах кода ли типы определяются явно или неявно.  
  
1.  Тип элементов в источнике данных `names`, тип переменной диапазона `name`, в запросе.  
  
2.  Тип объекта, который выбран, `name`, определяет тип переменной запроса `mNames`. Здесь `name` является строкой, поэтому переменная запроса является IEnumerable (Of String) в Visual Basic.  
  
3.  Запрос, определенный в `mNames` выполняется в `For Each` цикла. Цикл выполняет итерацию результата выполнения запроса. Поскольку `mNames`, при выполнении вернет последовательность строк, переменная итерации цикла `nm`, также является строкой.  
  
## <a name="queries-that-return-one-field-from-selected-elements"></a>Запросы, возвращающие одно поле из выбранных элементов  
 В следующем примере показан [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] операцию, которая возвращает последовательность, содержащую только одну часть каждого элемента, выбранного из источника данных запроса. Запрос получает коллекцию `Customer` объектов в качестве источника данных и только проекты `Name` свойства в результате. Поскольку имя заказчика является строкой, запрос создает последовательность строк в качестве выходных данных.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 Отношения между переменными аналогичны простой пример.  
  
1.  Тип элементов в источнике данных `customers`, тип переменной диапазона `cust`, в запросе. В этом примере этот тип является `Customer`.  
  
2.  `Select` Инструкция возвращает `Name` каждого экземпляра `Customer` объект, а не весь объект. Поскольку `Name` является строкой, переменная запроса `custNames`, снова будет IEnumerable (Of String), не `Customer`.  
  
3.  Поскольку `custNames` представляет собой последовательность строк, `For Each` переменная итерации цикла, `custName`, должно быть строкой.  
  
 Без локального определения типа предыдущий пример бы более громоздким для записи и понимания, как показано в следующем примере.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## <a name="queries-that-require-anonymous-types"></a>Запросы, требующие анонимные типы  
 В следующем примере показано более сложная ситуация. В предыдущем примере был неудобен явно указать типы для всех переменных. В данном примере это невозможно. Вместо выбора всего `Customer` элементы из источника данных или одного поля из каждого элемента `Select` предложения в этом запросе возвращает два свойства из исходного `Customer` объект: `Name` и `City`. В ответ на `Select` предложение, компилятор определяет анонимный тип, содержащий эти два свойства. В результате выполнения `nameCityQuery` в `For Each` цикла — это коллекция экземпляров нового анонимного типа. Поскольку анонимный тип не имеет имени, нельзя указать тип `nameCityQuery` или `custInfo` явным образом. То есть, анонимный тип, у вас есть отсутствует имя типа для использования вместо `String` в `IEnumerable(Of String)`. Дополнительные сведения см. в разделе [анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md).  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Несмотря на то, что не поддерживается для указания типов для всех переменных в предыдущем примере, связи не изменяются.  
  
1.  Тип элементов в источнике данных снова является типом переменной диапазона в запросе. В этом примере `cust` является экземпляром класса `Customer`.  
  
2.  Поскольку `Select` инструкция создает анонимный тип, переменная запроса `nameCityQuery`, неявно типизируется как анонимный тип. Анонимный тип не имеет имени и поэтому не может быть указан явно.  
  
3.  Тип переменной итерации в `For Each` цикл имеет анонимный тип, созданный на шаге 2. Так как тип не имеет имени, тип переменной итерации цикла следует определять неявно.  
  
## <a name="see-also"></a>См. также  
 [Приступая к работе с LINQ в Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Введение в LINQ в Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Запросы](../../../../visual-basic/language-reference/queries/queries.md)
