---
title: Объявление переменных объектов (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- early binding [Visual Basic]
- declarations [Visual Basic], class
- classes [Visual Basic], declaring
- binding [Visual Basic], late and early
- object variables [Visual Basic], declaring
- variables [Visual Basic], object
- declaring variables [Visual Basic], object variables
- declaring classes [Visual Basic]
- late binding [Visual Basic]
ms.assetid: 2a5a41a3-1aa8-4236-b1f0-2382af7bf715
ms.openlocfilehash: f5f77b81380d997e078a9f52ac4aae6f6e975575
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="object-variable-declaration-visual-basic"></a>Объявление переменных объектов (Visual Basic)
Используйте обычный оператор объявления для объявления переменной объекта. Для типа данных, либо указать `Object` (то есть [тип данных Object](../../../../visual-basic/language-reference/data-types/object-data-type.md)) или более определенный класс, из которого будет создан объект.  
  
 Объявление переменной как `Object` совпадает со значением его объявление как <xref:System.Object?displayProperty=nameWithType>.  
  
 При объявлении переменной с помощью конкретного объекта класса доступны всем методам и свойствам этого класса и классов, от которых он наследуется. Если объявить переменную с <xref:System.Object>, он может получить доступ к только к членам <xref:System.Object> класса, если не выключить `Option Strict Off` чтобы разрешить позднее связывание.  
  
## <a name="declaration-syntax"></a>Синтаксис объявления  
 Для объявления переменной объекта, используйте следующий синтаксис:  
  
```vb  
Dim variablename As [New] { objectclass | Object }  
```  
  
 Можно также указать [открытый](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), `Protected Friend`, [закрытый](../../../../visual-basic/language-reference/modifiers/private.md), [Shared](../../../../visual-basic/language-reference/modifiers/shared.md), или [статических](../../../../visual-basic/language-reference/modifiers/static.md) в объявлении. Допустимы следующие варианты объявлений.  
  
```vb  
Private objA As Object  
Static objB As System.Windows.Forms.Label  
Dim objC As System.OperatingSystem  
```  
  
## <a name="late-binding-and-early-binding"></a>Раннее связывание и позднее связывание  
 Иногда определенный класс неизвестно до выполнения кода. В этом случае необходимо объявить переменную объекта с `Object` тип данных. Это создает общую ссылку на объект любого типа, и определенный класс назначается во время выполнения. Это называется *позднего связывания*. Позднее связывание требует дополнительного времени выполнения. Код, чтобы методы и свойства класса, в которых вы назначили недавно в него также ограничивается. Это может вызвать ошибки во время выполнения, если код пытается получить доступ к членам другого класса.  
  
 Если определенный класс известен во время компиляции, следует объявить переменную объекта в этом классе. Этот принцип называется *раннее связывание*. Раннее связывание позволяет повысить производительность и гарантирует доступ к методам и свойствам определенного класса. В предыдущем примере объявлений, если переменная `objA` использует только объекты класса <xref:System.Windows.Forms.Label?displayProperty=nameWithType>, следует указать `As System.Windows.Forms.Label` в его объявлении.  
  
### <a name="advantages-of-early-binding"></a>Преимущества раннего связывания  
 Объявление объектной переменной в определенном классе дает следующие преимущества:  
  
-   Автоматическая проверка типа  
  
-   Гарантированный доступ ко всем членам определенного класса  
  
-   Поддержка технологии Microsoft IntelliSense в редакторе кода  
  
-   Улучшение читаемости кода  
  
-   Меньшее количество ошибок в коде  
  
-   Обнаружение ошибок во время компиляции, а не время выполнения  
  
-   Увеличение скорости выполнения кода  
  
## <a name="access-to-object-variable-members"></a>Доступ к членам объектных переменных  
 Когда `Option Strict` включена `On`, объектной переменной доступны методы и свойства класса, в котором она объявлена. Это показано в следующем примере.  
  
```vb  
' Option statements must precede all other source file lines.  
Option Strict On  
' Imports statement must precede all declarations in the source file.  
Imports System.Windows.Forms  
Public Sub accessMembers()  
    Dim p As Object  
    Dim q As System.Windows.Forms.Label  
    p = New System.Windows.Forms.Label  
    q = New System.Windows.Forms.Label  
    Dim j, k As Integer  
    ' The following statement generates a compiler ERROR.  
    j = p.Left  
    ' The following statement retrieves the left edge of the label in pixels.  
    k = q.Left  
End Sub  
```  
  
 В этом примере `p` может использовать только члены класса <xref:System.Object> без свойства `Left` . С другой стороны, `q` был объявлен с типом <xref:System.Windows.Forms.Label>, поэтому он может использовать все методы и свойства класса <xref:System.Windows.Forms.Label> в пространстве имен <xref:System.Windows.Forms> .  
  
## <a name="flexibility-of-object-variables"></a>Гибкость объектных переменных  
 При работе с объектами в иерархии наследования имеется выбор класс, который будет использоваться при объявлении переменных объектов. При этом, необходимо соблюдать баланс между гибкостью присваивания объекта доступа к членам класса. Например, рассмотрим иерархию наследования, которая приводит к <xref:System.Windows.Forms.Form?displayProperty=nameWithType> класса:  
  
 <xref:System.Object>  
  
 &nbsp;&nbsp;<xref:System.MarshalByRefObject>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;<xref:System.ComponentModel.Component>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Control>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ScrollableControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.ContainerControl>  
  
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<xref:System.Windows.Forms.Form>  
  
 Предположим, что приложение определяет форму `specialForm`, который наследует от класса <xref:System.Windows.Forms.Form>. Можно объявить объектную переменную, которая специально ссылается на `specialForm`, как показано в следующем примере.  
  
```vb  
Public Class specialForm  
    Inherits System.Windows.Forms.Form  
    ' Insert code defining methods and properties of specialForm.  
End Class  
Dim nextForm As New specialForm  
```  
  
 Объявление в предыдущем примере ограничивает переменную `nextForm` объектам класса `specialForm`, но оно также делает все методы и свойства `specialForm` для `nextForm`, а также все члены всех классов из которых `specialForm` наследует.  
  
 Можно сделать общими объектную переменную, объявив ее типа <xref:System.Windows.Forms.Form>, как показано в следующем примере.  
  
```vb  
Dim anyForm As System.Windows.Forms.Form  
```  
  
 Объявление в предыдущем примере позволяет назначить любой форме в приложении `anyForm`. Тем не менее несмотря на то что `anyForm` доступны все члены класса <xref:System.Windows.Forms.Form>, она не может использовать дополнительные методы или свойства, определенные для конкретных форм, таких как `specialForm`.  
  
 Все члены базового класса доступны для производных классов, но дополнительные члены производного класса недоступны для базового класса.  
  
## <a name="see-also"></a>См. также  
 [Объектные переменные](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [Присваивание объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [Значения объектных переменных](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)  
 [Как: объявление объектной переменной и присвоение ей объекта в Visual Basic](../../../../visual-basic/programming-guide/language-features/variables/how-to-declare-an-object-variable-and-assign-an-object-to-it.md)  
 [Практическое руководство. Доступ к членам объекта](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)  
 [Оператор New](../../../../visual-basic/language-reference/operators/new-operator.md)  
 [Оператор Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Вывод локального типа](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
