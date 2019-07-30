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
ms.openlocfilehash: 68f92142cdc435ebd82101eea83035e1d09dcf25
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630014"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Практическое руководство. Доступ к переменной, скрытой производным классом (Visual Basic)

Когда код в производном классе получает доступ к переменной, компилятор обычно разрешает ссылку на ближайшую доступную версию, то есть доступную версию с минимальными производными шагами назад от класса доступа. Если переменная определена в производном классе, код обычно получает доступ к определению.

Если переменная производного класса затеняет переменную в базовом классе, она скрывает версию базового класса. Однако можно получить доступ к переменной базового класса, указав ее с `MyBase` помощью ключевого слова.

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Доступ к переменной базового класса, скрытой производным классом

- В выражении или операторе присваивания перед именем `MyBase` переменной следует указать ключевое слово и точку (`.`).

    Компилятор разрешает ссылку на версию базового класса переменной.

    В следующем примере показано затенение с помощью наследования. Он делает две ссылки — одну, которая обращается к переменной с тенью, и одну, которая обходит затенение.

    ```vb
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

    В предыдущем примере переменная `shadowString` объявляется в базовом классе и переобъявляется в производном классе. Процедура `showStrings` в производном классе отображает версию строки с тенью, если ее имя `shadowString` не является полным. После этого она отображает затененную версию, `shadowString` если дополнена `MyBase` ключевым словом.

## <a name="robust-programming"></a>Отказоустойчивость

Чтобы снизить риск обращения к непреднамеренной версии затененной переменной, можно полностью определить все ссылки на затененную переменную. При затенении введено более одной версии переменной с тем же именем. Если инструкция Code ссылается на имя переменной, версия, на которую компилятор разрешает ссылку, зависит от таких факторов, как расположение инструкции Code и наличие подходящих строк. Это может увеличить риск обращения к неверной версии переменной.

## <a name="see-also"></a>См. также

- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Затенение в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Различия между затемнением и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Практическое руководство. Скрыть переменную с тем же именем, что и у вашей переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Практическое руководство. Скрыть унаследованную переменную](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
