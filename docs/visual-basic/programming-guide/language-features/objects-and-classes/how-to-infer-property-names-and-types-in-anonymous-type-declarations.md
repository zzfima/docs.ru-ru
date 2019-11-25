---
title: Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов
ms.date: 07/20/2015
helpviewer_keywords:
- inferring property names [Visual Basic]
- anonymous types [Visual Basic], inferring property names and types
- inferring property types [Visual Basic]
ms.assetid: 7c748b22-913f-4d9d-b747-6b7bf296a0bc
ms.openlocfilehash: 89a39e8e9cd66b1d774da70be47c7c6824cccef2
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350027"
---
# <a name="how-to-infer-property-names-and-types-in-anonymous-type-declarations-visual-basic"></a>Практическое руководство. Выведение имен свойств и типов в объявлениях анонимных типов (Visual Basic)

Анонимные типы не предоставляют механизм для прямого указания типов данных для свойств. Типы всех свойств определяются посредством вывода. В следующем примере типы `Name` и `Price` выводятся напрямую из значений, которые используются для их инициализации.

[!code-vb[VbVbalrAnonymousTypes#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#1)]

Анонимные типы также могут выводить имена и типы свойств из других источников. В последующих разделах представлен список ситуаций, где вывод возможен, и примеры обратных ситуаций.

## <a name="successful-inference"></a>Успешный вывод

#### <a name="anonymous-types-can-infer-property-names-and-types-from-the-following-sources"></a>Анонимные типы могут выводить имена и типы свойств из следующих источников.

- Из имен переменных. Анонимный тип `anonProduct` будет иметь два свойства: `productName` и `productPrice`. Их типами данных будут типы исходных переменных, `String` и `Double`соответственно.

  [!code-vb[VbVbalrAnonymousTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#11)]

- Из имен свойств или полей других объектов. Например, рассмотрим объект `car` типа `CarClass` , включающий свойства `Name` и `ID` . Чтобы создать новый экземпляр анонимного типа `car1`со свойствами `Name` и `ID` , которые инициализируются значениями из объекта `car` , можно написать следующее.

  [!code-vb[VbVbalrAnonymousTypes#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#34)]

  Предыдущее объявление эквивалентно большей строке кода, определяющей анонимный тип `car2`.

  [!code-vb[VbVbalrAnonymousTypes#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#35)]

- Из имен элементов XML

  [!code-vb[VbVbalrAnonymousTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#12)]

  Результирующий тип для `anon` будет иметь одно свойство `Book`c типом <xref:System.Collections.IEnumerable>(XElement).

- Из функции, которая не имеет параметров, например `SomeFunction` в следующем примере.

  ```vb
  Dim sc As New SomeClass
  Dim anon1 = New With {Key sc.SomeFunction()}
  ```

  Переменная `anon2` в следующем коде является анонимным типом, который имеет одно свойство: знак с именем `First`. Этот код будет отображать букву E — букву, которая возвращена функцией <xref:System.Linq.Enumerable.First%2A>.

  [!code-vb[VbVbalrAnonymousTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#13)]

## <a name="inference-failures"></a>Неудачный вывод

#### <a name="name-inference-will-fail-in-many-circumstances-including-the-following"></a>Вывод имени завершится сбоем во многих случаях, в том числе в следующих.

- Вывод является производным от вызова метода, конструктора или параметризованного свойства, для которого требуются аргументы. Предыдущее объявление `anon1` завершается сбоем, если `someFunction` имеет один или несколько аргументов.

  ```vb
  ' Not valid.
  ' Dim anon3 = New With {Key sc.someFunction(someArg)}
  ```

  Проблема решается путем назначения новому имени свойства.

  ```vb
  ' Valid.
  Dim anon4 = New With {Key .FunResult = sc.someFunction(someArg)}
  ```

- Вывод является производным от сложного выражения.

  ```vb
  Dim aString As String = "Act "
  ' Not valid.
  ' Dim label = New With {Key aString & "IV"}
  ```

  Ошибку можно устранить, назначив результат выражения для имени свойства.

  [!code-vb[VbVbalrAnonymousTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#14)]

- Вывод нескольких свойств создает два или более свойств с одинаковым именем. Возвращаясь к объявлениям в предыдущих примерах, невозможно указывать `product.Name` и `car1.Name` в качестве свойств для одного анонимного типа. Это связано с тем, что выводимый идентификатор для каждого из них будет `Name`.

  ```vb
  ' Not valid.
  ' Dim anon5 = New With {Key product.Name, Key car1.Name}
  ```

  Проблему можно решить, назначив значения уникальным именам свойств.

  [!code-vb[VbVbalrAnonymousTypes#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#36)]

  Обратите внимание, что изменение регистра (изменение прописных букв на строчные и наоборот) не делает имя уникальным.

  ```vb
  Dim price = 0
  ' Not valid, because Price and price are the same name.
  ' Dim anon7 = New With {Key product.Price, Key price}
  ```

- Исходные тип и значение одного свойства зависят от другого свойства, которое еще не установлено. Например, `.IDName = .LastName` не является допустимым в объявлении анонимного типа, если только `.LastName` уже не инициализирован.

  ```vb
  ' Not valid.
  ' Dim anon8 = New With {Key .IDName = .LastName, Key .LastName = "Jones"}
  ```

  В этом примере проблему можно устранить, изменив порядок, в котором объявлены свойства, на обратный.

  [!code-vb[VbVbalrAnonymousTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#15)]

- Имя свойства анонимного типа совпадает с именем элемента <xref:System.Object>. Например, следующее объявление завершится сбоем, так как `Equals` — это метод <xref:System.Object>.

  ```vb
  ' Not valid.
  ' Dim relationsLabels1 = New With {Key .Equals = "equals", Key .Greater = _
  '                       "greater than", Key .Less = "less than"}
  ```

  Проблему можно устранить, изменив имя свойства:

  [!code-vb[VbVbalrAnonymousTypes#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrAnonymousTypes/VB/Class1.vb#16)]

## <a name="see-also"></a>См. также

- [Инициализаторы объектов. Именованные и анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Анонимные типы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Key](../../../../visual-basic/language-reference/modifiers/key.md)
