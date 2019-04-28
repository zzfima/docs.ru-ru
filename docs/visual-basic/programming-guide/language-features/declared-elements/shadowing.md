---
title: Сокрытие в Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- inheritance [Visual Basic], shadowing
- overriding, and shadowing
- shadowing
- duplicate names [Visual Basic]
- shadowing, by inheritance
- declared elements [Visual Basic], referencing
- shadowing, by scope
- declared elements [Visual Basic], hiding
- naming conflicts, shadowing
- declared elements [Visual Basic], shadowing
- shadowing, and overriding
- scope [Visual Basic], shadowing
- Shadows keyword [Visual Basic], about
- objects [Visual Basic], names
- names [Visual Basic], shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
ms.openlocfilehash: 9ad992a53618fa2f410e0b0fb23886c30136384f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917921"
---
# <a name="shadowing-in-visual-basic"></a>Сокрытие в Visual Basic
Если два программных элемента имеют одинаковые имена, один из них может скрыть, или *тени*, другой. В таком случае затененный элемент недоступен для обращения. Вместо этого когда код использует имя элемента, компилятор Visual Basic разрешает его скрывающий элемент.  
  
## <a name="purpose"></a>Цель  
 Основная цель затенение является защита определения членов класса. Базовый класс может претерпеть изменения, создается элемент с тем же именем, как один, которые вы уже определили. В этом случае `Shadows` применении модификатора ссылается в классе быть член определенный, а не к новому элементу базового класса.  
  
## <a name="types-of-shadowing"></a>Типы затенения  
 Элемент может затенить другой двумя разными способами. Скрывающий элемент может быть объявлен внутри входит в область, содержащую скрытый элемент, в котором выполняется тогда затенение *через область*. Или производный класс может переопределить член базового класса, в котором выполняется тогда затенение *через наследование*.  
  
### <a name="shadowing-through-scope"></a>Затемнения посредством области  
 Вполне возможно программных элементов, в модуле, классе или структуре могут иметь тем же именем, но разными областями действия. Если код ссылается на имя, они совместно используют два элемента объявляются таким образом, элемент с более узкой областью действия затеняет второй элемент (узкая — область видимости блока).  
  
 Например, модуль может определить `Public` переменную с именем `temp`, и процедура в модуле можно объявить локальную переменную также `temp`. Ссылки на `temp` изнутри процедура доступа к локальной переменной, а ссылки на `temp` из процедуры доступа извне `Public` переменной. В данном случае переменная процедуры `temp` затеняет переменную модуля `temp`.  
  
 На следующем рисунке показаны две переменные, обе с именем `temp`. Локальная переменная `temp` скрывает переменную-член `temp` при доступе из своей собственной процедуры `p`. Тем не менее `MyClass` ключевое слово обходит затенение и обращается к переменной-члена.  
  
 ![Рисунок, показывающий затемнения посредством области.](./media/shadowing/shadow-scope-diagram.gif)
  
 Пример затемнения посредством области, см. в разделе [как: Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Затемнения посредством наследования  
 Если производный класс переопределяет программный элемент, наследуемый от базового класса, переопределенный элемент затеняет исходным элементом. С любой другой тип способен переобъявить любой тип, объявленный элемент или набор перегруженных элементов. Например `Integer` переменной способен переобъявить `Function` процедуры. При скрытии процедуры другой можно использовать другой список параметров и другой тип возвращаемого значения.  
  
 На следующем рисунке показан базовый класс `b` и производный класс `d` , наследуемый от `b`. Базовый класс определяет процедуру с именем `proc`, и его скрывает производного класса с тем же именем. Первый `Call` оператор обращается к затенение `proc` в производном классе. Тем не менее `MyBase` ключевое слово обходит затенение и обращается к затененной процедуре в базовом классе.  
  
 ![График схемы затемнения посредством наследования](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Пример затемнения посредством наследования, см. в разделе [как: Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) и [как: Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Затенение и уровень доступа  
 Скрывающий элемент не всегда доступен из кода с помощью производного класса. Например, он может быть объявлен `Private`. В таком случае Затенение нарушается, и компилятор разрешает все ссылки на один элемент, его длина будет Если был установлен затенения не. Этот элемент является элемент, к наименьшем количестве последовательных шагов от переопределяющий класса. Если переопределяемый элемент является процедурой, разрешение является ближайший доступный с тем же именем, список параметров и тип возвращаемого значения.  
  
 В следующем примере показано иерархии наследования из трех классов. Каждый класс определяет `Sub` процедуры `display`, и каждый производный класс затеняет `display` процедуры в базовом классе.  
  
```  
Public Class firstClass  
    Public Sub display()  
        MsgBox("This is firstClass")  
    End Sub  
End Class  
Public Class secondClass  
    Inherits firstClass  
    Private Shadows Sub display()  
        MsgBox("This is secondClass")  
    End Sub  
End Class  
Public Class thirdClass  
    Inherits secondClass  
    Public Shadows Sub display()  
        MsgBox("This is thirdClass")  
    End Sub  
End Class  
Module callDisplay  
    Dim first As New firstClass  
    Dim second As New secondClass  
    Dim third As New thirdClass  
    Public Sub callDisplayProcedures()  
        ' The following statement displays "This is firstClass".  
        first.display()  
        ' The following statement displays "This is firstClass".  
        second.display()  
        ' The following statement displays "This is thirdClass".  
        third.display()  
    End Sub  
End Module  
```  
  
 В приведенном выше примере производный класс `secondClass` shadows `display` с `Private` процедуры. Когда модуль `callDisplay` вызовы `display` в `secondClass`, вызывающий код находится за пределами `secondClass` и поэтому недоступны для закрытого `display` процедуры. Затенение нарушается, и компилятор разрешает ссылку на базовый класс `display` процедуры.  
  
 Тем не менее, дополнительный производный класс `thirdClass` объявляет `display` как `Public`, поэтому код в `callDisplay` доступа к нему.  
  
## <a name="shadowing-and-overriding"></a>Сокрытием и переопределением  
 Не следует путать затенение с переопределением. Оба используются, когда производный класс наследует от базового класса, и другое замещает один элемент, объявленный с другим. Но существуют значительные различия между ними. Сравнение, см. в разделе [различия между сокрытием и подмена](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Затенение и перегрузка  
 При скрытии же элемент с более чем одним элементом базового класса в производный класс, переопределяющий элементы становятся перегруженные версии этого элемента. Дополнительные сведения см. в разделе [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Доступ к скрытый элемент  
 Для доступа к элементу из производного класса, обычно происходит через текущий экземпляр этого класса, путем указания имени элемента с `Me` ключевое слово. Если производный класс скрывает элемент базового класса, можно получить доступ к элементу базового класса путем определения ее с `MyBase` ключевое слово.  
  
 Пример доступа к скрытый элемент, см. в разделе [как: Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Объявление объектной переменной  
 Как создать переменную объекта можно также влияет на производном классе получает доступ к скрывающий элемент или переопределяемый элемент. В следующем примере создается два объекта производного класса, но один объект объявляется как базовый класс, а другой — как производного класса.  
  
```  
Public Class baseCls  
    ' The following statement declares the element that is to be shadowed.  
    Public z As Integer = 100  
End Class  
Public Class dervCls  
    Inherits baseCls  
    ' The following statement declares the shadowing element.  
    Public Shadows z As String = "*"  
End Class  
Public Class useClasses  
    ' The following statement creates the object declared as the base class.  
    Dim basObj As baseCls = New dervCls()  
    ' Note that dervCls widens to its base class baseCls.  
    ' The following statement creates the object declared as the derived class.  
    Dim derObj As dervCls = New dervCls()  
    Public Sub showZ()   
    ' The following statement outputs 100 (the shadowed element).  
        MsgBox("Accessed through base class: " & basObj.z)  
    ' The following statement outputs "*" (the shadowing element).  
        MsgBox("Accessed through derived class: " & derObj.z)  
    End Sub  
End Class  
```  
  
 В приведенном выше примере переменная `basObj` объявляется в качестве базового класса. Назначение `dervCls` объекта он реализует расширяющее преобразование и, соответственно, допустимо. Тем не менее, базовый класс недоступен скрывающий версии переменной `z` в производном классе, поэтому компилятор разрешает `basObj.z` к исходному значению базового класса.  
  
## <a name="see-also"></a>См. также

- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Область, в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
