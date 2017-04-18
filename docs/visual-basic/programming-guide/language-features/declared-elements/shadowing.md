---
title: "Сокрытие в Visual Basic | Документы Microsoft"
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
- inheritance, shadowing
- overriding, and shadowing
- shadowing
- duplicate names
- shadowing, by inheritance
- declared elements, referencing
- shadowing, by scope
- declared elements, hiding
- naming conflicts, shadowing
- declared elements, shadowing
- shadowing, and overriding
- scope, shadowing
- Shadows keyword, about
- objects [Visual Basic], names
- names, shadowing
ms.assetid: 54bb4c25-12c4-4181-b4a0-93546053964e
caps.latest.revision: 24
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
ms.openlocfilehash: 5f4053de05f0a7a42fccdade1714e08f8eb172e6
ms.lasthandoff: 03/13/2017

---
# <a name="shadowing-in-visual-basic"></a>Сокрытие в Visual Basic
Если два программных элемента имеют общее имя, один из них может скрыть, или *тени*, другой. В такой ситуации затененный элемент недоступен для обращения. Вместо этого в том случае, если ваш код использует имя элемента [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] компилятор разрешает его переопределяющий элемент.  
  
## <a name="purpose"></a>Назначение  
 Основным предназначением затенения является защита определения членов класса. Базовый класс может претерпеть изменения, создается элемент с тем же именем, как вы уже определены. В этом случае `Shadows` применении модификатора ссылается через классе член определенный, а не к новому элементу базового класса.  
  
## <a name="types-of-shadowing"></a>Типы затенения  
 Элемент может затенить другой двумя разными способами. Переопределяющий элемент может быть объявлен внутри подобласти области, содержащей затеняемый элемент, в котором выполняется тогда затенение *посредством области*. Или производный класс может переопределить член базового класса, в котором происходит тогда затенение *через наследование*.  
  
### <a name="shadowing-through-scope"></a>Затемнения посредством области  
 Существует возможность программирования элементов модуля, класса или структуры таким же именем, но разными областями действия. Если два элемента объявляются таким образом и код обращается к их общему имени, элемент с более узкой областью действия затеняет второй элемент (узкая — область видимости блока).  
  
 Например, модуль может определить `Public` переменной с именем `temp`, и процедура в модуле может объявить локальную переменную также `temp`. Ссылки на `temp` с помощью процедуры, доступ к локальной переменной, а ссылки на `temp` из вне процедуры — к `Public` переменной. В данном случае переменная процедуры `temp` затеняет переменную модуля `temp`.  
  
 На следующем рисунке показано две переменные, обе с именем `temp`. Локальная переменная `temp` затеняет переменную-член `temp` при доступе из своей собственной процедуры `p`. Однако `MyClass` ключевое слово обходит затенение и обращается к переменной-члена.  
  
 ![График схемы затемнения посредством области](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowscope.gif "ShadowScope")  
Затемнения посредством области  
  
 Примером затемнения посредством области в разделе [как: сокрытие переменной с тем же именем, как к переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md).  
  
### <a name="shadowing-through-inheritance"></a>Затемнения посредством наследования  
 Если производный класс переопределяет программный элемент, наследуемый от базового класса, переопределенный элемент затеняет первоначальный элемент. С любой другой тип способен переобъявить любой тип, объявленный элемент или набор перегруженных элементов. Например `Integer` может затенить переменную `Function` процедуры. При скрытии процедуры другой можно использовать другой список параметров и другой тип возвращаемого значения.  
  
 На следующем рисунке показан базовый класс `b` и производный класс `d` , производный от `b`. Базовый класс определяет процедуру с именем `proc`, и его скрывает производного класса с помощью другой процедуры с тем же именем. Первый `Call` оператор обращается к затенение `proc` в производном классе. Однако `MyBase` ключевое слово обходит затенение и обращается к затененной процедуре в базовом классе.  
  
 ![График схемы затемнения посредством наследования](../../../../visual-basic/programming-guide/language-features/declared-elements/media/shadowinherit.gif "ShadowInherit")  
Затемнения посредством наследования  
  
 Примером затемнения посредством наследования в разделе [как: сокрытие переменной с тем же именем, как к переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md) и [как: скрыть унаследованные переменную](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md).  
  
#### <a name="shadowing-and-access-level"></a>Затенение и уровень доступа  
 Переопределяющий элемент не всегда доступен из кода с помощью производного класса. Например, он может быть объявлен `Private`. В таком случае Затенение нарушается и компилятор разрешает все ссылки на один элемент, было бы, если бы не было не затенение. Этот элемент является доступного элемента наименьшем количестве последовательных шагов от идентичной класса. Если затененный элемент — процедура, разрешение является ближайший доступный с тем же именем, список параметров и возвращаемого типа.  
  
 В следующем примере показано иерархии наследования из трех классов. Каждый класс определяет `Sub` процедура `display`, и каждый производный класс затеняет `display` процедуру в базовом классе.  
  
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
  
 В предыдущем примере производный класс `secondClass` тени `display` с `Private` процедуры. Когда модуль `callDisplay` вызовов `display` в `secondClass`, вызывающий код находится вне `secondClass` и поэтому не могут получить закрытый `display` процедуры. Затенение нарушается, и компилятор разрешает ссылку на базовый класс `display` процедуры.  
  
 Однако дополнительный производный класс `thirdClass` объявляет `display` как `Public`, поэтому код в `callDisplay` доступ к нему.  
  
## <a name="shadowing-and-overriding"></a>Сокрытием и переопределением  
 Не следует путать затенение с переопределением. Оба командлета используются, когда производный класс наследует от базового класса, и другое замещает один объявленный элемент другим. Но существуют значительные различия между ними. Сравнение см. в разделе [различия между сокрытием и подмена](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md).  
  
## <a name="shadowing-and-overloading"></a>Затенение и перегрузка  
 При скрытии элемента того же базового класса с более чем одним элементом в производный класс, переопределяющий элементы становятся перегруженные версии этого элемента. Дополнительные сведения см. в разделе [перегрузка процедур](../../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="accessing-a-shadowed-element"></a>Доступ к скрытый элемент  
 Обращение к элементу производного класса обычно происходит через текущий экземпляр этого класса путем указания имени элемента `Me` ключевое слово. Если производный класс затеняет элемент базового класса, можно получить доступ к элементу базового класса путем определения ее с `MyBase` ключевое слово.  
  
 Пример доступа к скрытый элемент, в разделе [Практическое руководство: доступ к переменной скрыты с помощью производного класса](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
### <a name="declaration-of-the-object-variable"></a>Объявление переменной объекта  
 Как создать переменную объекта можно также влияет на производный класс обращается к переопределяющий элемент или элемент скрыт. В следующем примере создается два объекта производного класса, но один объект объявлен как базовый класс, а другой — как производного класса.  
  
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
  
 В предыдущем примере переменной `basObj` объявляется как базовый класс. Назначение `dervCls` объекта он реализует расширяющее преобразование и, соответственно, допустимо. Тем не менее, базовый класс не может получить доступ к идентичной версии переменной `z` в производном классе, поэтому компилятор разрешает `basObj.z` к исходному значению базового класса.  
  
## <a name="see-also"></a>См. также  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Расширяющие и сужающие преобразования](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [Тени](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
