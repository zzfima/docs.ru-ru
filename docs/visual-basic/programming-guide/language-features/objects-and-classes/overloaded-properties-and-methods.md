---
title: Перегруженные свойства и методы (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], multiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
ms.openlocfilehash: 8d7341370d9770d2e57f786ac7c68277e66a9bbd
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/08/2019
ms.locfileid: "57677400"
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Перегруженные свойства и методы (Visual Basic)

Перегрузка — это создание более чем одной процедуры, конструктор экземпляра или свойства в классе с тем же именем, но разные типы аргументов.

## <a name="overloading-usage"></a>Использование перегрузки

Перегрузка особенно полезна при объектную модель определяет, что нужно использовать одинаковые имена процедур, работающих на различных типов данных. Например, класс, который может отображать несколько различных типов данных может иметь `Display` процедуры, которые выглядят следующим образом:

[!code-vb[VbVbalrOOP#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#64)]

Без перегрузки, вам потребовалось бы создать уникальные имена для каждой процедуры, несмотря на то, что они делают одно и то же самое, как показано далее:

[!code-vb[VbVbalrOOP#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#65)]

Перегрузка облегчает использование свойств или методов, так как она позволяет выбрать из типов данных, которые могут использоваться. Например, перегруженных `Display` способов, описанных ранее может вызываться с любым из следующих строк кода:

[!code-vb[VbVbalrOOP#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#66)]

Во время выполнения Visual Basic вызывает правильную процедуру, на основе типов данных параметров, указанную вами.

## <a name="overloading-rules"></a>Правила перегрузки

 Создание перегруженного члена класса путем добавления двух или более свойств или методов с одинаковым именем. За исключением перегруженных унаследованных членов все перегруженные члены должны иметь разные списки параметров и не может использоваться как средство отличительный перечисленные ниже при перегрузке свойство или процедура:

- Модификаторы, такие как `ByVal` или `ByRef`, которые применяются к элементу, или параметрам элемента.

- Имена параметров

- Типы возвращаемого значения процедуры

`Overloads` Ключевое слово является необязательным при перегрузке, но если некоторый перегруженный элемент использует `Overloads` ключевое слово, то все остальные перегруженные члены с тем же именем необходимо также указать это ключевое слово.

Производные классы могут перегружать унаследованные члены с членами, имеющими одинаковые параметры и типы параметров, этот процесс называется *перекрытие по имени и подписи*. Если `Overloads` при перекрытие по имени и подписи, реализацию члена производного класса будет использоваться вместо реализации в базовом классе, и все другие перегрузки этого элемента будут доступны для экземпляров, используется ключевое слово производный класс.

Если `Overloads` слово опущено, при перегрузке унаследованный член с членом, имеющим одинаковые параметры и типы параметров, а затем перегрузка называется *перекрытие по имени*. Перекрытие по имени заменяет унаследованной реализации члена, и делает все остальные перегрузки недоступными для экземпляров производного класса и его потомков.

`Overloads` И `Shadows` модификаторы не могут использоваться одновременно с одним свойством или методом.

### <a name="example"></a>Пример

В следующем примере создается перегруженные методы, поддерживающие `String` или `Decimal` представление суммы в долларах и возвращающие строку, содержащую налог с продаж.

#### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Чтобы использовать этот пример для создания перегруженного метода

1. Откройте новый проект и добавьте класс с именем `TaxClass`.

2. Добавьте следующий код в класс `TaxClass` .

    [!code-vb[VbVbalrOOP#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#67)]

3. Добавьте следующую процедуру в форму.

    [!code-vb[VbVbalrOOP#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#68)]

4. Добавьте кнопку в форму и вызовите `ShowTax` процедуры из `Button1_Click` события кнопки.

5. Запустите проект и нажмите кнопку на форме, чтобы проверить перегруженных `ShowTax` процедуры.

Во время выполнения компилятор выбирает соответствующий перегруженной функции, который соответствует параметрам, используемым. При нажатии кнопки, перегруженный метод сначала вызывается с `Price` параметр, который является строкой и сообщение, «цена is a String. Налог — $5,12" отображается. `TaxAmount` вызывается с `Decimal` значение во второй раз и сообщение, «цена — десятичное число. Налог — $5,12" отображается.

## <a name="see-also"></a>См. также

- [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)
- [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)
- [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
