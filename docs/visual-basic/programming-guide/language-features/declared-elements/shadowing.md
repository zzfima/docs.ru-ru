---
title: Удаленное управление
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
ms.openlocfilehash: 20a33478f622fca6d3183772f53dcb3e72f79409
ms.sourcegitcommit: 43d10ef65f0f1fd6c3b515e363bde11a3fcd8d6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2020
ms.locfileid: "78266889"
---
# <a name="shadowing-in-visual-basic"></a>Сокрытие в Visual Basic
Когда два элемента программирования имеют одно и то же имя, один из них может скрыть, или *тень*, другой. В такой ситуации затененный элемент недоступен для справки; вместо этого, когда код использует имя элемента, компилятор Visual Basic разрешает его элементу оттенения.  
  
## <a name="purpose"></a>Назначение  
 Основная цель слежки — защитить определение членов класса. Базовый класс может подвергнуться изменению, которое создает элемент с тем же именем, что и тот, который вы уже определили. В этом случае `Shadows` модификатор заставляет ссылки через ваш класс, чтобы быть решенным к определенному элементу, а не к новому элементу базового класса.  
  
## <a name="types-of-shadowing"></a>Типы теней  
 Элемент может затмевать другой элемент двумя различными способами. Элемент тени может быть объявлен внутри субрегиона региона, содержащего затененный элемент, и в этом случае затенение осуществляется *через область.* Или производное класс может переопределить члена базового класса, и в этом случае слежка осуществляется *через наследство.*  
  
### <a name="shadowing-through-scope"></a>Тень через область  
 Элементы программирования в одном модуле, классе или структуре могут иметь одно и то же имя, но разные области. Когда два элемента объявляются таким образом и код относится к имени, которое они разделяют, элемент с более узким объемом тени другого элемента (область блока является самой узкой).  
  
 Например, модуль может `Public` определить `temp`переменную, названную, а процедура в `temp`модуле может объявить местную переменную, также названную. Ссылки `temp` на из нутри процедуры имеют доступ `temp` к локальной переменной, в то время как ссылки на из-за пределов процедуры имеют доступ к переменной. `Public` В этом случае переменная `temp` процедуры `temp`затеняет переменную модуля.  
  
 На следующей иллюстрации показаны `temp`две переменные, обе названы . Локальная `temp` переменная тени `temp` переменной члена при доступе из своей собственной процедуры. `p` Однако `MyClass` ключевое слово обходит тень и получает доступ к переменной члена.  
  
 ![Графика, которая показывает, оттеядая через область.](./media/shadowing/shadow-scope-diagram.gif)
  
 Для примера оттепования через область, [см. Как: Скрыть переменную с тем же именем, как ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Тень через наследство  
 Если полученный класс переопределяет элемент программирования, унаследованный от базового класса, элемент переосмысления затеняет исходный элемент. Вы можете затенить любой тип заявленного элемента или набор перегруженных элементов любым другим типом. Например, `Integer` переменная может `Function` затмить процедуру. Если вы затеняете процедуру другой процедурой, можно использовать другой список параметров и другой тип возврата.  
  
 На следующей иллюстрации `b` показан базовый `d` класс и `b`производный класс, который наследует от . Базовый класс определяет процедуру, названную, `proc`и полученный класс затеняет ее другой процедурой с тем же названием. Первое `Call` утверждение получает доступ `proc` к теневому выводу в производном классе. Однако `MyBase` ключевое слово обходит тени и получает доступ к затененных процедурам в базовом классе.  
  
 ![График схемы затемнения посредством наследования](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Для примера тени через наследство, [см. Как: Скрыть переменную с тем же именем, как ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) и [как: Скрыть унаследованные переменные](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Уровень тени и доступа  
 Элемент оттенения не всегда доступен из кода с использованием произветядного класса. Например, он может `Private`быть объявлен . В таком случае, тень побеждена, и компилятор разрешает любую ссылку на тот же элемент, который он имел бы, если бы не было тени. Этот элемент является доступным элементом наименьшего производним шагов назад от теневого класса. Если затененный элемент является процедурой, разрешение находится в ближайшей доступной версии с тем же именем, списком параметров и типом возврата.  
  
 В следующем примере показана иерархия наследования трех классов. Каждый класс `Sub` определяет `display`процедуру, и каждый `display` выведенный класс затеняет процедуру в своем базовом классе.  
  
```vb  
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
  
 В предыдущем примере выведенный `secondClass` класс `display` тени `Private` с процедурой. При `callDisplay` `display` вызове `secondClass`модуля код `secondClass` вызова находится за `display` пределами и поэтому не может получить доступ к частной процедуре. Тень побеждена, и компилятор разрешает ссылку `display` на процедуру базового класса.  
  
 Тем не менее, `thirdClass` дальнейший `display` `Public`класс объявляется `callDisplay` как, так что код может получить к нему доступ.  
  
## <a name="shadowing-and-overriding"></a>Тень и переопределение  
 Не путайте затенение с переопределением. Оба используются, когда полученный класс наследует из базового класса, и оба переопределяют один объявленный элемент с другим. Но между ними существуют существенные различия. Для сравнения, [см.](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
  
## <a name="shadowing-and-overloading"></a>Тень и перегрузка  
 Если вы затеняете один и тот же элемент базового класса с более чем одним элементом в вашем производном классе, элементы оттенения становятся перегруженными версиями этого элемента. Дополнительные сведения см. в разделе [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Доступ к элементу затенения  
 При доступе к элементу из производного класса обычно это происходит через текущий экземпляр этого `Me` производного класса, квалифицируя имя элемента с помощью ключевого слова. Если ваш производный класс затеняет элемент в базовом классе, вы `MyBase` можете получить доступ к элементу базового класса, квалифицируя его с помощью ключевого слова.  
  
 Для примера доступа к затененный элемент, [см. Как: Доступ к переменной скрытые производные класса](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Декларация переменной объекта  
 Способ создания переменной объекта может также повлиять на то, получает сярвый класс к элементу теней или элементу затенения. Следующий пример создает два объекта из производного класса, но один объект объявляется базовым классом, а другой – производным классом.  
  
```vb  
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
  
 В предыдущем примере `basObj` переменная объявляется базовым классом. Назначение `dervCls` объекта ему представляет собой расширение преобразования и поэтому является действительным. Однако базовый класс не может получить `z` доступ к теневой версии переменной `basObj.z` в производной группе, поэтому компилятор решает исходное значение базового класса.  
  
## <a name="see-also"></a>См. также раздел

- [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Widening and Narrowing Conversions](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
