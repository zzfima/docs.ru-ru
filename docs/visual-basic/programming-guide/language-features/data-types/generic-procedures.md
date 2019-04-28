---
title: Generic Procedures in Visual Basic
ms.date: 07/20/2015
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
ms.openlocfilehash: 4aed16ce9eb59da54156a0cd5f1594819788521b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61906598"
---
# <a name="generic-procedures-in-visual-basic"></a>Generic Procedures in Visual Basic
Объект *универсальной процедуры*, называемой *универсальный метод*, — это процедура, определенная с помощью по крайней мере один тип параметра. Это позволяет настроить типы данных к его требованиям при каждом вызове процедуры вызывающему коду.  
  
 Процедура не является универсальным, просто в силу определенные внутри универсального класса или структурой универсального типа. Чтобы быть универсальным, процедура должна принимать хотя бы один параметр типа, в дополнение к обычным параметрам, которые может потребоваться. Универсальный класс или структура может содержать неуниверсальные процедуры и неуниверсальный класс, структуру, или модуль может содержать универсальные процедуры.  
  
 Универсальную процедуру можно использовать его параметров типа в обычном списке параметров, в возвращаемом типе, если он имеет один и процедуру его код.  
  
## <a name="type-inference"></a>Вывод типа  
 Универсальную процедуру можно вызвать без аргументов типа вообще. При вызове его таким образом, компилятор пытается определить соответствующий тип данных для передачи аргументов в процедуру типа. Это называется *вывод типа*. В следующем коде показано вызов в котором компилятор выводит, что ему следует передать тип `String` параметру типа `t`.  
  
 [!code-vb[VbVbalrDataTypes#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#15)]  
  
 Если компилятор не может вывести аргументы типа из контекста вызова, он сообщает об ошибке. Одной из возможных причин такой ошибки является несоответствие ранга массива. Например предположим, что вы определяете обычный параметр как массив с параметром типа. При вызове универсальной процедуры предоставив массив другого ранга (число измерений), несоответствие вызывает сбой вывода типа. В следующем коде показано вызов в который двумерный массив передается в процедуру, ожидающую одномерный массив.  
  
```vb  
Public Sub demoSub(Of t)(ByVal arg() As t)
End Sub

Public Sub callDemoSub()
    Dim twoDimensions(,) As Integer
    demoSub(twoDimensions)
End Sub
```
  
 Вывод типа можно вызывать только опуская все аргументы типа. Если указать один аргумент типа, необходимо указать их все.  
  
 Вывод типа поддерживается только для универсальных процедур. Не удается вызвать вывод типа в универсальных классов, структур, интерфейсов или делегатов.  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание  
 В следующем примере определяется универсальный `Function` процедуре, чтобы найти конкретный элемент в массиве. Он определяет один параметр типа и использует его для создания двух параметров в списке параметров.  
  
### <a name="code"></a>Код  
 [!code-vb[VbVbalrDataTypes#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#14)]  
  
### <a name="comments"></a>Комментарии  
 В предыдущем примере требуется возможность сравнения `searchValue` отношению к каждому элементу `searchArray`. Чтобы обеспечить эту возможность, он ограничивает параметр типа `T` для реализации <xref:System.IComparable%601> интерфейс. Код использует <xref:System.IComparable%601.CompareTo%2A> вместо метода `=` оператор, так как нет никакой гарантии, что аргумент типа, предоставленный для `T` поддерживает `=` оператор.  
  
 Вы можете протестировать `findElement` процедуры следующим кодом.  
  
 [!code-vb[VbVbalrDataTypes#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#13)]  
  
 Предыдущие вызовы `MsgBox` отображения «0», «1» и «-1"соответственно.  
  
## <a name="see-also"></a>См. также

- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Практическое руководство. Определение класса, реализующего одинаковую функциональность для разных типов данных](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)
- [Практическое руководство. Использование универсального класса](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
- [Процедуры](../../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)
- [Список типов](../../../../visual-basic/language-reference/statements/type-list.md)
- [Список параметров](../../../../visual-basic/language-reference/statements/parameter-list.md)
