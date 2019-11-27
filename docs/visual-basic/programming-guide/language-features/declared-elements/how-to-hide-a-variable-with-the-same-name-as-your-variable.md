---
title: Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: 0915adbbabb778b1bdd3b6b30e56725a7e74867c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345360"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)

Переменную можно скрыть, то есть Переопределяя *ее переменной* с тем же именем. Переменную, которую нужно скрыть, можно затенить двумя способами:

- **Затенение через область.** Это можно сделать с помощью области, переобъявляя ее в подобласти области, содержащей переменную, которую необходимо скрыть.

- **Затенение посредством наследования.** Если переменная, которую нужно скрыть, определена на уровне класса, ее можно затенить с помощью наследования, повторно объявляя ее с помощью ключевого слова [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) в производном классе.

## <a name="two-ways-to-hide-a-variable"></a>Два способа скрыть переменную

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Скрытие переменной путем ее скрытия с помощью Scope

1. Определите регион, определяющий переменную, которую необходимо скрыть, и определите подобласть, в которой нужно переопределить переменную.

    |Регион переменной|Допустимая подобласть для переопределения|
    |-----------------------|-------------------------------------------|
    |Модуль|Класс внутри модуля|
    |Class|Подкласс в классе<br /><br /> Процедура в классе|

    Нельзя переопределить переменную процедуры в блоке внутри этой процедуры, например в конструкции `If`...`End If` или в цикле `For`.

2. Создайте подобласть, если она еще не существует.

3. В пределах подобласти напишите [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) , объявляющий переменную с тенью.

    Если код внутри подобласти ссылается на имя переменной, компилятор разрешает ссылку на переменную с тенью.

    В следующем примере демонстрируется затенение через область, а также ссылка, которая обходит затенение.

    ```vb
    Module shadowByScope
        ' The following statement declares num as a module-level variable.
        Public num As Integer
        Sub show()
            ' The following statement declares num as a local variable.
            Dim num As Integer
            ' The following statement sets the value of the local variable.
            num = 2
            ' The following statement displays the module-level variable.
            MsgBox(CStr(shadowByScope.num))
        End Sub
        Sub useModuleLevelNum()
            ' The following statement sets the value of the module-level variable.
            num = 1
            show()
        End Sub
    End Module
    ```

    В предыдущем примере переменная объявляется `num` как на уровне модуля, так и на уровне процедуры (в процедуре `show`). Локальная переменная `num` затеняет переменную уровня модуля `num` в пределах `show`, поэтому локальной переменной присваивается значение 2. Однако в процедуре `useModuleLevelNum` нет локальной переменной для теневого `num`. Таким образом, `useModuleLevelNum` устанавливает значение переменной уровня модуля равным 1.

    `MsgBox` вызов в `show` обходит механизм теневого копирования путем уточнения `num` именем модуля. Таким образом, вместо локальной переменной отображается переменная уровня модуля.

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Скрытие переменной путем ее скрытия с помощью наследования

1. Убедитесь, что переменная, которую нужно скрыть, объявлена в классе и на уровне класса (вне любой процедуры). В противном случае ее нельзя будет скрыть с помощью наследования.

2. Определите класс, производный от класса переменной, если он еще не существует.

3. Внутри производного класса напишите оператор `Dim`, объявляющий переменную. Включите в объявление ключевое слово [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) .

    Если код в производном классе ссылается на имя переменной, компилятор разрешает ссылку на переменную.

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

    В предыдущем примере переменная объявляется `shadowString` в базовом классе и скрывается в производном классе. Процедура, `showStrings` в производном классе, отображает версию строки с тенью, если имя `shadowString` не является полным. Затем отображается затененная версия, если `shadowString` дополнено ключевым словом `MyBase`.

## <a name="robust-programming"></a>Отказоустойчивость

При затенении введено более одной версии переменной с тем же именем. Если инструкция Code ссылается на имя переменной, версия, на которую компилятор разрешает ссылку, зависит от таких факторов, как расположение инструкции Code и наличие подходящих строк. Это может увеличить риск обращения к непреднамеренной версии затененной переменной. Можно снизить этот риск, полностью подполняя все ссылки на затененную переменную.

## <a name="see-also"></a>См. также

- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Затенение в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Различия между затемнением и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Практическое руководство. Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Практическое руководство. Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
