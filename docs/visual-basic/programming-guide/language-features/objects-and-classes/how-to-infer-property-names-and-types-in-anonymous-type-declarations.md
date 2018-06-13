---
title: Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 80127c05d56162397cfa421122ddd9698750b376
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653316"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a>Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов (Visual Basic)
Анонимные типы не предоставляют механизм для прямого указания типов данных для свойств. Типы всех свойств определяются посредством вывода. В следующем примере типы `Name` и `Price` выводятся напрямую из значений, которые используются для их инициализации.  
  
 [!code-vb[VbVbalrAnonymousTypes#1](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_1.vb)]  
  
 Анонимные типы также могут выводить имена и типы свойств из других источников. В последующих разделах представлен список ситуаций, где вывод возможен, и примеры обратных ситуаций.  
  
## <a name="successful-inference"></a>Успешный вывод  
  
#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a>Анонимные типы могут выводить имена и типы свойств из следующих источников.  
  
-   Из имен переменных. Анонимный тип `anonProduct` будет иметь два свойства: `productName` и `productPrice`. Их типами данных будут типы исходных переменных, `String` и `Double`соответственно.  
  
     [!code-vb[VbVbalrAnonymousTypes#11](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_2.vb)]  
  
-   Из имен свойств или полей других объектов. Например, рассмотрим объект `car` типа `CarClass` , включающий свойства `Name` и `ID` . Чтобы создать новый экземпляр анонимного типа `car1`со свойствами `Name` и `ID` , которые инициализируются значениями из объекта `car` , можно написать следующее.  
  
     [!code-vb[VbVbalrAnonymousTypes#34](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_3.vb)]  
  
     Предыдущее объявление эквивалентно большей строке кода, определяющей анонимный тип `car2`.  
  
     [!code-vb[VbVbalrAnonymousTypes#35](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_4.vb)]  
  
-   Из имен элементов XML  
  
     [!code-vb[VbVbalrAnonymousTypes#12](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_5.vb)]  
  
     Результирующий тип для `anon` будет иметь одно свойство `Book`c типом <xref:System.Collections.IEnumerable>(XElement).  
  
-   Из функции, которая не имеет параметров, например `SomeFunction` в следующем примере.  
  
     `Dim sc As New SomeClass`  
  
     `Dim anon1 = New With {Key sc.SomeFunction()}`  
  
     Переменная `anon2` в следующем коде является анонимным типом, который имеет одно свойство: знак с именем `First`. Этот код будет отображать букву E — букву, которая возвращена функцией <xref:System.Linq.Enumerable.First%2A>.  
  
     [!code-vb[VbVbalrAnonymousTypes#13](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_6.vb)]  
  
## <a name="inference-failures"></a>Неудачный вывод  
  
#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a>Вывод имени завершится сбоем во многих случаях, в том числе в следующих.  
  
-   Вывод является производным от вызова метода, конструктора или параметризованного свойства, для которого требуются аргументы. Предыдущее объявление `anon1` завершается сбоем, если `someFunction` имеет один или несколько аргументов.  
  
     `' Not valid.`  
  
     `' Dim anon3 = New With {Key sc.someFunction(someArg)}`  
  
     Проблема решается путем назначения новому имени свойства.  
  
     `' Valid.`  
  
     `Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}`  
  
-   Вывод является производным от сложного выражения.  
  
    ```  
    Dim aString As String = "Act "  
    ' Not valid.  
    ' Dim label = New With {Key aString & "IV"}  
    ```  
  
     Ошибку можно устранить, назначив результат выражения для имени свойства.  
  
     [!code-vb[VbVbalrAnonymousTypes#14](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_7.vb)]  
  
-   Вывод нескольких свойств создает два или более свойств с одинаковым именем. Возвращаясь к объявлениям в предыдущих примерах, невозможно указывать `product.Name` и `car1.Name` в качестве свойств для одного анонимного типа. Это связано с тем, что выводимый идентификатор для каждого из них будет `Name`.  
  
     `' Not valid.`  
  
     `' Dim anon5 = New With {Key product.Name, Key car1.Name}`  
  
     Проблему можно решить, назначив значения уникальным именам свойств.  
  
     [!code-vb[VbVbalrAnonymousTypes#36](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_8.vb)]  
  
     Обратите внимание, что изменение регистра (изменение прописных букв на строчные и наоборот) не делает имя уникальным.  
  
     `Dim price = 0`  
  
     `' Not valid, because Price and price are the same name.`  
  
     `' Dim anon7 = New With {Key product.Price, Key price}`  
  
-   Исходные тип и значение одного свойства зависят от другого свойства, которое еще не установлено. Например, `.IDName = .LastName` не является допустимым в объявлении анонимного типа, если только `.LastName` уже не инициализирован.  
  
     `' Not valid.`  
  
     `' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}`  
  
     В этом примере проблему можно устранить, изменив порядок, в котором объявлены свойства, на обратный.  
  
     [!code-vb[VbVbalrAnonymousTypes#15](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_9.vb)]  
  
-   Имя свойства анонимного типа совпадает с именем элемента <xref:System.Object>. Например, следующее объявление завершится сбоем, так как `Equals` — это метод <xref:System.Object>.  
  
     `' Not valid.`  
  
     `' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _`  
  
     `'                       "greater than", Key .Less = "less than"}`  
  
     Проблему можно устранить, изменив имя свойства:  
  
     [!code-vb[VbVbalrAnonymousTypes#16](../../../../visual-basic/language-reference/modifiers/codesnippet/VisualBasic/how-to-infer-property-names-and-types-in-anonymous-type-declarations_10.vb)]  
  
## <a name="see-also"></a>См. также  
 [Инициализаторы объектов. Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Key](../../../../visual-basic/language-reference/modifiers/key.md)
