---
title: Как выполнить Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)
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
ms.openlocfilehash: a770167bca0dc3538c828bfcc8a8de4ef86e80c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54602420"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Как выполнить Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)
Можно скрыть переменной с *затенение* его, то есть путем переопределения его с переменной с тем же именем. Можно скрыть переменную, которую вы хотите скрыть двумя способами:  
  
-   **Затемнения посредством области.** Его можно скрыть области видимости, путем ее переопределения внутри входит в область, содержащая переменную, которую вы хотите скрыть.  
  
-   **Затемнения посредством наследования.** Если вы хотите скрыть переменная определяется на уровне класса, можно скрыть его через наследование путем ее переопределения с [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в производном классе.  
  
## <a name="two-ways-to-hide-a-variable"></a>Два способа скрыть переменной  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Чтобы скрыть переменную с помощью области  
  
1.  Определите переменную, которую вы хотите скрыть область и подобласть, в котором следует переопределить его переменной.  
  
    |Область переменной|Допустимые подобласти для ее переопределения|  
    |-----------------------|-------------------------------------------|  
    |Module|Класс в модуле|  
    |Класс|Подкласс внутри класса<br /><br /> Процедура внутри класса|  
  
     Не удалось переопределить переменную процедуры в блоке, в рамках этой процедуры, например в `If`... `End If` конструкции или `For` цикла.  
  
2.  Создайте подобласть, если он еще не существует.  
  
3.  В пределах подобласти, написать [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) объявление переменной затенения.  
  
     Когда код внутри подобласти ссылается на имя переменной, компилятор разрешает ссылку переменной затенения.  
  
     В следующем примере показано, затемнения посредством области, а также ссылку, которая обходит затенение.  
  
    ```  
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
  
     В предыдущем примере объявляется переменной `num` как на уровне модуля, так и на уровне процедуры (в процедуре `show`). Локальная переменная `num` скрывает переменную уровня модуля `num` в `show`, поэтому локальная переменная имеет значение 2. Тем не менее, не существует локальной переменной в теневую `num` в `useModuleLevelNum` процедуры. Таким образом `useModuleLevelNum` присваивает значение переменной уровня модуля 1.  
  
     `MsgBox` Вызывать внутри `show` обходит скрывающий механизм путем уточнения `num` с именем модуля. Таким образом он отображает переменную уровня модуля, а не локальной переменной.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Чтобы скрыть переменную с помощью наследования  
  
1.  Убедитесь, что переменная, которую вы хотите скрыть объявлена в классе, а также на уровне класса (вне любых процедур). В противном случае он не может Затенять через наследование.  
  
2.  Определите класс, производный от класса переменной, если еще не существует.  
  
3.  Внутри производного класса, напишите `Dim` инструкции объявления переменной. Включить [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в объявлении.  
  
     Когда код в производном классе ссылается на имя переменной, компилятор разрешает ссылку на переменную.  
  
     В следующем примере показано, затемнения посредством наследования. Он делает две ссылки, который обращается к переменной затенения, а другой обходит затенение.  
  
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
  
     В предыдущем примере объявляется переменной `shadowString` в базовом классе, скрывается в производном классе. Процедура `showStrings` в производном классе отображает версию затенения строки при имя `shadowString` не обработаны квалификатором. Затем он отобразит затененная версия при `shadowString` квалифицируется `MyBase` ключевое слово.  
  
## <a name="robust-programming"></a>Отказоустойчивость  
 Затенение представляет несколько версий переменной с тем же именем. Если оператор кода ссылается на имя переменной, версии, к которому компилятор разрешает ссылку зависит от факторов, таких как расположение оператор кода, а также наличие уточняющей строки. Это может увеличить риск ссылки на неправильную версию затененной переменной. Можно снизить этот риск путем полного все ссылки на переменную тенью.  
  
## <a name="see-also"></a>См. также
- [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Различия между затемнением и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Практическое руководство. Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Практическое руководство. Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
