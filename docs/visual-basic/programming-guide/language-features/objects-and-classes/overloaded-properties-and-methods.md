---
title: "Перегруженные свойства и методы (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- properties [Visual Basic], overloading
- methods [Visual Basic], overloading
- shadowing
- names, multiple procedures with same
- procedures, mulltiples with same name
- classes [Visual Basic], properties
- classes [Visual Basic], methods
- method overloading
- Overloads keyword, overloaded members
ms.assetid: b686fb97-e7d7-4001-afaa-6650cba08f0d
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 6f379f04ca9b75161baf2bf2c33e87f05a9edf97
ms.lasthandoff: 03/13/2017

---
# <a name="overloaded-properties-and-methods-visual-basic"></a>Перегруженные свойства и методы (Visual Basic)
Перегрузка — это создание более чем одной процедуры, конструктора экземпляра или свойства класса с одинаковыми именами, но различными типами аргументов.  
  
## <a name="overloading-usage"></a>Использование перегрузки  
 Перегрузка особенно полезна при объектной модели определяет, что нужно использовать одинаковые имена процедур, работающих с разными типами данных. Например, класс, который может отображать несколько разных типов данных может иметь `Display` процедуры, которые выглядят следующим образом:  
  
 [!code-vb[VbVbalrOOP&#64;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_1.vb)]  
  
 Без использования перегрузки потребуются для создания уникальных имен для каждой процедуры, даже если они выполняют то же самое, как показано далее.  
  
 [!code-vb[VbVbalrOOP&#65;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_2.vb)]  
  
 Перегрузка облегчает использование свойств или методов, поскольку позволяет выбирать типы данных, которые могут использоваться. Например, перегруженных `Display` способов, описанных ранее может вызываться с любым из следующих строк кода:  
  
 [!code-vb[VbVbalrOOP&#66;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_3.vb)]  
  
 Во время выполнения [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] вызовы процедуры на основе типов данных параметров можно указать.  
  
## <a name="overloading-rules"></a>Правила перегрузки  
 Создание перегруженного члена класса путем добавления двух или более свойств или методов с одинаковыми именами. За исключением перегруженных унаследованных членов все перегруженные члены должны иметь разные списки параметров и не может использоваться как отличительный функция следующие элементы при перегрузке свойство или процедура:  
  
-   Модификаторы, такие как `ByVal` или `ByRef`, которые применимы к элементу, или параметрам элемента.  
  
-   Имена параметров  
  
-   Возвращаемые типы процедур  
  
 `Overloads` Ключевое слово не обязательно при перегрузке, но если некоторый перегруженный элемент использует `Overloads` ключевое слово, то все остальные перегруженные члены с тем же именем необходимо также указать это ключевое слово.  
  
 Производные классы могут перегружать унаследованные члены с членами, имеющими идентичные параметры и типы параметров, этот процесс называется *перекрытие по имени и подписи*. Если `Overloads` при перекрытие по имени и подписи, реализация производного класса элемента будет использоваться вместо реализации в базовом классе, и все другие перегрузки этого элемента будут доступны для экземпляров производного класса используется ключевое слово.  
  
 Если `Overloads` ключевое слово пропущено при перегрузке унаследованного элемента элементом, имеющим одинаковые параметры и типы параметров, а затем перегрузка называется *перекрытие по имени*. Перекрытие по имени заменяет унаследованную реализацию элемента и делает все остальные перегрузки недоступными для экземпляров производного класса и его потомков.  
  
 `Overloads` И `Shadows` модификаторы не могут использоваться одновременно с одним свойством или методом.  
  
### <a name="example"></a>Пример  
 В следующем примере создается перегруженные методы, поддерживающие `String` или `Decimal` представление суммы в долларах и возвращающие строку, содержащую налог с продаж.  
  
##### <a name="to-use-this-example-to-create-an-overloaded-method"></a>Чтобы использовать этот пример для создания перегруженного метода  
  
1.  Откройте новый проект и добавьте класс с именем `TaxClass`.  
  
2.  Добавьте следующий код в класс `TaxClass`.  
  
     [!code-vb[VbVbalrOOP&#67;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_4.vb)]  
  
3.  Добавьте следующую процедуру в форму.  
  
     [!code-vb[VbVbalrOOP&#68;](../../../../visual-basic/misc/codesnippet/VisualBasic/overloaded-properties-and-methods_5.vb)]  
  
4.  Добавьте кнопку в форму и вызовите `ShowTax` процедуру `Button1_Click` событие кнопки.  
  
5.  Запустите проект и нажмите кнопку на форме, чтобы проверить перегруженную `ShowTax` процедуры.  
  
 Во время выполнения компилятор выбирает подходящую перегруженную функцию, соответствующую параметрам, используемым. При нажатии кнопки, перегруженный метод сначала вызывается с `Price` параметр, который является строкой и сообщение, «Price is a String. Налог — $5,12" отображается. `TaxAmount`вызывается с `Decimal` значением во второй раз и сообщение, «Price is Decimal. Налог — $5,12" отображается.  
  
## <a name="see-also"></a>См. также  
 [Объекты и классы](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Оператор Sub](../../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)   
 [Тени](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)   
 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)   
 [Перегруженные методы](../../../../visual-basic/language-reference/modifiers/overloads.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
