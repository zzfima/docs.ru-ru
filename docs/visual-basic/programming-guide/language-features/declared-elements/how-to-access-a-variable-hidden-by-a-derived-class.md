---
title: Практическое руководство. Доступ к переменной, скрытой производным классом (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 8dd59dff5b8123331237db905432bbb4e94d62ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Практическое руководство. Доступ к переменной, скрытой производным классом (Visual Basic)
Когда код в производном классе получает доступ к переменной, компилятор обычно разрешает ссылку на ближайшую доступную версию, то есть доступный минимальное количество производных действий назад от обращающегося класса. Если переменная определена в производном классе, код обычно обращается к этому определению.  
  
 Если переменная производного класса затеняет переменную в базовом классе, он скрывает версии базового класса. Тем не менее, можно получить доступ к переменной базового класса путем определения ее с `MyBase` ключевое слово.  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Чтобы получить доступ к переменной базового класса, скрытой производным классом  
  
-   В выражение или оператор присваивания, перед именем переменной с `MyBase` ключевое слово и точку (`.`).  
  
     Компилятор разрешает ссылку на версию базового класса переменной.  
  
     В следующем примере показано затемнения посредством наследования. Он делает две ссылки, который обращается к переменной затенения, а другой обходит затенение.  
  
    ```  
    Public Class shadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class shadowDerivedClass  
        Inherits shadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub showStrings()  
            Dim s As String = "Unqualified shadowString: " & shadowString &  
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString  
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     В предыдущем примере объявляются переменная `shadowString` в базовом классе, скрывается в производном классе. Процедура `showStrings` в производном классе отображает версию затенения строки, если имя `shadowString` не обработаны квалификатором. Затем отображается затененная версия при `shadowString` квалифицируется `MyBase` ключевое слово.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Чтобы снизить риск ссылки на неправильную версию затененной переменной, можно полностью определить все ссылки на затененную переменную. Затенение представляет несколько версий переменной с тем же именем. Когда оператор кода ссылается на имя переменной, версии, для которого компилятор разрешает ссылку зависит от факторов, таких как расположение оператора кода и наличие уточняющей строки. Это может увеличить риск ссылки на неправильную версию переменной.  
  
## <a name="see-also"></a>См. также  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Различия между затемнением и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Практическое руководство. Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
