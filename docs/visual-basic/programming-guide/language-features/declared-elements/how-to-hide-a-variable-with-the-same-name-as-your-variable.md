---
title: "Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af031f3ef134b2a509922e6ada28aa5b2b80d641
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Практическое руководство. Сокрытие переменной с тем же именем, что и ваша переменная (Visual Basic)
Можно скрыть переменной с *затенение* его, то есть переопределением с переменной с тем же именем. Можно скрыть переменную, которую вы хотите скрыть двумя способами:  
  
-   **Затемнения посредством области.** Его можно скрыть посредством области путем ее переопределения внутри подобласти содержит переменную, которую требуется скрыть.  
  
-   **Затемнения посредством наследования.** Если вы хотите скрыть переменная определяется на уровне класса, можно скрыть его через наследование путем ее переопределения с [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в производном классе.  
  
## <a name="two-ways-to-hide-a-variable"></a>Два способа сокрытия переменной  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Чтобы скрыть переменную с помощью области  
  
1.  Определите переменную, которую вы хотите скрыть область и подобласть, в которой будет производиться переопределение переменной.  
  
    |Область переменной|Допустимые подобласти для ее переопределения|  
    |-----------------------|-------------------------------------------|  
    |Модуль|Класс в модуле|  
    |Класс|Подкласс внутри класса<br /><br /> Процедура внутри класса|  
  
     Нельзя переопределить переменную процедуры в блоке, в рамках этой процедуры, например в `If`... `End If` построения или `For` цикла.  
  
2.  Создайте подобласть, если он еще не существует.  
  
3.  В пределах подобласти, запись [оператор Dim](../../../../visual-basic/language-reference/statements/dim-statement.md) объявление переменной затенения.  
  
     Когда код внутри подобласти ссылается на имя переменной, компилятор разрешает ссылку переменной затенения.  
  
     В следующем примере показано затемнения посредством области, а также ссылки, который обходит затенение.  
  
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
  
     В предыдущем примере объявляются переменная `num` как на уровне модуля, так и на уровне процедуры (в процедуре `show`). Локальная переменная `num` скрывает переменную уровня модуля `num` в `show`, поэтому локальная переменная имеет значение 2. Однако есть нет локальной переменной для скрытия `num` в `useModuleLevelNum` процедуры. Таким образом `useModuleLevelNum` присваивает значение переменной уровня модуля 1.  
  
     `MsgBox` Вызывать внутри `show` обходит механизм скрывающий путем уточнения `num` с именем модуля. Поэтому он отображает переменную уровня модуля, вместо локальной переменной.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Чтобы скрыть переменную с помощью наследования  
  
1.  Убедитесь, что переменная, которую вы хотите скрыть объявлена в классе и на уровне класса (вне любых процедур). В противном случае он не может переобъявлять через наследование.  
  
2.  Определите класс, производный от класса переменной, если еще не существует.  
  
3.  Внутри производного класса, напишите `Dim` инструкции объявления переменной. Включить [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) ключевое слово в объявлении.  
  
     Когда код в производном классе ссылается на имя переменной, компилятор разрешает ссылку на переменную.  
  
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
 Затенение представляет несколько версий переменной с тем же именем. Когда оператор кода ссылается на имя переменной, версии, для которого компилятор разрешает ссылку зависит от факторов, таких как расположение оператора кода и наличие уточняющей строки. Это может увеличить риск ссылки на неправильную версию затененной переменной. Можно снизить этот риск, полное все ссылки на затененную переменную.  
  
## <a name="see-also"></a>См. также  
 [Ссылки на объявленные элементы](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Сокрытие в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Различия между затемнением и переопределением](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [Практическое руководство. Сокрытие наследуемой переменной](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Практическое руководство. Доступ к переменной, скрытой производным классом](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Переопределения](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase и MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Основы наследования](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
