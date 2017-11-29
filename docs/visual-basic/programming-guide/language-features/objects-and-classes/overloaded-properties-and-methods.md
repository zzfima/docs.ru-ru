---
title: "Перегруженные свойства и методы (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names [Visual Basic], multiple procedures with same
- procedures [Visual Basic], mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword [Visual Basic], overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8a872540716941ccd0dbb8b058508b89ce26a988
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Перегруженные свойства и методы (Visual Basic)
Перегрузка — это создание более чем одной процедуры, конструктора экземпляра или свойства в классе с тем же именем, но различными типами аргументов.  
  
## <a name="overloading-usage"></a>Использование перегрузки  
 Перегрузка особенно полезна при объектной модели определяет, что нужно использовать одинаковые имена процедур, работающих с разными типами данных. Например, класс, который может отображать несколько различных типов данных может иметь `Display` процедуры, которые выглядят следующим образом:  
  
 [!code-vb[VbVbalrOOP#64](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 Без использования перегрузки потребуются для создания уникальных имен для каждой процедуры, даже если они выполняют то же самое, как показано далее.  
  
 [!code-vb[VbVbalrOOP#65](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 Перегрузка облегчает использование свойств или методов, так как она предоставляет на выбор типов данных, которые могут использоваться. Например, перегруженных `Display` способов, описанных ранее может вызываться с любым из следующих строк кода:  
  
 [!code-vb[VbVbalrOOP#66](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 Во время выполнения [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] вызовы, правильной процедурой на основе типов данных параметров можно указать.  
  
## <a name="overloading-rules"></a>Правила перегрузки  
 Создайте перегруженного члена класса путем добавления двух или более свойств или методов с тем же именем. За исключением перегруженных унаследованных членов все перегруженные члены должны иметь разные списки параметров и не может использоваться как отличительный функция следующие элементы при перегрузке свойство или процедура:  
  
-   Модификаторы, такие как `ByVal` или `ByRef`, применяемые к элементу или параметров вызываемого члена.  
  
-   Имена параметров  
  
-   Возвращаемые типы процедур  
  
 `Overloads` Ключевое слово не обязательно при перегрузке, но если некоторый перегруженный член использует `Overloads` ключевое слово, то все остальные перегруженные члены с тем же именем необходимо также указать это ключевое слово.  
  
 Производные классы могут перегружать унаследованные члены с членами, имеющими одинаковые параметры и типы параметров, этот процесс называется *перекрытие по имени и подписи*. Если `Overloads` при перекрытие по имени и подписи, реализация производного класса элемента будет использоваться вместо реализации в базовом классе, и все другие перегрузки этого элемента будут доступны для экземпляров используется ключевое слово производный класс.  
  
 Если `Overloads` ключевое слово пропущено при перегрузке унаследованного члена членом, имеющим одинаковые параметры и типы параметров, а затем перегрузка называется *перекрытие по имени*. Перекрытие по имени заменяет унаследованную реализацию элемента и делает все остальные перегрузки недоступными для экземпляров производного класса и его потомков.  
  
 `Overloads` И `Shadows` модификаторы не могут использоваться одновременно с одним свойством или методом.  
  
### <a name="example"></a>Пример  
 В следующем примере создается перегруженные методы, поддерживающие `String` или `Decimal` представление суммы в долларах и возвращающие строку, содержащую налог с продаж.  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Чтобы использовать этот пример для создания перегруженного метода  
  
1.  Откройте новый проект и добавьте класс с именем `TaxClass`.  
  
2.  Добавьте следующий код в класс `TaxClass`.  
  
     [!code-vb[VbVbalrOOP#67](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  Добавьте следующую процедуру в форму.  
  
     [!code-vb[VbVbalrOOP#68](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  Добавьте кнопку в форму и вызовите `ShowTax` процедуры из `Button1_Click` события кнопки.  
  
5.  Запустите проект и нажмите кнопку на форме, чтобы проверить перегруженных `ShowTax` процедуры.  
  
 Во время выполнения компилятор выбирает подходящую перегруженную функцию, который соответствует параметрам, используемым. При нажатии кнопки, перегруженный метод сначала вызывается с `Price` параметр, который является строкой и сообщение «цена является строкой. Налог — $5,12" отображается. `TaxAmount`вызывается с `Decimal` значений во второй раз и сообщением, «цена — десятичное число. Налог — $5,12" отображается.  
  
## <a name="see-also"></a>См. также  
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)  
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)  
 [Перегрузки](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
