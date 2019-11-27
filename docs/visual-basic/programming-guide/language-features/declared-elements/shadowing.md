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
ms.openlocfilehash: 034b5c0ecf3be6e77048fb7318e931801575f07a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345330"
---
# <a name="shadowing-in-visual-basic"></a>Сокрытие в Visual Basic
Если два программных элемента имеют одно и то же имя, один из них может скрыть или *затенить*другой. В такой ситуации затененный элемент недоступен для справки; Вместо этого, если в коде используется имя элемента, компилятор Visual Basic разрешает его в элемент с тенью.  
  
## <a name="purpose"></a>Цель  
 Основной задачей теневого копирования является защита определения членов класса. Базовый класс может быть подвергнут изменениям, создающим элемент с тем же именем, что и у уже определенного. В этом случае модификатор `Shadows` заставляет ссылки через класс разрешаться в определенный член, а не в новый элемент базового класса.  
  
## <a name="types-of-shadowing"></a>Типы затенения  
 Элемент может скрывать другой элемент двумя разными способами. Элемент с тенью можно объявить внутри подобласти, содержащей затененный элемент. в этом случае затенение выполняется *через область*. Или производный класс может переопределить член базового класса, в этом случае теневая работа осуществляется *с помощью наследования*.  
  
### <a name="shadowing-through-scope"></a>Затенение через область  
 Элементы программирования в одном модуле, классе или структуре могут иметь одно и то же имя, но разные области. Когда два элемента объявляются таким образом и код ссылается на имя, к которому они относятся, элемент с более узким областью скрывает другой элемент (область видимости блока является самой узким элементом).  
  
 Например, модуль может определить `Public` переменную с именем `temp`, а процедура в модуле может объявить локальную переменную с именем `temp`. Ссылки на `temp` из процедуры обращаются к локальной переменной, а ссылки на `temp` извне процедуры обращаются к переменной `Public`. В этом случае переменная процедуры `temp` затеняет переменную модуля `temp`.  
  
 На следующем рисунке показаны две переменные с именем `temp`. Локальная переменная `temp` затеняет переменную члена `temp` при доступе из своей собственной процедуры `p`. Однако ключевое слово `MyClass` обходит затенение и обращается к переменной члена.  
  
 ![Рисунок, демонстрирующий затенение через область.](./media/shadowing/shadow-scope-diagram.gif)
  
 Пример затенения с помощью области см. в разделе [как скрыть переменную с тем же именем, что и у переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Затенение через наследование  
 Если производный класс переопределяет программный элемент, наследуемый от базового класса, переопределяющий элемент затеняет исходный элемент. Можно создать тень любого типа объявленного элемента или набора перегруженных элементов с любым другим типом. Например, переменная `Integer` может скрывать `Function` процедуру. При скрытии процедуры с помощью другой процедуры можно использовать другой список параметров и другой тип возвращаемого значения.  
  
 На следующем рисунке показан базовый класс `b` и производный класс `d`, наследуемый от `b`. Базовый класс определяет процедуру с именем `proc`, а производный класс скрывает его с помощью другой процедуры с тем же именем. Первая инструкция `Call` обращается к `proc`м теневого копирования в производном классе. Однако ключевое слово `MyBase` обходит затенение и обращается к затененной процедуре в базовом классе.  
  
 ![График схемы затемнения посредством наследования](./media/shadowing/shadowing-inherit-diagram.gif)  
  
 Пример затенения с помощью наследования см. в разделе [как скрыть переменную с тем же именем, что и у переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) , и [как скрыть унаследованную переменную](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Затенение и уровень доступа  
 Элемент с тенью не всегда доступен из кода, использующего производный класс. Например, он может быть объявлен `Private`. В этом случае переобъявление нарушается, и компилятор разрешает любую ссылку на тот же элемент, который был бы в случае отсутствия тени. Этот элемент является доступным элементом, который является минимальным количеством порожденных шагов назад от класса теневого копирования. Если затененный элемент является процедурой, то решением является Ближайшая доступная версия с тем же именем, списком параметров и типом возвращаемого значения.  
  
 В следующем примере показана иерархия наследования трех классов. Каждый класс определяет `Sub` процедуру `display`, и каждый производный класс затеняет процедуру `display` в своем базовом классе.  
  
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
  
 В предыдущем примере производный класс `secondClass` теней `display` с помощью `Private` процедуры. Когда модуль `callDisplay` вызывает `display` в `secondClass`, вызывающий код находится за пределами `secondClass` и, следовательно, не может получить доступ к закрытой процедуре `display`. Затенение нарушается, и компилятор разрешает ссылку на базовый класс `display` процедуры.  
  
 Однако следующий производный класс `thirdClass` объявляет `display` как `Public`, поэтому код в `callDisplay` может получить к нему доступ.  
  
## <a name="shadowing-and-overriding"></a>Затенение и переопределение  
 Не путайте перекрытие с переопределением. Оба используются, когда производный класс наследует от базового класса, и оба переопределяют один объявленный элемент с другим. Но существуют значительные различия между ними. Сравнение см. в разделе [различия между затенением и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Затенение и перегрузка  
 Если вы переобъявляете тот же элемент базового класса с более чем одним элементом в производном классе, элементы с тенью становятся перегруженными версиями этого элемента. Дополнительные сведения см. в разделе [Procedure Overloading](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Доступ к затененному элементу  
 При доступе к элементу из производного класса это обычно делается через текущий экземпляр этого производного класса путем уточнения имени элемента с помощью ключевого слова `Me`. Если производный класс затеняет элемент базового класса, можно получить доступ к элементу базового класса, указав его с помощью ключевого слова `MyBase`.  
  
 Пример доступа к затененному элементу см. в разделе [как получить доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Объявление объектной переменной  
 Способ создания объектной переменной также может влиять на то, имеет ли производный класс доступ к теневому элементу или к затененному элементу. В следующем примере создаются два объекта из производного класса, но один объект объявляется как базовый класс, а другой — как производный класс.  
  
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
  
 В предыдущем примере переменная `basObj` объявляется как базовый класс. Назначение объекта `dervCls` для него составляет расширяющее преобразование и, следовательно, является допустимым. Однако базовый класс не может получить доступ к версии теневого копирования переменной `z` в производном классе, поэтому компилятор разрешает `basObj.z` в исходное значение базового класса.  
  
## <a name="see-also"></a>См. также

- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
