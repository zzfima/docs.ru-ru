---
title: Generic Procedures in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- generic methods [Visual Basic], type inference
- generics [Visual Basic], type inference
- procedures [Visual Basic], generic
- generic procedures
- type inference, generics
- generic methods [Visual Basic]
- type inference
- generics [Visual Basic], procedures
- generic procedures [Visual Basic], type inference
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e019ca32277f93f798e99e996a3670c8302ba9b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="generic-procedures-in-visual-basic"></a>Generic Procedures in Visual Basic
Объект *универсальной процедуры*, который также называется *универсальный метод*, — это процедура, определенная с помощью по крайней мере один тип параметра. Это позволяет вызывающий код, чтобы адаптировать типы данных к его требованиям при каждом вызове процедуры.  
  
 Процедура не является универсальным просто посредством она определена внутри универсального класса или структурой универсального типа. Чтобы быть универсальной, процедура должна принимать хотя бы один параметр типа, в дополнение к обычным параметрам, которые может потребоваться. Универсальный класс или структура может содержать неуниверсальные процедуры, а неуниверсальные класс, структура, или модуль может содержать универсальные процедуры.  
  
 Универсальную процедуру можно использовать его параметров типа в обычном списке параметров, в возвращаемом типе, если он имеет один и процедуру его код.  
  
## <a name="type-inference"></a>Вывод типа  
 Универсальная процедура можно вызвать без указания аргументов типа вообще. При ее вызове таким образом, компилятор пытается определить соответствующий тип данных для передачи аргументов в процедуру типа. Это называется *вывод типа*. В следующем коде показан вызов в котором компилятор выводит, что ему следует передать тип `String` в параметр типа `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 Если компилятор не может вывести аргументы типа из контекста вызова, он сообщает об ошибке. Одной из возможных причин такой ошибки является несоответствие ранга массива. Например предположим, что определили обычные параметры в виде байтового массива параметром типа. При вызове универсальной процедуры предоставив массив различных ранг (число измерений), несоответствие вызывает сбой вывода типа. В следующем коде показан вызов в двумерный массив передаваемый в процедуру, ожидающую одномерный массив.  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 Определения типов можно вызвать только путем пропуска все аргументы типа. Если указывается один аргумент типа, необходимо указать их все.  
  
 Вывод типа поддерживается только для универсальных процедур. Невозможно вызвать вывод типа на универсальные классы, структуры, интерфейсы и делегаты.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере определяется универсальный `Function` процедуру для поиска конкретного элемента в массиве. Он определяет один параметр типа и использует его для создания двух параметров в списке параметров.  
  
### <a name="code"></a>Код  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### <a name="comments"></a>Комментарии  
 В предыдущем примере требуется возможность сравнения `searchValue` с каждым элементом `searchArray`. Чтобы обеспечить эту возможность, параметр типа ограничен `T` для реализации <xref:System.IComparable%601> интерфейса. Код использует <xref:System.IComparable%601.CompareTo%2A> вместо метода `=` оператор, так как нет никакой гарантии, что аргумент типа, предоставляемый для `T` поддерживает `=` оператор.  
  
 Можно проверить `findElement` процедуры следующим кодом.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 Предыдущие вызовы `MsgBox` отображают «0», «1» и «-1"соответственно.  
  
## <a name="see-also"></a>См. также  
 [Универсальные типы в Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Практическое руководство. Определение класса, реализующего одинаковую функциональность для различных типов данных](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)  
 [Практическое руководство. Использование универсального класса](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)  
 [Список типов](../../../../visual-basic/language-reference/statements/type-list.md)  
 [Список параметров](../../../../visual-basic/language-reference/statements/parameter-list.md)
